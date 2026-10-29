# Hallazgos abiertos

Estos son comportamientos observados en el código actual. No representan decisiones aprobadas ni correcciones ya implementadas.

| Área | Observación concreta | Estado |
|---|---|---|
| Período visible | `frontend/src/App.tsx` pasa el texto fijo `2024 - Full Year` al encabezado; `backend/app/routes.py` asigna años a los movimientos a partir de `date.today()`. | Pendiente de acordar período fijo o dinámico. |
| Aleatoriedad | `generate_mock_movements()` llama a `random.seed(42)` en `backend/app/routes.py`, lo que modifica el generador global del proceso. | No aislado en un generador local. |
| Endpoints no consumidos por la UI | `backend/app/routes.py` expone facets, summary, top categories, comparison, alerts y B2B/B2C; `frontend/src/App.tsx` solo solicita `/api/metrics`. | Uso futuro o estado de esos endpoints por decidir; no implica que deban eliminarse. |
| Contratos duplicados | El modelo Pydantic `FinancialMovement` está en `backend/app/routes.py`; los tipos TypeScript correspondientes están en `frontend/src/lib/financial-types.ts`. | Sin generación o sincronización automática observada. |
| Proxy de desarrollo | `frontend/vite.config.ts` apunta a `http://backend:8000`, hostname configurado por Compose en `docker-compose.yml`. | Ejecución de Vite fuera de Compose puede requerir `VITE_API_BASE_URL`. |
| CORS | `backend/app/main.py` configura `allow_origins=["*"]` y `allow_credentials=True`. | Revisar orígenes permitidos antes de exponer la API en otros entornos. |

## Decisiones que faltan

- Definir si el período del dashboard representa un rango fijo o deriva de los datos consultados.
- Decidir si se mantiene el contrato frontend/backend manual o se adopta una estrategia de generación/sincronización.
- Definir orígenes permitidos por entorno antes de endurecer CORS.
- Confirmar el uso esperado de los endpoints que todavía no consume la interfaz.
