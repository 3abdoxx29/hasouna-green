# Hassouna Green — Independent rebuild plan

## Product direction
A global-facing scientific decision-support workspace for Field Shift. The UI intentionally distinguishes observations, planned integrations, estimates and open questions.

## Design
- Movement: dark geospatial intelligence / quiet luxury SaaS.
- Principles: calm hierarchy, scientific transparency, field-first workflows, restrained motion.
- Palette: deep forest as the canvas, signal green for connected evidence, lime for actions, blue/amber for environmental signals.
- Layout: editorial dashboard with a persistent rail, asymmetrical hero and large interactive earth visualization rather than generic centered cards.
- Signature elements: rotating wireframe earth, field-signal labels, evidence/status chips.
- Typography: Manrope for a compact global product feel; DM Sans fallback for utility copy.
- Brand essence: earth intelligence that makes rotation decisions explainable. Calm, credible, practical.

## Architecture
- `frontend/`: Vite + React + TypeScript, Three.js/R3F globe, responsive dashboard routes represented by stateful navigation, charts and maps.
- `backend/`: FastAPI service with SQLite adapter and resource-oriented endpoints for fields, observations, sources and health.
- `data/`: existing SQLite demonstration dataset copied from the user's prototype.
- Future adapters: NASA POWER, SMAP, GPM/IMERG, Landsat/MODIS/VIIRS, ECOSTRESS, SRTM, local lab imports.

## Scientific guardrails
Every non-integrated source is labeled Planned. Rotation narratives are hypotheses, not validated yield scores. The report repeats the expert-review disclaimer.
