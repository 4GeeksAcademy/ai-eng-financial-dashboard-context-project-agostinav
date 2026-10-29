# Regla propuesta: consistencia del período

**Estado:** propuesta pendiente de validación.

**Alcance:** `frontend/src/App.tsx`, `frontend/src/components/dashboard/dashboard-header.tsx` y la generación/filtrado de fechas en `backend/app/routes.py`.

- El período que muestra el dashboard debe corresponder al conjunto de datos cargado; no debe quedar fijado a un año distinto del devuelto por la API.
- Si cambia la generación, el filtrado o la consulta por fechas, revisar también el período mostrado y las pruebas relacionadas.
- No asumir que la semilla fija de los movimientos implica un año fijo: `backend/app/routes.py` usa la fecha actual para asignar el año.
- Mantener explícita la decisión de producto sobre si el período es fijo o dinámico; no introducir un selector de fechas ni cambiar la fuente de datos como parte incidental de un ajuste visual.
