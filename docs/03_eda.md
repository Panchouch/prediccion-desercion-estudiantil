# Resumen del Análisis Exploratorio de Datos (EDA)

## 1. Objetivo del EDA

El análisis exploratorio de datos tuvo como propósito comprender la estructura general del dataset, identificar patrones iniciales en las variables y detectar posibles problemas de calidad o preparación antes de avanzar al preprocesamiento.

En particular, el EDA permitió observar la distribución de la variable objetivo, explorar la composición de las variables categóricas y numéricas, y reconocer posibles relaciones, redundancias y desbalances relevantes para el proyecto.

---

## 2. Estructura general del dataset

El dataset utilizado corresponde a **Predict Students’ Dropout and Academic Success**, obtenido desde el repositorio UCI Machine Learning Repository. Este conjunto de datos contiene **4424 registros** y variables de distinta naturaleza, incluyendo:

- variables sociodemográficas;
- variables académicas previas;
- variables administrativas;
- variables de rendimiento del primer y segundo semestre;
- una variable objetivo con tres categorías: `Dropout`, `Enrolled` y `Graduate`.

Durante esta etapa se revisaron dimensiones, nombres de columnas, tipos de variables y frecuencia de categorías, con el fin de comprender el contenido del dataset antes de transformarlo.

---

## 3. Principales hallazgos del EDA

### 3.1 Variable objetivo

La variable `Target` mostró tres posibles resultados para la trayectoria del estudiante:

- `Dropout`
- `Enrolled`
- `Graduate`

Esto permitió abordar el fenómeno de deserción no solo como una condición binaria, sino como parte de una trayectoria académica más amplia.

### 3.2 Variables categóricas codificadas numéricamente

Se identificó que varias variables estaban representadas con códigos numéricos, aunque en realidad correspondían a variables categóricas. Esto fue especialmente relevante en variables como:

- `Marital status`
- `Application mode`
- `Previous qualification`
- `Mother's qualification`
- `Father's qualification`
- `Mother's occupation`
- `Father's occupation`
- `Nacionality`
- `Course`

Este hallazgo fue importante, ya que permitió evitar tratarlas erróneamente como variables numéricas continuas.

### 3.3 Alta fragmentación en algunas variables

Se observó que varias variables categóricas presentaban un número elevado de categorías, muchas de ellas con muy baja frecuencia. Esto ocurría especialmente en variables relacionadas con nivel educacional, ocupación, nacionalidad y modalidad de ingreso.

Esta fragmentación dificultaba la interpretación y sugería la necesidad de reagrupar categorías en la etapa de preprocesamiento.

### 3.4 Presencia de variables binarias bien definidas

También se identificaron variables binarias como:

- `Displaced`
- `Educational special needs`
- `Debtor`
- `Tuition fees up to date`
- `Gender`
- `Scholarship holder`
- `International`

Estas variables, en general, no requerían recodificación estructural, aunque algunas presentaban desbalance importante entre clases.

### 3.5 Desbalance en algunas variables

Una observación relevante fue el fuerte desbalance en variables como `Educational special needs`, donde la categoría positiva representaba una proporción muy pequeña del total. Este tipo de comportamiento se consideró importante para la interpretación posterior de resultados.

### 3.6 Posibles redundancias

El EDA permitió detectar relaciones de redundancia entre algunas variables:

- `Nacionality` e `International`
- `Course` y `Daytime/evening attendance`

Estas observaciones fueron clave para tomar decisiones más adelante en el preprocesamiento.

---

## 4. Utilidad del EDA para el proyecto

El EDA no solo permitió describir el dataset, sino que también aportó evidencia concreta para justificar decisiones posteriores. Gracias a esta etapa fue posible:

- distinguir correctamente variables numéricas y categóricas;
- identificar variables con categorías poco frecuentes;
- detectar posibles redundancias;
- revisar la distribución de variables binarias;
- reconocer inconsistencias que requerían tratamiento.

En consecuencia, el análisis exploratorio fue una etapa fundamental para orientar el preprocesamiento de manera técnica y justificada.

---

## 5. Conclusión

El análisis exploratorio de datos permitió comprender la estructura del dataset y detectar elementos clave para su preparación. En particular, evidenció la necesidad de reagrupar ciertas variables categóricas, revisar redundancias, controlar inconsistencias puntuales y planificar una codificación adecuada de variables.

De este modo, el EDA cumplió un rol central como base para la etapa de preprocesamiento, permitiendo avanzar con una visión más clara y fundamentada del conjunto de datos.
