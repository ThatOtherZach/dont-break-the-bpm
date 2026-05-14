# BreakBPM

**A retro Windows 98-style pool & billiards scorer with live Balls-Per-Minute (BPM) tracking.**

From the opening break to the final 8-ball — log every shot, watch your pace, play with friends via 4-digit code or shareable link, or grind solo practice.

> *"BreakBPM — the score that starts at the break and ends when you win."*

## Current Version: v0.4 (Windows 98 Edition)

This is a **single-file web app** (`index.html`) that feels like a genuine 1998 Windows program.

### Key Features
- **Full Windows 98 UI** — Classic gray 3D windows, navy title bars, inset/outset borders, MS Sans Serif font, teal desktop background.
- **Simplified ball system** — Balls shown as `(1)(3)(8)(2)` text (no emojis).
- **Smart ball selector** — Only shows legal/available balls based on game rules and what’s already sunk.
- **Ball Return terminal** — Green-on-black readout showing sunk balls in chronological order.
- **8-Ball & 9-Ball support** — Proper win conditions (must clear your group before 8-ball; 9-ball wins on the 9).
- **Team assignment** — Solids vs Stripes for 8-ball games.
- **4-digit share code** — Easy-to-say code (e.g. `K7P2`) + full URL with game state.
- **Live BPM + Timer** — Calculated from actual sunk balls over game duration.
- **Multiplayer (async)** — Share the link or code; state travels with the URL.
- **Practice Mode** — Solo drills with unlimited racks.
- **Undo, fouls, safeties, shot log** — Full action history.

## How to Run

Just open `index.html` in any modern browser. No build step, no dependencies.

For best experience:
- Deploy to GitHub Pages (Settings → Pages → Deploy from `main` branch)
- Or run locally with Live Server extension in VS Code

## Project Structure

```
BreakBPM/
├── index.html          # The entire app (HTML + CSS + JS)
├── README.md           # This file
├── SCHEMA.md           # Data model & future backend plan
└── (no other files yet)
```

## Data Model (see SCHEMA.md for full details)

- **Players**: Name + optional team (solids/stripes) + stats
- **Games**: Type (8ball/9ball), short code, status, actions[]
- **Actions**: Every pot, miss, foul, safety, win (timestamped for accurate BPM)

The current implementation stores everything in-memory and serializes to the URL (`?state=...`) for sharing. Ready to drop into Firebase/Supabase later with zero schema changes.

## Vision & Goals

- Make casual pool nights more fun and trackable
- Bring back that satisfying 90s software feel
- Keep the core loop dead simple: Start game → Assign teams → Sink balls → Watch BPM climb → Win with confetti
- Future: Real-time multiplayer rooms, player accounts, payment integration (per-game credits), advanced stats

## What the Next Developer / AI Should Know

This project was built iteratively in one long session. The UI went through several evolutions:
1. Modern Tailwind pool-hall theme
2. Added team assignment + ball selector
3. Added 4-digit codes + proper win rules
4. Full Windows 98 retro theme + simplified `(X)` ball system (current state)

The ball return was specifically designed to feel like a physical pool table ball return — balls appear in order as they’re logged.

Key files to edit:
- `index.html` — everything lives here (keep it single-file for now)
- `SCHEMA.md` — the source of truth for data model

When adding features, prioritize:
- Keeping the retro Win98 aesthetic
- Making ball selection feel fair and rule-accurate
- Keeping the terminal readout clean and satisfying

## Roadmap (Next AI Priorities)

- [ ] Real-time multiplayer (Firebase/Supabase rooms + join by code)
- [ ] Player accounts & persistent history
- [ ] Payment integration (Stripe / crypto per-game credits)
- [ ] Better mobile support (current is desktop-first Win98)
- [ ] Sound effects (classic Windows .wav clicks?)
- [ ] Export game summary as image/PDF

## Credits

Built live with Grok (xAI) + connected GitHub tools.
Original idea by @ThatOtherZach (Zachary Jordan).

*Let’s keep the BreakBPM high.* 🎱