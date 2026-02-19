# BDA03 — Debug Guide (Colab: Pig / Spark / Hive)

## 1) Java 17
**Síntoma:** Pig/Hadoop/Spark fallan por Java.
- Ejecuta: `java -version` y verifica que sea **17**.
- Si no: instala `openjdk-17-jdk-headless` y ajusta `JAVA_HOME`.

## 2) Rutas con espacios
**Síntoma:** “No such file” al cargar CSV/XLSX.
- Si la carpeta tiene espacios (p.ej. `Dataset not incorporated...`):
  - Usa rutas entre comillas.
  - Evita concatenaciones raras; imprime la ruta antes de usarla.

## 3) Pig no genera salida
**Síntoma:** carpeta `pig_out/...` no aparece o está vacía.
- Revisa el log: `cat pig_err.log | tail -n 50`
- Asegúrate de:
  - `STORE ... INTO '/content/data/pig_out/...';`
  - `rmf` antes del STORE (si re-ejecutas).
  - Que el `LOAD` apunte al CSV correcto.

## 4) Pig ERROR 2244 / fallos en DUMP
**Causa típica:** estás usando `DUMP` sobre un alias que no existe o no se calculó.
- Solución simple:
  - Separa en 2 scripts: `limpieza.pig` y `tratamiento_top3_race.pig`.
  - Ejecuta primero limpieza y luego tratamiento.

## 5) CSV y delimitadores
**Síntoma:** columnas “corridas” o conteos raros.
- Asegura `PigStorage(',')` si el CSV es coma.
- Si hay comas dentro de texto, Pig puede romper (caso raro). Mantén el caso simple.

## 6) Hive/Spark
**Síntoma:** no se crean tablas en Hive.
- Usa `SparkSession.builder.enableHiveSupport()`.
- Muestra evidencia:
  - `spark.sql("SHOW TABLES").show()`
  - `spark.sql("SELECT COUNT(*) FROM tabla_survey").show()`

## 7) AVG sobre columnas string
**Síntoma:** error o AVG incorrecto.
- Haz cast: `AVG(CAST(GRS AS DOUBLE))` (solo si lo necesitas y el output lo muestra).
