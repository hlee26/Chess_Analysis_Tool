# ♟ Chess Improver

A single-file web app that pulls your rapid game history from the chess.com public API and tells you exactly where you're losing ELO — and how to fix it.

**No login. No backend. No dependencies to install.** Just open the HTML file.

---

## Features

| Section | What it shows |
|---|---|
| 📈 Rating Progression | Your ELO arc over the last 6 months |
| 🏆 Results Breakdown | Win / Draw / Loss split with percentages |
| ♟ Opening Performance | Win rate for every opening you've played ≥3 times |
| 🎯 Accuracy Trend | Game-by-game accuracy for your last 30 games (color-coded by result) |
| ⚪⚫ Color Performance | White vs Black win rates side by side |
| 🧭 Game Phase Analysis | Which phase — opening, middlegame, or endgame — your losses cluster in |
| 💡 Personalized Insights | Up to 6 prioritized study recommendations based on your actual data |

---

## Usage

### Option 1 — Open locally
1. Download `chess_improver.html`
2. Open it in Chrome (recommended) or Firefox
3. Type your chess.com username and click **Analyze My Games →**

### Option 2 — Direct link (when hosted)
Append `#username` to the URL to skip the input screen:
```
https://yourdomain.com/chess_improver.html#hikaru
```

### Option 3 — GitHub Pages (free hosting)
See the [Deploy to GitHub Pages](#deploy-to-github-pages) section below.

---

## Notes

- **Rapid games only** — blitz and bullet are filtered out automatically
- **Last 6 months** of games are analyzed
- **Accuracy data** requires running chess.com's Game Review feature on your games; without it the accuracy chart will be hidden
- The app uses the [chess.com public API](https://www.chess.com/news/view/published-data-api) — no API key required

---

## Deploy to GitHub Pages

1. Push this repo to GitHub (see setup instructions below)
2. Go to your repo → **Settings → Pages**
3. Under *Source*, select **Deploy from a branch** → `main` → `/ (root)`
4. Click Save — your site will be live at `https://<your-username>.github.io/<repo-name>/chess_improver.html`

---

## Setup — pushing to GitHub for the first time

```bash
# 1. Create a new repo on github.com first, then:
git init
git add chess_improver.html README.md
git commit -m "Initial commit: chess improver app"
git branch -M main
git remote add origin https://github.com/YOUR_USERNAME/YOUR_REPO.git
git push -u origin main
```

---

## Tech

- Vanilla HTML / CSS / JavaScript — zero build step
- [Chart.js 4.4](https://www.chartjs.org/) for charts (loaded from CDN)
- [chess.com Public API](https://www.chess.com/news/view/published-data-api)
