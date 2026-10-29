# Arquitectura actual

## Componentes y entry points

- **Frontend:** React + TypeScript + Vite. `frontend/index.html` carga `frontend/src/main.tsx`, que monta `frontend/src/App.tsx`.
- **Dashboard:** `App.tsx` solicita `GET /api/metrics`, mantiene estados de carga/error y calcula KPI y series mensuales usando `frontend/src/lib/financial-utils.ts`. Los componentes de pantalla están bajo `frontend/src/components/dashboard/`.
- **Backend:** FastAPI. `backend/app/main.py` crea `app`, configura CORS e incluye el router de `backend/app/routes.py`. Los modelos, endpoints, datos simulados y cálculos de métricas están actualmente en `routes.py`.
- **Pruebas:** backend en `backend/tests/`; frontend usa Vitest y tiene pruebas de utilidades en `frontend/src/lib/financial-utils.test.ts`.

## Ejecución y comunicación

- `docker-compose.yml` inicia el frontend en el puerto `5173` y el backend en `8000`; `5678` se publica para `debugpy`.
- El proxy de `frontend/vite.config.ts` reenvía `/api` a `http://backend:8000`, nombre de servicio de Compose. Fuera de Compose, el frontend puede apuntar a otro origen mediante `VITE_API_BASE_URL`.
- El backend expone `/health` y endpoints bajo `/api/metrics`, incluida la lista de movimientos, facets, summary, top categories, comparison, alerts y rutas B2B/B2C. La UI actual consume `/api/metrics`.

## Datos actuales

- La API genera movimientos simulados en cada solicitud y no usa una base de datos.
- La generación recibe semilla `42`, pero calcula el año con la fecha actual.
- La UI calcula KPI y agregados mensuales en el cliente a partir de los movimientos que recibe.

Este documento describe el estado observado; no prescribe una arquitectura futura.
