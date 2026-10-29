# Regla propuesta: configuración CORS

**Estado:** propuesta pendiente de validación.

**Alcance:** middleware CORS y creación de la aplicación en `backend/app/main.py`.

- No combinar `allow_origins=["*"]` con `allow_credentials=True`.
- Cuando se habiliten credenciales, enumerar los orígenes permitidos explícitamente.
- Mantener la lista de orígenes alineada con los entornos que realmente ejecutan el frontend; no añadir dominios de producción hipotéticos.
- Al modificar CORS, verificar una petición desde el origen permitido y otra desde un origen no permitido.
