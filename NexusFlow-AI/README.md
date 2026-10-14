# NexusFlow AI — Smart Traffic Intelligence

A responsive smart-city traffic dashboard prototype with traffic monitoring, congestion forecasting, signal timing recommendations, incident center, emergency corridor planning, and analytics. The frontend includes interactive sample data and the FastAPI backend provides demo endpoints.

> **Important:** This is a working prototype, not a live traffic-control system. Traffic values, map geometry, incidents, emergency routes, and predictions are synthetic/demo content. No real traffic signals or emergency vehicles are controlled. Live feeds, trained forecasting models, secure user authentication, a production database, and cloud deployment must be integrated and validated before operational use.

## Requirements
- Node.js 20+ and npm
- Python 3.10+

## Run the frontend (quick start)
Open a terminal in the `frontend` folder:

```bash
npm install
npm run dev
```

Open the local URL printed by Vite, usually `http://localhost:5173`.

## Run the API (optional, in a second terminal)
From the project root:

### Windows PowerShell
```powershell
cd backend
py -m venv .venv
.\.venv\Scripts\Activate.ps1
python -m pip install -r requirements.txt
uvicorn main:app --reload --port 8000
```

If PowerShell blocks activation, run `Set-ExecutionPolicy -Scope Process -ExecutionPolicy Bypass` in that terminal, then activate again. Alternatively use `py -m pip install -r requirements.txt` without activating and run `py -m uvicorn main:app --reload --port 8000`.

### macOS / Linux
```bash
cd backend
python3 -m venv .venv
source .venv/bin/activate
python -m pip install -r requirements.txt
uvicorn main:app --reload --port 8000
```

API docs: `http://127.0.0.1:8000/docs`

## Demo API endpoints
- `GET /api/health` — health check
- `GET /api/traffic` — synthetic corridor readings
- `POST /api/predict` — transparent baseline forecast
- `GET /api/signals` — signal recommendations

Example request body for `POST /api/predict`:

```json
{
  "road": "Avinashi Road",
  "horizon_minutes": 120,
  "weather": "rain",
  "event_factor": 1.0
}
```

## Main features
- Custom NexusFlow AI logo and favicon; no Lovable branding is included in this new project.
- Responsive dark/light dashboard UI.
- Road congestion search and zone filters.
- Live-style simulated map and traffic KPIs.
- Forecast interaction and recommendation output.
- Signal timing recommendation cards.
- Sample incident center and emergency corridor planning.
- Analytics charts and vehicle mix visualization.
- FastAPI endpoints using NumPy and Pandas, with a transparent baseline forecast formula.

## Planned production integrations
1. Replace synthetic data with authorized traffic sensors/API feeds.
2. Train and validate a time-series congestion model with Scikit-learn (or a suitable time-series framework).
3. Connect PostgreSQL using migrations, environment-based credentials, and access control.
4. Add authentication and role-based access for traffic operators.
5. Connect a routing provider and verified emergency-service workflow.
6. Keep signal control in read-only/recommendation mode until certified hardware, safety checks, and city authorization are in place.
7. Deploy frontend/backend to AWS with monitoring, logging, secrets management, and tests.

## Project layout
```text
NexusFlow-AI/
  frontend/
    public/nexusflow.svg
    src/main.jsx
    src/styles.css
    index.html
    package.json
  backend/
    main.py
    requirements.txt
  .env.example
  README.md
```
