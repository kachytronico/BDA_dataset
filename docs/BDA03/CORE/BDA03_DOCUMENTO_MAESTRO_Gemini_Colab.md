# BDA03 — Documento Maestro (Gemini + Colab · Evaluación)

Este documento define el **método de trabajo** para resolver la **tarea de evaluación BDA03**
en **Google Colab** con **Gemini integrado**, manteniendo control humano y asegurando una entrega
**evaluable** (con evidencias visibles y conclusiones basadas en outputs reales).

## Documentos de referencia (leer primero)
- docs/BDA03/CORE/ENUNCIADO_BDA03.md (enunciado oficial)
- docs/BDA03/CORE/BDA03_GUIA_OPERATIVA_EVALUACION.md (pasos + evidencia mínima)
- docs/BDA03/CORE/BDA03_DOCUMENTO_MAESTRO_Gemini_Colab.md (reglas anti-bloqueo)

## Fuente primaria
El agente debe basarse primero en: docs/BDA03/CORE/ENUNCIADO_BDA03.md

## Referencia obligatoria de estilo
- Referencia de estilo (CORE): [docs/BDA03/CORE/REFERENCIA_ESTILO_CUADERNOS_BDA03.md](docs/BDA03/CORE/REFERENCIA_ESTILO_CUADERNOS_BDA03.md)
- Cuaderno Pig de referencia: [BDA03_cuadernos/0301_Apache_Pig.ipynb](BDA03_cuadernos/0301_Apache_Pig.ipynb)
- Cuaderno Spark+Hive+HQL de referencia: [BDA03_cuadernos/0305_Importación_de_datos_en_Hive_utilizando_PySpark.ipynb](BDA03_cuadernos/0305_Importación_de_datos_en_Hive_utilizando_PySpark.ipynb)
- Antes de escribir código de Pig, Spark, Hive o HQL, el agente debe revisar estos cuadernos y aplicar el mismo estilo operativo.
- Se mantienen reglas fijas: Java 17 obligatorio, `-9` como missing y consultas HQL con JOIN real.

## Estructura documental CORE vs SUPPORT

### CORE (fuente primaria)
- docs/BDA03/CORE/ENUNCIADO_BDA03.md
- docs/BDA03/CORE/BDA03_GUIA_OPERATIVA_EVALUACION.md
- docs/BDA03/CORE/BDA03_DOCUMENTO_MAESTRO_Gemini_Colab.md
- docs/BDA03/CORE/DATASET_CARD.md

### SUPPORT (consulta bajo demanda)
- docs/BDA03/SUPPORT/BDA03_CHECKLIST_FINAL.md
- docs/BDA03/SUPPORT/BDA03_DEBUG_GUIDE.md
- docs/BDA03/SUPPORT/BDA03_GUIA_ESTILO.md
- docs/BDA03/SUPPORT/BDA03_I7_Guia_Tutor.md
- docs/BDA03/SUPPORT/BDA03_I0_Analisis_Estrategico.md

No consultar SUPPORT salvo que el usuario lo pida o el estado lo requiera: (a) redacción → GUIA_ESTILO, (b) antes de entregar → CHECKLIST, (c) error → DEBUG, (d) dudas de rúbrica → I7.

---

## 1) Filosofía (lo que manda siempre)
- **El enunciado es la ley**: no optimizar si contradice requisitos.
- **Reproducible > sofisticado**: que se pueda ejecutar de 0 a 100 sin fallos.
- **Evidencia visible > explicación larga**: si no se ve en outputs, “no existe” para corrección.
- **Nada se inventa**: cualquier número/tabla/métrica debe salir del output del notebook.
- **Gemini es asistente, no jefe**: propone; **espera confirmación**; ejecuta solo lo autorizado.

---

## 2) Regla anti‑bloqueo (CRÍTICA en Colab)
En Colab, Gemini a veces intenta crear celdas “automáticas” de análisis (“Analyze…”, “Status report…”).
Eso **no se permite** en evaluación.

**Normas obligatorias:**
- ❌ No leer documentos desde disco ni imprimirlos en notebook.
- ❌ No generar celdas automáticas de análisis o “planes multi‑step” sin confirmación.
- ✅ El **chat** se usa para planificar/decidir.
- ✅ El **notebook** se usa solo para: **código + outputs + conclusiones**.

---

## 3) Reglas técnicas fijas para BDA03 (IMPORTANTE)

### 3.1 Entorno
- **Java 17 obligatorio**.
- Validaciones mínimas de entorno (outputs visibles):
  - `java -version`
  - `hadoop version` (si aplica)
  - `pyspark --version` o `spark.version`

### 3.2 HQL / Hive (requisito evaluable)
- Se requieren **al menos 2 consultas HQL**.
- **Cada consulta debe realizar un JOIN real** entre **mínimo 2 tablas** (p. ej., `survey` y `genotyping`).
- No se consideran válidas como “solución completa” consultas sobre una sola tabla sin JOIN.

### 3.3 Dataset oficial para esta evaluación
- Dataset: **T1D Screening Project (Guertin 2024)**.
- Tablas objetivo:
  - `survey_data_and_results_final`
  - `assay_final_genotyping_file`
- En genotipado, valores **-9 representan missing** y deben tratarse en limpieza (Pig / preprocesado).

---

## 4) Ciclo de trabajo (NO saltarlo)
Para cada apartado del enunciado:

1. Gemini propone el plan (sin código).
2. Tú confirmas.
3. Gemini genera SOLO:
   - Celda Markdown: **Objetivo y plan**
   - Celda de código
   - Celda Markdown: **Conclusiones (a completar tras ejecutar)**
4. Ejecutas el código.
5. Gemini reescribe solo las conclusiones con **outputs reales**.
6. Pasas al siguiente apartado.

---

## 5) Orden práctico recomendado (para minimizar riesgos)
1. Preparar entorno (Java 17 + dependencias).
2. Importación automática (descarga reproducible) + verificación de ficheros.
3. Carga y exploración con Pandas (calidad: nulos, -9, formatos).
4. Pig (mínimo 2 correcciones demostrables + tratamiento interesante).
5. Spark + Hive: crear **2 tablas** (survey y genotyping) desde datos ya curados.
6. HQL: ejecutar **2 consultas con JOIN** y mostrar resultados.
7. Checklist final: ejecutar “Run all” y verificar evidencias.

---

## 6) Prompt de arranque recomendado (pegar al iniciar la sesión)
```text
Vamos a resolver la evaluación BDA03 paso a paso en este notebook.

REGLAS:
1) No leas/imprimas documentos desde disco.
2) No crees celdas automáticas de análisis.
3) Chat = planificación; notebook = código + outputs + conclusiones.
4) No avances sin mi confirmación.
5) No inventes resultados.

Antes de escribir código:
- Resume qué apartado del enunciado toca ahora.
- Define evidencia mínima visible.
- Indica riesgos y validación.
Espera mi confirmación.
```
