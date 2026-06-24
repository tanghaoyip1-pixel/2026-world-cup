# ⚽ 2026 FIFA World Cup — Road to Knockout

A single-file static website tracking the **2026 FIFA World Cup** group stage, knockout bracket, and player statistics. Built with pure HTML, CSS, and JavaScript — no frameworks, no build tools, no dependencies.

**Live site:** [tanghaoyip1-pixel.github.io/2026-world-cup](https://tanghaoyip1-pixel.github.io/2026-world-cup/)

## Features

### 📊 Group Standings
- All 12 groups (A–L) with 48 teams
- Sort by points → goal difference → goals scored
- Top 2 highlighted in gold as knockout qualifiers
- Click any group for: full table, match history, and goal scorers

### 🏟 Knockout Bracket
- Round of 32 → Round of 16 → Quarterfinals → Semifinals → Final
- Qualified teams auto-filled into their bracket slots
- Visual tree layout with flags and scores

### 📈 Stats Leaderboards
- **Top Scorers** — goal count, player name, team flag
- **Top Assists** — assist count with source match data
- **Yellow Cards / Red Cards** — discipline records

### 🔄 Live Data
- **Manual refresh** — green button in the top-right corner
- **Auto-refresh** — silently updates every 30 minutes
- Data fetched live from ESPN public API (no API key required)

## Data Sources

| Source | What | Speed |
|--------|------|-------|
| [ESPN API](https://site.api.espn.com/apis/site/v2/sports/soccer/fifa.world) | Match results, goals, assists, cards | ⚡ Fast (global CDN, CORS enabled) |
| [worldcup26.ir](https://worldcup26.ir) | Team names, group structure, scorers (backup) | 🐢 Slower (fallback only) |

Team market values from [Transfermarkt](https://www.transfermarkt.com) (static, updated periodically).

## Tech Stack

| Layer | Technology |
|-------|------------|
| Structure | HTML5 |
| Styling | CSS3 (custom properties, grid, animations, responsive) |
| Logic | Vanilla JavaScript (fetch API, localStorage caching, ES modules-free) |

## How It Works

1. **Instant load:** Pre-bundled match data renders immediately — no network wait
2. **Background sync:** Fetches latest ESPN results (dual-source race with 6s timeout)
3. **Client-side compute:** Standings calculated from match results in the browser
4. **Local cache:** 5-minute TTL for matches; versioned cache for stats
5. **Auto-refresh:** Silent background refresh every 30 minutes

## Run Locally

Double-click `index.html` to open in any browser, or serve with Python:

```bash
python3 -m http.server 8080
# Open http://localhost:8080
```

## Deploy

This site is deployed via **GitHub Pages** on the `main` branch. To fork and deploy your own:

1. Fork this repo
2. Go to **Settings → Pages**
3. Set source to `main` branch, root (`/`)
4. Your site will be live at `https://<your-username>.github.io/2026-world-cup/`

## Project Structure

```
.
├── index.html      # The entire website (HTML + CSS + JS)
├── haaland.png     # Decorative watermark image
├── README.md       # You're reading it
└── .gitignore
```

## License

MIT — free to use, modify, and share.
