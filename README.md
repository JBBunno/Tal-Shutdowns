# Talison Shutdowns — PalmCrest

One repo for all Talison shutdown dashboards.

| Path | What |
|---|---|
| `dashboard/index.html` | The ONE dashboard page (shared by every site) |
| `config/d1.json` … | Per-dashboard settings: title + API URL |
| `d1/`, `d2/`, `d3/` | Short addresses → `dashboard/?site=dN` (add `?tv=1` for TV mode) |

Backend: one Apps Script project ("TAL-Dashboards-API") serving all sites via `&site=dN`.

## Add a dashboard
1. Add the site to `SITES` in the Apps Script and deploy a new version.
2. Copy `config/d1.json` → `config/d4.json`, change `site` and `title`.
3. Copy the `d1/` folder → `d4/` and change `d1` to `d4` inside `index.html`.

## Change the code
Edit `dashboard/index.html` once — every dashboard picks it up.
