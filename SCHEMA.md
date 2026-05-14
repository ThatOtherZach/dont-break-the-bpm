# BreakBPM Data Schema (MVP + Future)

## Core Concepts

- **Players** (accounts): Identified by name or future user ID. For MVP, names are entered manually (no login required).
- **Games**: A single session of pool (8-ball, 9-ball, or future types). Has a unique short code (4 digits) + shareable URL.
- **Actions**: Every discrete event — ball potted, miss, foul, safety, 8-ball sunk, etc. These power BPM calculation and history.

## MVP Schema (in-memory / URL-encoded for now)

```json
{
  "game": {
    "id": "AB12",                    // 4-digit share code
    "type": "8ball" | "9ball",     // extensible
    "status": "active" | "completed",
    "created_at": "2026-05-14T...",
    "ended_at": null | timestamp,
    "winner": null | { "player_id": "p1", "name": "Alex" },
    "total_balls_potted": 12,
    "bpm": 8.7
  },

  "players": [
    {
      "id": "p1",
      "name": "Alex",
      "position": 1,               // Player 1 = game starter
      "team": "solids" | "stripes" | null,
      "balls_potted": [1, 3, 5, 8],
      "fouls": 1,
      "safeties": 0
    },
    ...
  ],

  "actions": [
    {
      "id": "a1",
      "timestamp": "...",
      "player_id": "p1",
      "type": "pot" | "miss" | "foul" | "safety" | "8ball_pot",
      "ball": 3 | "8" | null,
      "legal": true
    }
  ]
}
```

## Future / Production Schema (Supabase / Firebase)

### Tables

**players** (accounts)
- id (uuid, PK)
- name (text)
- email (optional)
- created_at
- stats: { total_games, avg_bpm, win_rate, ... }

**games**
- id (uuid, PK)
- short_code (text, unique, 4 chars)
- type (enum: 8ball, 9ball, ...)
- status (enum)
- created_by (FK → players.id)
- winner_id (FK, nullable)
- started_at, ended_at
- total_duration_seconds
- total_balls_potted
- calculated_bpm

**game_players** (join + team assignment)
- game_id (FK)
- player_id (FK)
- position (1-4)
- team (solids | stripes | null)
- balls_potted_count
- is_winner (bool)

**actions** (immutable log)
- id (uuid, PK)
- game_id (FK)
- player_id (FK)
- timestamp
- type (pot, miss, foul, safety, 8ball, ...)
- ball_number (int 1-15 or null)
- group (solids/stripes/8ball)
- legal (bool)
- notes (text)

### Indexes & Rules
- short_code unique + indexed for fast lookup
- actions append-only (for accurate BPM + replay)
- BPM = total_balls_potted / (total_duration / 60)
- Winner auto-determined on 8-ball pot (8-ball rules) or last ball (9-ball)

## MVP Implementation Notes

- Current `index.html` uses URL `?state=` for sharing (base64 JSON).
- Next version will add:
  - 4-digit short code generation
  - Solids/Stripes assignment in new-game flow
  - Ball selector modal with emojis (⚫ 🔴 🟡 etc.)
  - Proper 8-ball win condition (must clear your group before 8)
  - Action log that feeds BPM + per-player stats

This schema keeps the MVP dead simple while being ready to drop into a real backend with zero migration pain.

*BreakBPM — from break to finish.*