# BDA_dataset

Este repositorio reúne el material de trabajo de **BDA03 – Ecosistema Hadoop-Spark**.  
Su objetivo es servir como base práctica para un flujo ETL de extremo a extremo con datos de diabetes tipo 1.  
Incluye cuadernos de laboratorio, recursos de datos y documentación de apoyo para ejecución, validación y depuración.  
Se usa como guía tanto para trabajo humano (estudio, implementación, entrega) como para asistentes de IA (Copilot, Gemini).  
El proyecto cubre un pipeline completo con **Pandas, Pig, Spark y Hive**, incluyendo transformación, persistencia y consultas.  
También incorpora documentos de control para checklist final, estilo técnico y resolución de errores.  

---

## 1) Estructura del repositorio

### Raíz
- [README.md](README.md): documento principal del repositorio.
- [Dataset not incorporated into the T1DKP/README_Guertin2024.txt](Dataset%20not%20incorporated%20into%20the%20T1DKP/README_Guertin2024.txt): referencia del dataset T1D Guertin 2024.
- [BDA03_cuadernos/](BDA03_cuadernos/): notebooks de práctica de la unidad.
- [docs/](docs/): documentación de control, guías operativas y teoría.

### Cuadernos de trabajo (`BDA03_cuadernos/`)
- [BDA03_cuadernos/0301_Apache_Pig.ipynb](BDA03_cuadernos/0301_Apache_Pig.ipynb): limpieza y transformaciones con Pig.
- [BDA03_cuadernos/0302_Primeros_pasos_Spark.ipynb](BDA03_cuadernos/0302_Primeros_pasos_Spark.ipynb): introducción operativa a Spark.
- [BDA03_cuadernos/0303_Ejemplos_de_componentes_Spark.ipynb](BDA03_cuadernos/0303_Ejemplos_de_componentes_Spark.ipynb): componentes y ejemplos de Spark.
- [BDA03_cuadernos/0304_Sqoop_y_Flume.ipynb](BDA03_cuadernos/0304_Sqoop_y_Flume.ipynb): ingesta con Sqoop/Flume.
- [BDA03_cuadernos/0305_Importación_de_datos_en_Hive_utilizando_PySpark.ipynb](BDA03_cuadernos/0305_Importación_de_datos_en_Hive_utilizando_PySpark.ipynb): carga de datos en Hive con PySpark (**notebook principal del flujo final**).

### Datasets crudos y recursos (`BDA03_cuadernos/recursos/`)
- [BDA03_cuadernos/recursos/dataset_cuaderno_0301_Apache_Pig_train.csv](BDA03_cuadernos/recursos/dataset_cuaderno_0301_Apache_Pig_train.csv)
- [BDA03_cuadernos/recursos/train.csv](BDA03_cuadernos/recursos/train.csv)
- [BDA03_cuadernos/recursos/Example1.json](BDA03_cuadernos/recursos/Example1.json)
- [BDA03_cuadernos/recursos/pruebas_por_localidades.json](BDA03_cuadernos/recursos/pruebas_por_localidades.json)

### Documentación y control (`docs/`)
- [docs/BDA03/CORE/](docs/BDA03/CORE/): documentación fuente primaria para ejecución y evaluación.
- [docs/BDA03/SUPPORT/](docs/BDA03/SUPPORT/): documentación de apoyo (checklist, debug, estilo y guía tutor).
- [docs/teoria/BDA02_resumen.md](docs/teoria/BDA02_resumen.md): resumen teórico de apoyo.

### Qué leer primero
1. [README.md](README.md)  
2. [docs/BDA03/CORE/ENUNCIADO_BDA03.md](docs/BDA03/CORE/ENUNCIADO_BDA03.md)  
3. [docs/BDA03/CORE/BDA03_GUIA_OPERATIVA_EVALUACION.md](docs/BDA03/CORE/BDA03_GUIA_OPERATIVA_EVALUACION.md)  
4. [docs/BDA03/CORE/BDA03_DOCUMENTO_MAESTRO_Gemini_Colab.md](docs/BDA03/CORE/BDA03_DOCUMENTO_MAESTRO_Gemini_Colab.md)  
5. [docs/BDA03/CORE/DATASET_CARD.md](docs/BDA03/CORE/DATASET_CARD.md)  
6. [docs/BDA03/CORE/REFERENCIA_ESTILO_CUADERNOS_BDA03.md](docs/BDA03/CORE/REFERENCIA_ESTILO_CUADERNOS_BDA03.md)  
7. [docs/BDA03/SUPPORT/BDA03_CHECKLIST_FINAL.md](docs/BDA03/SUPPORT/BDA03_CHECKLIST_FINAL.md)  
8. [docs/BDA03/SUPPORT/BDA03_DEBUG_GUIDE.md](docs/BDA03/SUPPORT/BDA03_DEBUG_GUIDE.md)  
9. [BDA03_cuadernos/0305_Importación_de_datos_en_Hive_utilizando_PySpark.ipynb](BDA03_cuadernos/0305_Importación_de_datos_en_Hive_utilizando_PySpark.ipynb)

## Estructura documental BDA03

