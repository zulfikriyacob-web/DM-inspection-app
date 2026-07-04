# Door Mirror Inspection App

Mobile-first digital inspection platform for factory floor — converting paper-based job setup check sheets (PGE-GE-001-C) into a live, auditable digital workflow.

**Owner:** Zul Fikri Yacob — Sr. Manufacturing Quality Engineer, Armstrong Auto Parts Sdn. Bhd.
**Line:** L2 Door Mirror
**Target compliance:** IATF 16949, ISO 9001

---

## Status

| Phase | Status |
|---|---|
| Phase 1 — Data structure | ✅ Done (Google Sheets schema) |
| Phase 2 — App skeleton (Dashboard, Check Sheet, History) | 🚧 In progress |
| Phase 3 — Google Sheets API integration | ⏳ Pending |
| Phase 4 — Additional tabs (Reports, Action Items, Master Data Admin) | ⏳ Pending |
| Phase 5 — PWA / offline / installable | ⏳ Pending |
| Phase 6 — Authentication (Google OAuth) | ⏳ Pending |

---

## Tech stack

- **Frontend:** Vanilla HTML / CSS / JavaScript (no build step)
- **Backend:** Google Sheets (via Google Sheets API — *coming Phase 3*)
- **Hosting:** GitHub Pages (free)
- **Auth:** Google OAuth — *coming Phase 6*

---

## Project structure

```
inspection-app/
├── index.html                       # The app (self-contained)
├── README.md                        # You are here
└── data-reference/
    └── Inspection_App_DataSheet_v2.xlsx   # Master data sheet (upload to Google Sheets)
```

For now everything lives in `index.html`. As the app grows we'll split into:

```
inspection-app/
├── index.html
├── assets/
│   ├── css/styles.css
│   └── js/
│       ├── app.js              # Router + state
│       ├── data.js             # Google Sheets API layer
│       └── views/
│           ├── dashboard.js
│           ├── fill-check-sheet.js
│           └── history.js
```

---

## How to run locally

1. Clone the repo
2. Open `index.html` in any browser
3. (Optional) For phone testing, use any simple static server:
   ```bash
   python3 -m http.server 8000
   ```
   Then open `http://<your-laptop-IP>:8000` on your phone (same WiFi).

---

## How to deploy to GitHub Pages

1. Push this repo to GitHub
2. Go to **Settings → Pages**
3. Source: `main` branch, root folder
4. Save — your app is live at `https://<username>.github.io/<repo-name>/`

---

## Data model

See `data-reference/Inspection_App_DataSheet_v2.xlsx` for the full schema. Quick overview:

```
Master data:
  Templates ──< Processes ──< ControlItems ──< ModelSpecs
  Models ──< ModelSpecs
  Users

Planning:
  ProductionPlan (daily schedule by line/shift/model/sides/qty)

Transactional:
  Inspections (auto-generated from ProductionPlan: 1 per model×side)
  Results (per check item, per inspection)
```

### How a day flows through the app

1. Production Leader fills the **Dashboard** form: date, line, shift, model, sides, target qty
2. App creates a `ProductionPlan` record and auto-generates `Inspections` (e.g. T20 with sides `RH-L, RH-R` = 2 inspections)
3. Operator opens **Check Sheet** tab, picks the inspection, fills each control item — standards are auto-populated based on model
4. NG triggers `ACTION NEEDED` status; submitted inspections show in **History**

---

## Roadmap notes

- **Phase 3 (Google Sheets API):** Replace the `DB` object in `index.html` with API calls. Read-only first, then write.
- **Phase 4 (additional tabs):** Reports / Analytics (Pareto, KPI), Action Items (8D follow-up), Master Data Admin (QE-only).
- **Phase 5 (PWA):** Add `manifest.json` + service worker for offline-capable, installable experience on the factory floor.
- **Phase 6 (Auth):** Google OAuth so each PIC entry is tied to a verified user.

---

## License

Internal use — Armstrong Auto Parts Sdn. Bhd.
