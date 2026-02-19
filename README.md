# BDA_dataset

Repositorio de trabajo para la evaluación BDA03 (pipeline ETL con Pandas, Pig, Spark y Hive) sobre el dataset T1D Guertin 2024.
Su objetivo es centralizar cuadernos, datos fuente y documentación para ejecutar el flujo completo A→1→2→3→4→5 de forma reproducible.

## Qué leer primero (CORE)
- [docs/BDA03/CORE/ENUNCIADO_BDA03.md](docs/BDA03/CORE/ENUNCIADO_BDA03.md)
- [docs/BDA03/CORE/BDA03_GUIA_OPERATIVA_EVALUACION.md](docs/BDA03/CORE/BDA03_GUIA_OPERATIVA_EVALUACION.md)
- [docs/BDA03/CORE/BDA03_DOCUMENTO_MAESTRO_Gemini_Colab.md](docs/BDA03/CORE/BDA03_DOCUMENTO_MAESTRO_Gemini_Colab.md)
- [docs/BDA03/CORE/DATASET_CARD.md](docs/BDA03/CORE/DATASET_CARD.md)

## Documentos SUPPORT (verificación)
- [docs/BDA03/SUPPORT/BDA03_CHECKLIST_FINAL.md](docs/BDA03/SUPPORT/BDA03_CHECKLIST_FINAL.md)
- [docs/BDA03/SUPPORT/BDA03_GUIA_ESTILO.md](docs/BDA03/SUPPORT/BDA03_GUIA_ESTILO.md)
- [docs/BDA03/SUPPORT/BDA03_DEBUG_GUIDE.md](docs/BDA03/SUPPORT/BDA03_DEBUG_GUIDE.md)
- [docs/BDA03/SUPPORT/BDA03_I0_Analisis_Estrategico.md](docs/BDA03/SUPPORT/BDA03_I0_Analisis_Estrategico.md)
- [docs/BDA03/SUPPORT/BDA03_I7_Guia_Tutor.md](docs/BDA03/SUPPORT/BDA03_I7_Guia_Tutor.md)

## Estructura del repo

```text
BDA_dataset/
├── README.md
├── BDA03_cuadernos/
│   ├── 0301_Apache_Pig.ipynb
│   ├── 0302_Primeros_pasos_Spark.ipynb
│   ├── 0303_Ejemplos_de_componentes_Spark.ipynb
│   ├── 0304_Sqoop_y_Flume.ipynb
│   ├── 0305_Importación_de_datos_en_Hive_utilizando_PySpark.ipynb
│   ├── 0306_Ejemplo_completo_HDFS_Sqoop_HUE_Hive_en_Cloudera.pdf
│   └── recursos/
├── Dataset not incorporated into the T1DKP/
│   ├── survey_data_and_results_final.xlsx
│   ├── assay_final_genotyping_file.xlsx
│   ├── TableS1_TID GRS SNP List.xlsx
│   └── README_Guertin2024.txt
├── docs/
│   ├── BDA03/
│   │   ├── CORE/
│   │   └── SUPPORT/
│   └── teoria/
├── archive_notebooks/
│   └── BDA03_Evaluacion_T1D01.ipynb ... BDA03_Evaluacion_T1D06.ipynb
├── BDA03_Evaluacion_T1D.ipynb
├── BDA03_Evaluacion_T1D_copilot.ipynb
└── .venv/ (entorno local)
```

## Cómo ejecutar en Colab (resumen)
1. Clonar este repositorio en la sesión de Colab.
2. Preparar datos de entrada: usar XLSX del dataset y convertir a CSV cuando el flujo lo requiera.
3. Seguir estrictamente el orden del enunciado: A) contexto del dataset, 1) importación, 2) exploración, 3) Pig, 4) Spark→Hive, 5) HQL con JOIN.
4. Mantener evidencia visible en outputs en cada sección antes de pasar a la siguiente.

## Requisitos clave de evaluación
- Java 17 en entorno de ejecución.
- Pig: mínimo 2 correcciones de calidad + 1 tratamiento interesante.
- Spark→Hive: crear 2 tablas (survey y genotyping).
- HQL: mínimo 2 consultas con JOIN real entre tablas.

## Organización de cuadernos
- Cuaderno canónico de trabajo: `BDA03_Evaluacion_T1D.ipynb`.
- Cuaderno alternativo/copilot: `BDA03_Evaluacion_T1D_copilot.ipynb`.
- Versiones históricas: `archive_notebooks/BDA03_Evaluacion_T1D01.ipynb` a `archive_notebooks/BDA03_Evaluacion_T1D06.ipynb`.