### CORE (fuente primaria para agentes)
- [docs/BDA03/CORE/ENUNCIADO_BDA03.md](docs/BDA03/CORE/ENUNCIADO_BDA03.md)
- [docs/BDA03/CORE/BDA03_GUIA_OPERATIVA_EVALUACION.md](docs/BDA03/CORE/BDA03_GUIA_OPERATIVA_EVALUACION.md)
- [docs/BDA03/CORE/BDA03_DOCUMENTO_MAESTRO_Gemini_Colab.md](docs/BDA03/CORE/BDA03_DOCUMENTO_MAESTRO_Gemini_Colab.md)
- [docs/BDA03/CORE/DATASET_CARD.md](docs/BDA03/CORE/DATASET_CARD.md)

### SUPPORT (consultar bajo demanda)
- [docs/BDA03/SUPPORT/BDA03_CHECKLIST_FINAL.md](docs/BDA03/SUPPORT/BDA03_CHECKLIST_FINAL.md)
- [docs/BDA03/SUPPORT/BDA03_DEBUG_GUIDE.md](docs/BDA03/SUPPORT/BDA03_DEBUG_GUIDE.md)
- [docs/BDA03/SUPPORT/BDA03_GUIA_ESTILO.md](docs/BDA03/SUPPORT/BDA03_GUIA_ESTILO.md)
- [docs/BDA03/SUPPORT/BDA03_I7_Guia_Tutor.md](docs/BDA03/SUPPORT/BDA03_I7_Guia_Tutor.md)
- [docs/BDA03/SUPPORT/BDA03_I0_Analisis_Estrategico.md](docs/BDA03/SUPPORT/BDA03_I0_Analisis_Estrategico.md)

---

## 2) Documentos clave para agentes de IA

Antes de proponer o escribir código:

**Fuente primaria (CORE):**

- [docs/BDA03/CORE/ENUNCIADO_BDA03.md](docs/BDA03/CORE/ENUNCIADO_BDA03.md)
- [docs/BDA03/CORE/BDA03_DOCUMENTO_MAESTRO_Gemini_Colab.md](docs/BDA03/CORE/BDA03_DOCUMENTO_MAESTRO_Gemini_Colab.md)
- [docs/BDA03/CORE/BDA03_GUIA_OPERATIVA_EVALUACION.md](docs/BDA03/CORE/BDA03_GUIA_OPERATIVA_EVALUACION.md)
- [docs/BDA03/CORE/DATASET_CARD.md](docs/BDA03/CORE/DATASET_CARD.md)
- Referencia de estilo (CORE): docs/BDA03/CORE/REFERENCIA_ESTILO_CUADERNOS_BDA03.md

**Soporte (SUPPORT, solo bajo demanda):**
- [docs/BDA03/SUPPORT/BDA03_GUIA_ESTILO.md](docs/BDA03/SUPPORT/BDA03_GUIA_ESTILO.md)
- [docs/BDA03/SUPPORT/BDA03_CHECKLIST_FINAL.md](docs/BDA03/SUPPORT/BDA03_CHECKLIST_FINAL.md)
- [docs/BDA03/SUPPORT/BDA03_DEBUG_GUIDE.md](docs/BDA03/SUPPORT/BDA03_DEBUG_GUIDE.md)
- [docs/BDA03/SUPPORT/BDA03_I7_Guia_Tutor.md](docs/BDA03/SUPPORT/BDA03_I7_Guia_Tutor.md)
- [docs/BDA03/SUPPORT/BDA03_I0_Analisis_Estrategico.md](docs/BDA03/SUPPORT/BDA03_I0_Analisis_Estrategico.md)

---

## 3) Flujo recomendado de trabajo

1. Clonar el repositorio y validar estructura de carpetas.  
2. Convertir el origen Excel a CSV (estándar de entrada del flujo).  
3. Realizar exploración inicial con Pandas (perfilado y calidad de datos).  
4. Aplicar limpieza y normalización con Pig.  
5. Persistir resultados en Hive (tablas gestionadas/externas según práctica).  
6. Ejecutar consultas HQL de validación y análisis, incluyendo **JOIN obligatorio**.

---

## 4) Reglas técnicas fijas

- **Java 17 obligatorio** para el entorno de ejecución.
- Dataset de referencia: **T1D Guertin 2024**.
- El valor **`-9` representa missing** y debe tratarse explícitamente.
- Se requieren **2 consultas HQL con JOIN real** (no simulaciones ni subconsultas sin join efectivo).

---

## 5) Árbol visual del repositorio

```text
BDA_dataset/
├── README.md
├── BDA03_cuadernos/
│   ├── 0301_Apache_Pig.ipynb
│   ├── 0302_Primeros_pasos_Spark.ipynb
│   ├── 0303_Ejemplos_de_componentes_Spark.ipynb
│   ├── 0304_Sqoop_y_Flume.ipynb
│   ├── 0305_Importación_de_datos_en_Hive_utilizando_PySpark.ipynb
│   └── recursos/
│       ├── dataset_cuaderno_0301_Apache_Pig_train.csv
│       ├── Example1.json
│       ├── pruebas_por_localidades.json
│       └── train.csv
├── Dataset not incorporated into the T1DKP/
│   └── README_Guertin2024.txt
└── docs/
    ├── BDA03/
    │   ├── CORE/
    │   │   ├── ENUNCIADO_BDA03.md
    │   │   ├── BDA03_GUIA_OPERATIVA_EVALUACION.md
    │   │   ├── BDA03_DOCUMENTO_MAESTRO_Gemini_Colab.md
    │   │   └── DATASET_CARD.md
    │   └── SUPPORT/
    │       ├── BDA03_CHECKLIST_FINAL.md
    │       ├── BDA03_DEBUG_GUIDE.md
    │       └── ...
    └── teoria/
        └── BDA02_resumen.md
```