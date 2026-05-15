# BreakBPM

**A retro pool & billiards Balls-Per-Minute (BPM) tracker.**

From the opening break to the final 8-ball — log every shot, watch your pace, play with friends via 4-digit code, or grind in solo practice.

## Current Version: v1.0

### Key Features
- **Full Retro UI** — Classic gray 3D windows, navy title bars, inset/outset borders, Sans Serif font, teal felt background. Nice.
- **Simplified Ball System** — Balls shown as badges with enhanced UI input schema.
- **Smart Ball Selector** — Only shows legal/available balls based on game rules and what’s already sunk.
- **Live BPM Timer** — Calculated from actual sunk balls over game duration.
- **Ball Return Terminal** — Green-on-black readout showing sunk balls in chronological order.
- **8-Ball & 9-Ball Support** — Proper win conditions (must clear your group before 8-ball; 9-ball wins on the 9).
- **Auto Team Assignment** — Solids vs Stripes for 8-ball games. Never forget your balls.
- **Practice Mode** — Solo drills with unlimited racks.
- **Undo, fouls, safeties, shot log** — Full action history.
- **Share Code** — Easy-to-say code (e.g. `K7P2`) + full URL with game state. (Note: Feature TBD)
- **Multiplayer** — Share the link or code. (Note: Feature TBD)

## Data Model (see SCHEMA.md for full details)

- **Players**: Name + optional team (solids/stripes) + stats
- **Games**: Type (8ball/9ball), short code, status, actions[]
- **Actions**: Every pot, miss, foul, safety, win (timestamped for accurate BPM)

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

**Important for future AIs:**
- Read `CONTRIBUTING.md` first — it contains specific instructions and constraints
- Always maintain the Windows 98 aesthetic and `(X)` ball notation
- Keep changes minimal and focused on the retro experience
- Update `CHANGELOG.md` with every release

## Roadmap (Next AI Priorities)

- [ ] Real-time multiplayer (Firebase/Supabase rooms + join by code)
- [ ] Player accounts & persistent history
- [ ] Payment integration (Stripe / crypto per-game credits)
- [ ] Better mobile support
- [ ] Sound effects (classic Windows .wav style)
- [ ] Export game summary

## Credits

Built live with Grok (xAI) + connected GitHub tools.
Original idea by @ThatOtherZach (Zachary Jordan).

*Let’s keep the BreakBPM high.* 🎱
