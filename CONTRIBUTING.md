# Contributing to BreakBPM

Thank you for your interest in BreakBPM! This is a fun, retro Windows 98-style pool scorer built as a single-file web app.

## Development Guidelines

### Core Principles
- **Keep it single-file** — Everything lives in `index.html` for now (HTML + CSS + JS). No build step.
- **Maintain the Windows 98 aesthetic** — Gray 3D buttons, navy title bars, inset/outset borders, MS Sans Serif font, teal background. Do not modernize the UI.
- **Balls as (X) text only** — Use simple `(1)(3)(8)` notation. No emojis or colored circles.
- **Respect game rules** — Ball selector must only show legal/available balls based on team assignment and sunk balls.
- **Ball Return terminal** — Keep the green-on-black readout showing sunk balls in chronological order.

### How to Make Changes
1. Edit `index.html` directly.
2. Test thoroughly in a browser:
   - New Game flow (including team assignment for 8-ball)
   - Ball selection & terminal readout
   - Sharing via URL (state must survive reload)
   - Win conditions (8-ball group clearance, 9-ball on the 9)
   - Practice mode
   - Undo functionality
3. Update `README.md` and `CHANGELOG.md` when adding features.
4. Update `SCHEMA.md` if the data model changes.

### Testing Checklist
- [ ] Game starts with 4-digit code visible
- [ ] Ball selector only shows legal balls
- [ ] Terminal readout updates correctly in order
- [ ] BPM and timer work live
- [ ] Sharing URL works on another tab/device
- [ ] Win modal appears with correct winner

## For Future AIs / Developers

This project was built iteratively in one long conversation. The UI went through several major evolutions (modern → team assignment → proper rules → full Win98 retro).

**Key things to know:**
- The current version (v0.4) is intentionally retro and simplified.
- The goal is fun + satisfying feel over complex features.
- When adding new features, prioritize keeping the classic Windows 98 look and the `(X)` ball system.
- The `SCHEMA.md` file is the source of truth for data model — always keep it in sync.
- Future backend (Firebase/Supabase) should map cleanly to the existing `players` / `games` / `actions` structure.

If you're an AI continuing this project:
- Read `README.md` first for full context.
- Read `SCHEMA.md` for data model.
- Keep changes minimal and focused on the retro experience.
- Always update CHANGELOG.md with clear entries.

## Questions?

Open an issue or contact @ThatOtherZach.

*Let's keep the BreakBPM high.* 🎱