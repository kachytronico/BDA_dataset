# ENUNCIADO — BDA03 Tarea de Evaluación
## Ecosistema Hadoop-Spark (proceso completo ETL)

## Descripción de la tarea

Ahora que ya conocemos todo el ecosistema Hadoop-Spark en profundidad, vamos a realizar un ejercicio que abarque todo el proceso de tratamiento de datos: desde que se extraen de un repositorio, se limpian, se transforman, se exportan a una base de datos relacional (Hive) y se realizan consultas sobre ellos.

Para ello, recupera los conjuntos de datos que usaste en la tarea anterior BDA01 - Tarea de Evaluación. Recuerda que usaste un conjunto de datos de tu elección 
## Entregable

Debes entregar un cuaderno de Colab con:

### 1) Explicación del conjunto de datos elegido
- Cuál es su temática.
- Cuál es su tamaño.
- Con qué campos se relaciona.
- Por qué puede resultar interesante.

### 2) Importación automática de los datos
Importa de manera automática tus conjuntos de datos desde Kaggle u otro repositorio.

Pistas de herramientas posibles:
- Librería `kaggle`.
- Librería `opendatasets`.
- Otras opciones equivalentes.
- `Sqoop` (dependiendo de dónde se encuentren los datos).

### 3) Exploración inicial con Pandas
Usa Pandas para realizar una primera visualización en forma de tabla y estudiar los datos:
- Valores nulos.
- Fechas con formatos incorrectos.
- Campos vacíos.
- Otros problemas de calidad de datos.

### 4) Limpieza y tratamiento con Apache Pig
Usa Apache Pig para:
- Corregir los fallos observados en el punto anterior.
- Modificar al menos dos campos (por ejemplo: cambiar formatos de fechas y rellenar campos vacíos/nulos con valores por defecto).
- Realizar un tratamiento de datos que consideres interesante (por ejemplo, encontrar las 3 palabras más repetidas en ambos archivos).

### 5) Persistencia y consultas con Spark + Hive
Usa Spark (PySpark) para importar tus ficheros a una base de datos relacional Hive.

Realiza al menos dos consultas HQL que impliquen dos tablas.

## Criterios de calificación

La tarea se calificará de 0 a 10 cuando termine la unidad:

- 1 punto: apartado 1.
- 1 punto: apartado 2.
- 3 puntos: apartado 3 (1,5 por subapartado).
- 2 puntos: apartado 4.
- 3 puntos: apartado 5 (1,5 por consulta).

Esta tarea tiene efecto directo en tu nota. Puedes consultar los BDA Criterios de calificación para ver el peso exacto.

## Recursos necesarios

- Conexión a Internet.
- Cuenta de Gmail `@fpfrioja` para acceder a Colab.
- Tutoriales de Colab.

## Consejos y recomendaciones

- Estudia los contenidos teóricos de la unidad; comprender los conceptos te ayudará a entender los procesos y los códigos.
- Sigue los tutoriales de Colab para familiarizarte con la herramienta.
- Es muy recomendable que trabajes todos los cuadernos de la unidad antes de abordar la tarea.
- Accede a cada uno de los cuadernos de tareas y cópialo en tu Google Drive o en tu repositorio de Git.

## Indicaciones de entrega

### Nombre del archivo
Formato: `<iniciales><número de unidad>`

Ejemplo:
- Juan García Rodríguez, unidad 1: `JGR01.zip`

### Entrega de varios archivos

- Solo se permite la entrega de un archivo por tarea.
- En caso de tener que entregar varios cuadernos de Colab o scripts de código:
   - Crea una carpeta con el mismo convenio de nombre anterior.
   - Esa carpeta no debe contener subcarpetas adicionales.
   - Comprímela en formato `.zip`, `.7z` o `.rar` y envíala.

Ejemplo: `JGR01.zip`

### Plazos de entrega

- Toda práctica entregada fuera de plazo constará como "no apta" (si es Tarea de Refuerzo) o "0" (si es Tarea de Evaluación).

### Copia total o parcial de prácticas

- En caso de detectar copia total o parcial, se puntuará como "no apta" (Tarea de Refuerzo) o "0" (Tarea de Evaluación) a todas las entregas que coincidan.
