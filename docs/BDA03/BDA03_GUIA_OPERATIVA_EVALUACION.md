# BDA03 — Guía Operativa de Evaluación (Hadoop · Pig · Spark · Hive)

Objetivo: traducir el enunciado a acciones técnicas claras, con **evidencia mínima** por apartado,
para maximizar nota y reducir riesgo.

---

## 0) Prioridad de fuentes
1. Enunciado oficial
2. Tutorías del profesor
3. Cuadernos de ejemplo de BDA03
4. Teoría / resúmenes

---

## 1) Estructura recomendada del notebook (evaluable)
- **Apartado 1 — Dataset (1 p)**
- **Apartado 2 — Importación automática (1 p)**
- **Apartado 3 — Exploración con Pandas (3 p)**
- **Apartado 4 — Apache Pig (2 p)**
- **Apartado 5 — Spark + Hive + HQL (3 p)**
- **Checklist final**

Regla: cada apartado debe incluir:
- Markdown: *Objetivo y plan*
- Código
- Markdown: *Conclusiones* (tras ejecutar)

---

## 2) Apartado 1 — Dataset (1 punto)
**Qué debe explicarse:**
- Qué mide el dataset y por qué es interesante.
- Qué ficheros se usan (mínimo 2, relacional).
- Qué clave(s) permiten relacionarlos (JOIN).
- Qué variables son útiles para análisis.

**Evidencia mínima:**
- `df.head()` (o `df.sample()`)
- `df.shape`
- `df.dtypes` / `df.info()`
- Texto: relación entre tablas (survey ↔ genotyping)

---

## 3) Apartado 2 — Importación automática (1 punto)
**Objetivo:** descarga reproducible (sin carga manual).

**Opciones válidas:**
- Descarga automática desde URL (p. ej. `wget` / `gdown` / `curl`) + checksum opcional.
- Kaggle API (si aplica).
- Repositorio propio con archivos (siempre que la obtención sea automatizada).

**Evidencia mínima:**
- Celda con comando/función de descarga
- `!ls -lh` mostrando ficheros con tamaño > 0
- Lectura en Pandas sin error

---

## 4) Apartado 3 — Exploración con Pandas (3 puntos)
**Debe cubrir (como mínimo):**
- Nulos (conteos y % si puedes)
- Valores codificados como missing (p. ej. -9 en genotipado)
- Formatos erróneos (fechas / strings vacíos si existen)

**Evidencia mínima:**
- `df.info()`
- `df.isna().sum()` (y/o %)
- Conteo de -9 en columnas relevantes (si aplica)
- 3 observaciones escritas (2–4 líneas cada una)

---

## 5) Apartado 4 — Apache Pig (2 puntos)

### 5.1 Correcciones obligatorias (mínimo 2)
**Ejemplos válidos:**
- Reemplazar `-9` → `NULL` en columnas numéricas relevantes (genotipado)
- Convertir tipos (string → int/float)
- Normalizar strings (`TRIM`, `LOWER`) y vacíos → NULL

**Evidencia mínima:**
- Script Pig visible (`%%writefile limpieza.pig`)
- Log de ejecución exitoso
- Vista “antes/después” (comparación con counts / head)

### 5.2 Tratamiento interesante (no trivial)
Ejemplos:
- Agregación por grupo (p. ej. media GRS por grupo de edad/sexo)
- Conteo de “high genetic risk” por categoría
- Top‑N (si tiene sentido con el dataset)

**Evidencia mínima:**
- Resultado final visible (tabla / top‑N / agregación)

---

## 6) Apartado 5 — Spark + Hive + HQL (3 puntos)

### 6.1 Crear tablas Hive (mínimo 2 tablas)
Objetivo: cargar en Hive **dos tablas** (survey y genotyping) desde datos ya curados.

**Evidencia mínima:**
- `SparkSession.builder.enableHiveSupport()` (o equivalente)
- `saveAsTable()` (o `insertInto()`)
- `SHOW TABLES;` mostrando ambas tablas

### 6.2 Consultas HQL obligatorias (2 consultas)
**Requisitos:**
- **2 consultas diferentes**
- **Cada consulta debe realizar un JOIN real** entre **al menos 2 tablas**
- Mostrar resultado con `.show()` o tabla equivalente

**Evidencia mínima:**
- SQL visible (texto)
- Resultado visible
- (Recomendado) `COUNT(*)` para validar que el JOIN funciona

---

## 7) Checklist final (antes de entregar)
- ¿Aparecen los 5 apartados con títulos claros?
- ¿Importación automática demostrada?
- ¿En Pandas hay 3 observaciones justificadas?
- ¿Pig corrige 2 campos y se demuestra?
- ¿Hive tiene 2 tablas?
- ¿Hay 2 HQL con JOIN real?
- ¿El notebook ejecuta completo sin errores (“Run all”)?
