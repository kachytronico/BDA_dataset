# ENUNCIADO — BDA03 Tarea de Evaluación
## Ecosistema Hadoop–Spark (proceso completo ETL)

> **Este enunciado está formateado para que tus agentes (Copilot/Gemini) respeten la numeración REAL del profesor.**  
> La explicación del dataset **NO es el punto 1**: es un requisito previo “fuera” de la lista numerada 1–5.

---

## Contexto general
Vamos a realizar un ejercicio que cubra el proceso completo de tratamiento de datos:
importación → exploración → limpieza → carga en Hive → consultas HQL con JOIN.

**Dataset:** recupera los conjuntos de datos que usaste en **BDA01 — Tarea de Evaluación** (Kaggle u otro repositorio).

---

# ✅ Lo que debes entregar en el cuaderno (estructura correcta)

## A) Explicación del conjunto de datos (va ANTES de la lista 1–5)
En el notebook debe aparecer **primero** un bloque explicativo con:

- **Temática:** de qué trata el dataset.
- **Tamaño:** nº de filas/columnas y/o tamaño en MB por archivo.
- **Relación:** con qué campos se relacionan los archivos/tablas (clave de unión).
- **Interés:** por qué es un dataset interesante para ETL/análisis.

> **Evidencia mínima recomendada:** `shape`, `head(3)` y una frase justificando la clave de relación.

---

## B) Una vez quede claro el contexto: pasos 1–5 (numeración del profesor)

### 1. Importación automática (Kaggle u otro repositorio)
Importa de manera automática tus conjuntos de datos desde Kaggle u otro repositorio.
Pista: puedes usar `kaggle`, `opendatasets` u otras opciones; también `sqoop` si aplica por origen.

> **Evidencia mínima recomendada:** comando de descarga/clonado + `ls -lh` mostrando archivos presentes y tamaño > 0.

---

### 2. Exploración inicial con Pandas
Usa Pandas para una primera visualización en forma de tabla y estudiar los datos:
- valores nulos,
- fechas con formatos incorrectos,
- campos vacíos,
- otros problemas de calidad.

> **Importante:** aquí debes **identificar problemas reales** que luego corregirás en el paso 3 (Pig).

---

### 3. Apache Pig
Usa Apache Pig para:

**3.1 Corregir fallos detectados en Pandas**  
- Debes **modificar al menos 2 campos** (ej.: cambiar formato de fechas, rellenar vacíos/nulos con valores por defecto, normalizar claves, reemplazar códigos de missing como `-9`, etc.).

**3.2 Tratamiento de datos “interesante”**  
- Por ejemplo: encontrar las 3 palabras más repetidas en ambos archivos (o una alternativa equivalente que tenga sentido con tu dataset).

> **Evidencia mínima recomendada:** script `.pig` visible + ejecución `pig` + muestra del output y explicación breve.

---

### 4. Spark (PySpark) → Hive
Usa Spark (PySpark) para importar tus ficheros a una base de datos relacional Hive.

> **Evidencia mínima recomendada:** creación/guardado de tablas Hive y una consulta simple de verificación (p.ej. `show tables`, `select count(*)`).

---

### 5. Consultas HQL (mínimo 2) con JOIN entre dos tablas
Realiza al menos **dos consultas HQL** que impliquen **dos tablas** (JOIN real), no solo consultas sobre una única tabla.

> **Evidencia mínima recomendada:** dos queries con `JOIN` + salida con resultados.

---

# Criterios de calificación (0 a 10)
- **1 punto:** Explicación del dataset (sección A)
- **1 punto:** Paso 1
- **3 puntos:** Paso 2 y Paso 3 (según rúbrica del profesor)
- **2 puntos:** Paso 4
- **3 puntos:** Paso 5 (1,5 por consulta)

---

# Indicaciones de entrega (resumen)
- Entregar **un único archivo** (.zip/.7z/.rar) con el convenio de nombre `<iniciales><unidad>`, por ejemplo `JGR01.zip`.
- Si hay varios archivos/notebooks/scripts, meterlos en **una carpeta sin subcarpetas** y comprimir.
- Fuera de plazo: “no apta” / “0” según tipo de tarea.
- Copia total/parcial: “no apta” / “0”.

