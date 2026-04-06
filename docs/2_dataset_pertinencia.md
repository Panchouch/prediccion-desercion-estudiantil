# Selección, carga y pertinencia del dataset

## 1. Dataset seleccionado

Para este proyecto se seleccionó el dataset **Predict Students’ Dropout and Academic Success**, orientado al análisis de factores asociados a la trayectoria académica de estudiantes de educación superior.

## 2. Fuente de datos

El dataset fue obtenido desde el repositorio **UCI Machine Learning Repository**, una fuente ampliamente utilizada en proyectos académicos y de ciencia de datos.

Fuente:
- UCI Machine Learning Repository
- Dataset: *Predict Students’ Dropout and Academic Success*

## 3. Proceso de carga

La carga del dataset se realizó a partir de un archivo CSV, utilizando Python y la biblioteca pandas. Posteriormente, se verificaron dimensiones, nombres de columnas, tipos de datos y estructura general del conjunto de datos, con el fin de asegurar una correcta ingesta antes de iniciar el análisis exploratorio y el preprocesamiento.

## 4. Cobertura del dataset

El dataset contiene **4424 registros** y un conjunto de variables que describen aspectos relevantes del estudiante, entre ellos:

- características sociodemográficas;
- antecedentes académicos previos;
- situación administrativa;
- información sobre matrícula y becas;
- variables de rendimiento académico del primer y segundo semestre.

La variable objetivo del dataset corresponde a tres posibles estados finales del estudiante:

- `Dropout`
- `Enrolled`
- `Graduate`

Esta cobertura permite abordar el fenómeno de deserción desde distintas dimensiones y no solo desde una perspectiva académica aislada.

## 5. Pertinencia respecto al problema

El dataset es pertinente para la problemática planteada porque contiene variables directamente relacionadas con la permanencia, graduación y deserción estudiantil. Esto permite analizar el fenómeno desde una perspectiva multivariable, incorporando factores académicos, económicos, administrativos y personales.

Además, la presencia de una variable objetivo explícita facilita estudiar la relación entre los atributos del estudiante y su situación final dentro del sistema educativo.

## 6. Utilidad analítica

Este dataset permite desarrollar varias etapas relevantes de un proyecto de ciencia de datos, entre ellas:

- análisis exploratorio de variables;
- estudio de distribuciones y relaciones entre atributos;
- identificación de patrones asociados a la deserción;
- preparación de datos mediante limpieza, recodificación y codificación;
- construcción de un dataset apto para análisis posterior o modelado.

Por lo tanto, no solo es pertinente respecto al problema, sino también suficiente para desarrollar un flujo de trabajo completo de análisis de datos.

## 7. Restricciones y consideraciones

A pesar de su utilidad, el dataset presenta algunas restricciones que deben considerarse:

- proviene de un contexto institucional específico, por lo que la generalización de resultados puede ser limitada;
- varias variables categóricas están codificadas numéricamente, lo que exige una revisión detallada antes de su uso;
- algunas variables presentan alta fragmentación de categorías;
- la categoría `Enrolled` no representa necesariamente un resultado final definitivo, ya que corresponde a estudiantes que continúan en curso.

Estas restricciones no impiden el análisis, pero sí obligan a interpretar los resultados con cautela.

## 8. Conclusión

El dataset seleccionado es adecuado para abordar la problemática de deserción estudiantil planteada en este proyecto. Su cobertura, estructura y contenido permiten realizar análisis exploratorios, aplicar preprocesamiento justificado y construir una base sólida para etapas posteriores. En consecuencia, se considera una fuente técnicamente pertinente, suficiente y coherente con los objetivos definidos.
