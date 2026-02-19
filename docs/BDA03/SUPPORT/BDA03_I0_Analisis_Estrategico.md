# BDA03_I0 — Análisis Estratégico (prioridades y riesgos)

## Objetivo evaluable
Entregar un flujo completo:
Importación automática → Pandas → Pig (2 cambios + tratamiento) → Spark→Hive (2 tablas) → HQL (2 JOIN).

## Prioridades (por puntos)
1) Pig (2 correcciones + tratamiento) y que deje outputs claros.
2) Spark→Hive: 2 tablas y evidencias (`SHOW TABLES`, `COUNT`).
3) HQL: 2 consultas con JOIN real y outputs visibles.

## Riesgos típicos
- Java incorrecta (no 17).
- Pig falla por rutas/espacios o por STORE.
- Hive no crea tablas por falta de `enableHiveSupport()`.
- Consultas HQL sin JOIN (no valen).

## Estrategia de blindaje
- Cada sección: título → código → outputs → conclusiones con números reales.
- No optimizar: mantener el estilo simple de cuadernos 0301 y 0305.
