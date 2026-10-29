---
name: review-api-contract
description: 'Use when changing FastAPI routes, Pydantic response models, query parameters, TypeScript API types, or frontend consumers of the financial API.'
---

# Review API Contract

Revisa los cambios del contrato entre FastAPI y el frontend sin asumir una estrategia de generación de tipos.

## Procedimiento

1. Identifica el endpoint afectado en `backend/app/routes.py`, su modelo Pydantic, parámetros y valores permitidos.
2. Localiza los tipos correspondientes en `frontend/src/lib/financial-types.ts` y todos los consumidores en `frontend/src/`.
3. Compara nombres, tipos, valores de enums, nulabilidad, formato de fechas y significado de los campos.
4. Actualiza los modelos, tipos y consumidores afectados de forma coordinada; conserva compatibilidad o describe claramente el cambio de contrato.
5. Añade o ajusta pruebas enfocadas al comportamiento cambiado: consulta `backend/tests/test_routes.py` para API y los tests frontend pertinentes para cálculos/consumidores.
6. Ejecuta las verificaciones relevantes y comunica cualquier aspecto del contrato que siga sin cobertura.

## Límites

- No declares obsoleto un endpoint solo porque actualmente no lo consuma la pantalla principal.
- No introduzcas generación OpenAPI, paquetes compartidos ni herramientas de sincronización de tipos sin una decisión explícita del proyecto.
