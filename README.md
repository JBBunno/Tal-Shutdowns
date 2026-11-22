# Talison Shutdowns — PalmCrest

One repo for all Talison shutdown dashboards.

| Path | What |
|---|---|
| `dashboard/index.html` | The ONE dashboard page (shared by every site) |
| `config/d1.json` … | Per-dashboard settings: title + API URL |
| `gantt/index.html` | The ONE online Gantt page (shared by every site) |
| `upload/index.html` | Schedule Data Upload panel (one card per site, from `config/client.json`) |
| `config/client.json` | Client name, API URL and the list of sites |
| `d1/`, `d2/`, `d3/` | Short addresses → `dashboard/?site=dN` (add `?tv=1` for TV mode) |
| `d1/gantt/` … | Short addresses → `gantt/?site=dN` |

Backend: one Apps Script project ("TAL-Dashboards-API") serving all sites via `&site=dN`.

## Add a dashboard
1. Add the site to `SITES` in the Apps Script and deploy a new version.
2. Copy `config/d1.json` → `config/d4.json`, change `site` and `title`, and add the site to `config/client.json`.
3. Copy the `d1/` folder → `d4/` and change `d1` to `d4` inside `index.html` and `gantt/index.html`.

## Change the code
Edit `dashboard/index.html` or `gantt/index.html` once — every site picks it up.

The Gantt reads the Tasks tab through the backend (`action=taskscsv`), so the Google Sheets don't need public sharing.
