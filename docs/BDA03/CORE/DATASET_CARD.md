# DATASET_CARD — T1D (Guertin 2024)

## Dataset
Datos de riesgo genético de Diabetes Tipo 1 (T1D) del estudio Guertin et al. (2024).

## Archivos usados (fuente en repo clonado)
- `survey_data_and_results_final.xlsx`  → convertido a `survey.csv`
- `assay_final_genotyping_file.xlsx`   → convertido a `genotyping.csv`

## Tablas objetivo (Hive)
- `tabla_survey`
- `tabla_genotyping`

## Clave relacional (JOIN)
- `tabla_survey.SUBJECT_ID` ↔ `tabla_genotyping.FID`
- Validación en Pandas (mi ejecución): IDs únicos 3818 en ambas tablas y merge inner 3818 filas.

## Calidad / problema a limpiar (para justificar Pig)
- En `genotyping` existe missing codificado como `-9`.
- Total detectado en outputs: 181 valores `-9` concentrados en:
  - `rs9585056` (89)
  - `rs12927355` (82)
  - `rs1367728` (9)
  - `rs72727394` (1)

## Rutas de trabajo en Colab (referencia)
- Repo clonado: `/content/BDA_dataset`
- CSV listos para Pig/Spark: `/content/data/csv/survey.csv` y `/content/data/csv/genotyping.csv`
- Salidas Pig: `/content/data/pig_out/...`
