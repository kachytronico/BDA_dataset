# REFERENCIA_ESTILO_CUADERNOS_BDA03

## Cuadernos que se deben imitar obligatoriamente
- `BDA03_cuadernos/0301_Apache_Pig.ipynb` (Pig)
- `BDA03_cuadernos/0305_Importación_de_datos_en_Hive_utilizando_PySpark.ipynb` (Spark + Hive + HQL)

## Qué significa “estilo profesor”
- Implementación simple y directa.
- Mismas secciones que en los cuadernos de referencia.
- Mismas llamadas principales y mismo orden operativo.
- Priorizar evidencia evaluable sobre variaciones personales.

## Patrones a replicar
- **Pig**: `%%writefile` + `!pig`, flujo `LOAD` / `FOREACH` / `STORE`, y manejo explícito de nulos y `-9` como missing.
- **Spark**: `SparkSession` con `enableHiveSupport`, lectura con `read.csv`, escritura con `write.saveAsTable`.
- **HQL**: uso de `spark.sql` con `JOIN` real entre dos tablas.

## Regla de alcance
- No usar patrones avanzados si no aparecen en los cuadernos `0301` y `0305`.

## Reglas fijas que se mantienen
- Java 17 obligatorio.
- Dataset T1D Guertin 2024.
- `-9` representa missing.
- En HQL: mínimo 2 consultas y cada una con `JOIN` real.