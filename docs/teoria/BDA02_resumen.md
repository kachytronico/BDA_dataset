# BDA02 — Resumen operativo (Hadoop: HDFS, YARN, MapReduce)

## Qué pide la unidad
Dominar almacenamiento distribuido (HDFS), ejecución de aplicaciones (YARN) y procesamiento (MapReduce).

## HDFS (comandos esenciales)
- Crear directorios: `hadoop fs -mkdir -p /ruta`
- Listar: `hadoop fs -ls /ruta` (o `-R` recursivo)
- Subir (local -> HDFS): `hadoop fs -put fichero_local /ruta_hdfs`
- Ver contenido: `hadoop fs -cat /ruta_hdfs/fichero`
- Copiar dentro de HDFS: `hadoop fs -cp origen destino`
- Borrar: `hadoop fs -rm -R /ruta`
- Mover: `hadoop fs -mv origen destino`

**Ojo**: “local” y “HDFS” no son lo mismo. `hadoop fs ...` siempre opera contra HDFS.

## YARN
Gestor de recursos del clúster. Permite ejecutar frameworks (MapReduce/Spark/etc.) compartiendo recursos.

## MapReduce (idea)
- MAP: tokeniza/transforma y emite (clave,1)
- SHUFFLE/SORT: agrupa por clave (automático)
- REDUCE: suma y emite (clave,total)

## Para la tarea BDA02
- grep + conclusiones
- wordcount con MapReduce (Java)
- wordcount con Hadoop Streaming (Python)
