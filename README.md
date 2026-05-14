# 🎱 Don't Break the BPM

**A fun, real-time(ish) web app for pool & billiards scoring.** Track every shot, measure your **Balls Per Minute (BPM)**, play casual games with up to 4 friends via shareable links, or grind solo practice mode.

> *"Don't break the beat... or the rack."*

## ✨ Features (MVP)

- **Multiplayer up to 4 players** – Instant shareable link (URL-encoded state for now; true realtime coming soon)
- **Shot-by-shot tracking** – Potted ball, Miss, Foul, Safety, Win Rack / 8-Ball
- **Live Balls-Per-Minute (BPM)** – Global + per-session stats with timer
- **Practice mode** – Solo drills, high-run tracking, pace training
- **Game types** – 8-ball, 9-ball, custom race-to-X racks
- **Beautiful mobile-first UI** – Felt-green theme, big friendly buttons, confetti wins
- **Zero install** – Works in any browser, PWA-ready

## 🚀 Live Demo

Open `index.html` directly in your browser (or deploy to GitHub Pages / Vercel). Share the URL after starting a game – the full state travels with it!

## 📁 Project Structure

- `index.html` – The entire playable app (single-file magic with Tailwind + vanilla JS)
- `README.md` – You're here

## 🔧 Tech Stack & Roadmap

**Current (v0.1):** Pure HTML + Tailwind CDN + JS (no build step)

**Next up:**
- Firebase / Supabase for real-time synced game rooms (join via code, live updates for all players)
- Persistent history & player profiles
- Payment integration (Stripe / crypto per-game credits as originally planned)
- Advanced analytics (shot heatmaps, improvement graphs)
- Deployed PWA + install prompt

## 🎯 How to Play (Quick Start)

1. Open `index.html`
2. Click **New Game** or **Practice Mode**
3. Add player names (1–4)
4. Choose race length & game type
5. Start shooting! Use the big action buttons
6. Watch BPM climb in real time
7. Hit **Share Link** to send to friends – they open it and see the live state
8. First to the target racks wins → confetti explosion!

## 👨‍💻 Local Development

Just open the HTML file. No server needed. For editing, use any text editor + live server extension.

## 🎉 Credits & Vibes

Built live in one session with Grok (xAI) + connected GitHub tools. Inspired by late-night pool hall sessions and the need for something better than chalkboards or group texts.

**Repo:** https://github.com/ThatOtherZach/dont-break-the-bpm

*Let's rack 'em up and keep the BPM high.* 🎱
