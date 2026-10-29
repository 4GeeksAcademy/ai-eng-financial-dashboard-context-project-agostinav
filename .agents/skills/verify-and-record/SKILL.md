---
name: verify-and-record
description: 'Use after a code or documentation change to choose focused project checks and record their actual commands and outcomes in verifications.md.'
---

# Verify and Record

Ejecuta verificaciones proporcionales al cambio y registra resultados observados en `verifications.md`.

## Procedimiento

1. Identifica los archivos y el comportamiento que cambió; consulta los scripts disponibles en `frontend/package.json` y las pruebas existentes en `backend/tests/` o `frontend/src/`.
2. Elige el chequeo ejecutable más acotado que pueda detectar una regresión relevante. Para cambios de API, usa el test backend relacionado; para cálculos frontend, el test de utilidades pertinente. Para cambios solo documentales, valida archivos y formato sin ejecutar tests de aplicación.
3. Ejecuta el chequeo y espera a que termine. Registra el comando exacto, su resultado y cualquier limitación; un comando no ejecutado no cuenta como aprobado.
4. Añade una entrada en la sección `Entrada` de la raíz `verifications.md`, rellenando alcance, comando/procedimiento, resultado y observaciones.
5. Distingue entre `Correcto`, `Fallido` y `Pendiente`; no conviertas advertencias, fallos ni verificaciones omitidas en un resultado correcto.

## Límites

- No ejecutes la suite completa cuando un test focalizado cubra el cambio.
- No incluyas credenciales, tokens ni otros secretos en comandos o registros.
- No alteres código para hacer pasar un chequeo fuera del alcance solicitado.
