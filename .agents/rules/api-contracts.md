# Regla propuesta: contratos de la API

**Estado:** propuesta pendiente de validación.

**Alcance:** modelos Pydantic y endpoints en `backend/app/routes.py`; tipos TypeScript y consumidores bajo `frontend/src/`.

- Al cambiar campos, valores permitidos o semántica de una respuesta, revisar el modelo Pydantic, el tipo TypeScript correspondiente y todos los consumidores del endpoint.
- Mantener los valores de enums y la forma serializada compatibles entre backend y frontend.
- Añadir o actualizar pruebas enfocadas al contrato y al comportamiento que cambió.
- No introducir una estrategia de generación de tipos ni una estructura compartida nueva sin acordar esa decisión primero.
