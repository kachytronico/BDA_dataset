# BDA03_I7 — Guía del Tutor (solo pasos/avisos/errores frecuentes)

## Qué valora el profesor
- Que sea **reproducible** (importación automática).
- Que haya **evidencias visibles** en el notebook.
- Que Pig haga **mínimo 2 cambios** justificables.
- Que HQL tenga **2 consultas con JOIN real** (2 tablas).

## Errores frecuentes
- “Limpio datos” pero no enseño el output limpio (`head` del resultado Pig).
- Tratamiento Pig sin `DUMP` visible.
- Crear una sola tabla en Hive y luego hacer SQL sin JOIN.
- Conclusiones con números inventados.

## Recomendación práctica
- Separar Pig en 2 scripts si da problemas: limpieza por un lado y tratamiento por otro.
- En HQL: escribir JOIN explícito en las dos consultas aunque el análisis “salga” de una sola tabla.
