# Regla propuesta: aleatoriedad aislada en backend

**Estado:** propuesta pendiente de validación.

**Alcance:** generación de movimientos mock en `backend/app/routes.py`, incluida `generate_mock_movements()` y `_build_movement()`.

- Para datos reproducibles, usar una instancia local de `random.Random` asociada a la semilla, en vez de modificar el generador global con `random.seed()`.
- Pasar el generador local a las funciones que necesiten aleatoriedad; no mezclar llamadas al módulo global `random` con el generador local.
- Al cambiar la generación, conservar pruebas que verifiquen reproducibilidad y las propiedades relevantes de los movimientos.
