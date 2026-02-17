# DATASET_CARD — T1D Screening Project (Guertin 2024)

## Archivos (inputs de la evaluación)
1) `survey_data_and_results_final.xlsx`  
2) `assay_final_genotyping_file.xlsx`  
3) `TableS1_TID GRS SNP List.xlsx`  
4) `README_Guertin2024.txt`  

> Nota: en genotipado, **-9** representa missing y debe tratarse en limpieza.

---

## Tablas objetivo (para Hive/HQL)
- `survey_data_and_results_final`  (tabla survey)
- `assay_final_genotyping_file`    (tabla genotyping)

---

## Clave relacional oficial (JOIN)
**Clave prevista:** `SUBJECT_ID` (o identificador equivalente).

### Cómo confirmarla (en Pandas)
- `df_survey.columns` y `df_geno.columns`
- Buscar columna común: `set(df_survey.columns) & set(df_geno.columns)`
- Validar unicidad:
  - `df_survey[KEY].nunique()` vs `len(df_survey)`
  - `df_geno[KEY].nunique()` vs `len(df_geno)`
- Validar solape del join:
  - `df_survey.merge(df_geno[[KEY]], on=KEY, how="inner").shape[0]`

---

## Correcciones Pig previstas (mínimo 2, defendibles)
1) **Missing codificado:** convertir `-9` → `NULL` en columnas numéricas relevantes (genotipado).
2) **Normalización de tipos / vacíos:** casteos (string→int/float) y/o vacíos→NULL (survey).

**Evidencia requerida:** comparación “antes/después” (counts de -9 / nulos y muestra de filas).

---

## Tratamiento interesante previsto (Pig o Spark)
- Agregación de “high genetic risk” por variable demográfica (sexo/raza/edad).
- Media/mediana de GRS por grupo (si existe columna GRS).
- Conteos y ranking de categorías con mayor proporción de alto riesgo.

---

## Outputs que deben verse en el notebook
- Datos crudos cargados (Pandas) + perfilado.
- Salida Pig “curada” (y recuentos de limpieza).
- 2 tablas Hive creadas y listadas.
- 2 queries HQL con JOIN (resultados mostrados).
