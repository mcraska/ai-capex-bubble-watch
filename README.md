# AI Capex Bubble Watch

Public dashboard for Matt’s AI Capex Bubble Watch: scored leading indicators of AI data-center capex stress.

**Live:** https://mcraska.github.io/ai-capex-bubble-watch/

**As of:** 2026-10-23 · **Composite:** 49.2 **AMBER** (0.8 pt under RED) · 6R / 13A / 9G

Inform only. No trades. Not investment advice.

## What it shows

1. **Key takeaway** first (from the standing state file)
2. Hero KPIs: composite, band, points/weight, R/A/G, nearest flip, day-over-day
3. Bucket cards A–E with one-line reads
4. Composite history sparkline (dated score JSON)
5. Filterable indicator table
6. Pattern meaning, next decisive prints, methodology
7. Footer: inform only / no trades

## Files

```
dashboard/
├── index.html                 # Single-page dark dashboard (Chart.js CDN)
├── data/
│   ├── latest.json            # Current score + indicators + copy
│   └── history.json           # Dated composite series
├── .github/workflows/pages.yml
└── README.md
```

## How to refresh

Authoritative sources on the box (do not invent numbers):

- State: `/workspace/briefs/state/ai-capex-bubble-watch.md`
- Score JSON: `/workspace/briefs/state/assets/ai-capex-bubble-watch-score-YYYY-MM-DD.json`
- Score script (indicator rows): `/workspace/briefs/state/assets/ai-capex-bubble-watch-score.py`

After a mosaic / score refresh:

1. Re-run or copy the latest score JSON into `data/latest.json` (keep the enriched fields: `key_takeaway`, `indicators`, `buckets`, `dod`, etc.).
2. Append / rebuild `data/history.json` from all dated score files.
3. Update the as-of line in this README.
4. Commit and push to `master` — GitHub Pages deploys from the repo root.

Bands: GREEN &lt; 25 · AMBER 25–49 · RED ≥ 50.

## Local preview

```bash
cd /workspace/research/bubble-watch/dashboard
python3 -m http.server 8080
# open http://localhost:8080
```

## License

Use, modify, and share freely for personal monitoring. No warranty.
