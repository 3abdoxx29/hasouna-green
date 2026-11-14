# Hassouna Green — Earth Intelligence Platform

A standalone React/TypeScript + FastAPI rebuild for NASA Space Apps Challenge: **Field Shift: Adapting Farms with NASA Data**.

## What is included

- Premium responsive dark geospatial UI for global demos.
- Actual 3D rotating Earth visualization using Three.js / React Three Fiber.
- Field explorer, layer controls, NASA data-source registry, climate chart, rotation planner and printable decision report.
- FastAPI backend with `/health`, `/api/fields`, `/api/fields/{id}/observations`, and `/api/data-sources`.
- Original SQLite demonstration data copied from the supplied Hassouna Green prototype.
- Explicit scientific status labels: connected, planned, observed, demo, and data gap.

## Run locally

### Frontend
```bash
cd frontend
npm install
npm run dev
```
Open `http://localhost:5173`.

### Backend
```bash
cd backend
python -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
uvicorn app.main:app --reload --port 8000
```
Open API docs at `http://localhost:8000/docs`.

### Docker Compose
```bash
docker compose up --build
```

## Scientific scope
NASA POWER is represented in the preserved SQLite dataset and the UI labels the connected status. SMAP, GPM/IMERG, Landsat/MODIS/VIIRS, ECOSTRESS and SRTM are intentionally shown as planned integrations until product access, extraction and validation are implemented. Rotation pathways are transparent hypotheses and must be reviewed with local soil measurements and qualified agronomy expertise.

## Next production phase
1. Put NASA adapters behind background jobs and cache responses by field/date.
2. Add verified crop ontology with regional varieties, phenology and water coefficients.
3. Add local lab import and unit validation for salinity, pH and organic matter.
4. Replace SQLite with PostgreSQL/PostGIS for multi-user global field workspaces.
5. Add authentication, audit logs, confidence metadata and reproducible report snapshots.


## Frontend ↔ Backend integration

The frontend now loads fields from FastAPI and requests live climate, soil and crop-suitability analysis for the selected field. Start the API first, then start Vite:

```bash
# terminal 1
cd backend
python -m uvicorn app.main:app --reload --port 8000

# terminal 2
cd frontend
npm install
npm run dev
```

The dashboard shows a green `LIVE API DATA` banner when the API responds. If the API is unavailable, the application stays usable in clearly labelled `DEMO FALLBACK` mode and does not describe fallback values as measurements. The optional frontend API URL can be changed with `VITE_API_URL`.

For the exact change list and validation results, see `docs/TECHNICAL_AUDIT_CONNECTED.md`.
