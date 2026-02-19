# BDA03 — Checklist Final (Blindaje de entrega)

## Antes de comprimir (OBLIGATORIO)
- [ ] **Run all** (o ejecutar de arriba a abajo) sin errores.
- [ ] El notebook muestra **outputs visibles** en cada sección.
- [ ] Las conclusiones están **basadas en outputs** (sin inventar).

---

## Sección A — Explicación del dataset (1p)
- [ ] Temática y por qué es interesante.
- [ ] Tamaño aproximado / nº de filas (si lo muestras en outputs, mejor).
- [ ] Archivos usados (nombres exactos).
- [ ] **Relación** entre tablas (`SUBJECT_ID` ↔ `FID`).

---

## Sección 1 — Importación automática (1p)
- [ ] Importación **automática** (git clone / kaggle / wget).
- [ ] Evidencia: `ls` del repo clonado.
- [ ] Evidencia: existen XLSX “raw” y CSV convertidos (rutas claras).
- [ ] Evidencia: `shape` y `head()` de ambos.

---

## Sección 2 — Pandas exploración (3p)
- [ ] Evidencia del JOIN: IDs únicos + intersección + merge inner.
- [ ] Evidencia calidad: nulos (NaN) y/o vacíos.
- [ ] Evidencia missing codificado: recuento de `-9` y **en qué columnas**.

---

## Sección 3 — Apache Pig (3p = 1.5 + 1.5)
### 3.1 Limpieza (mínimo 2 cambios)
- [ ] Se ven **dos correcciones** defendibles (ej. `-9`→NULL/empty + `TRIM` claves).
- [ ] Evidencia: script `.pig` visible (%%writefile o archivo).
- [ ] Evidencia: ejecución `pig -x local ...` sin error.
- [ ] Evidencia: outputs generados (`pig_out/...`) + `head` del resultado.

### 3.2 Tratamiento interesante (Pig)
- [ ] Evidencia: `DUMP` con resultado (ej. top3 de `RACE` con counts).
- [ ] El tratamiento es simple y evaluable (GROUP/COUNT/ORDER/LIMIT).

---

## Sección 4 — Spark → Hive (2p)
- [ ] Spark lee los **datos limpios** (salida Pig).
- [ ] Se crean **2 tablas Hive** (survey + genotyping).
- [ ] Evidencia: `SHOW TABLES` (aparecen como no temporales).
- [ ] Evidencia: `printSchema()` y `show(3)` de cada tabla.
- [ ] Evidencia: `COUNT(*)` (3818 en ambas, si es lo que te sale).

---

## Sección 5 — HQL con JOIN (3p = 1.5 + 1.5)
- [ ] **2 consultas**.
- [ ] **Ambas** hacen `JOIN` real entre `tabla_survey` y `tabla_genotyping`.
- [ ] Evidencia: outputs de ambas consultas (tabla impresa).
- [ ] Conclusión: resumen breve con números reales.

---

## Entrega
- [ ] Nombre de archivo según iniciales + unidad (ej. `ALR03.zip`).
- [ ] Dentro del zip: notebook `.ipynb` (y scripts `.pig` si aplica).
- [ ] Sin subcarpetas extra (si tu profe lo exige así).
