# Claims de producto y roadmap

## Política

No presentar como capacidad del producto algo que no esté respaldado por el código, pruebas, documentación vigente o una decisión explícitamente aprobada. No inventar roadmaps, fechas, prioridades, compromisos ni funcionalidades futuras.

## Cómo describir capacidades

- **Implementado:** afirmar que una función está disponible solo si la implementación actual la realiza. Citar el archivo, endpoint o flujo que la soporta cuando se documente o comunique.
- **Expuesto no integrado:** un endpoint disponible en backend no implica que la interfaz lo utilice ni que sea una función accesible para usuarios.
- **Propuesta:** marcar explícitamente como propuesta cualquier solución o funcionalidad que no esté implementada y aprobada. No describirla como compromiso.
- **Pendiente o desconocido:** si no hay evidencia suficiente, indicarlo como pendiente/desconocido o solicitar aclaración; no completar los huecos con suposiciones.

## Roadmaps y decisiones

- Incluir en un roadmap únicamente trabajo respaldado por una solicitud o decisión aprobada y registrada.
- No asignar fechas, prioridad, alcance comprometido ni estado de entrega si no existe una fuente explícita.
- Mantener los hallazgos de `open-findings.md` como observaciones y decisiones abiertas; no convertirlos automáticamente en roadmap.
- Las reglas de `.agents/rules/` y las skills de `.agents/skills/` guían a agentes y contribuidores; por sí mismas no demuestran que una función exista en el producto.

## Comprobaciones antes de publicar un claim

1. Identificar la afirmación concreta y si describe estado actual o trabajo futuro.
2. Verificar el código y las pruebas pertinentes; usar documentación aprobada para respaldar decisiones y compromisos.
3. Comprobar la diferencia entre endpoint backend, consumo real desde frontend y experiencia disponible para usuarios.
4. Si la evidencia no alcanza, reducir el alcance de la afirmación o etiquetarla como propuesta/pendiente.
