# Data Quality Report

## 1. Descripción general del dataset

El conjunto de datos utilizado en este proyecto corresponde al dataset **Predict Students’ Dropout and Academic Success**, obtenido desde el repositorio **UCI Machine Learning Repository**. Este dataset contiene información sociodemográfica, académica y administrativa de estudiantes de educación superior, y tiene como objetivo analizar variables asociadas a la permanencia, graduación o deserción estudiantil.

El dataset original contiene **4424 registros** y una combinación de variables numéricas, binarias y categóricas codificadas numéricamente.

---

## 2. Evaluación general de calidad

En términos generales, el dataset presenta una estructura adecuada para su uso en un proyecto de ciencia de datos. El archivo pudo cargarse correctamente y las variables cuentan con una definición clara desde la fuente. Sin embargo, la revisión inicial mostró que varias variables requerían tratamiento previo antes de ser utilizadas en etapas posteriores.

Los principales aspectos detectados fueron:

- presencia de variables categóricas codificadas con valores numéricos;
- alta fragmentación en algunas variables categóricas;
- redundancia entre algunas variables;
- y una inconsistencia puntual en una variable ordinal.

Debido a esto, fue necesario aplicar un proceso de limpieza y preparación para garantizar que el dataset quedara en condiciones apropiadas para su análisis.

---

## 3. Completitud

La completitud del dataset fue alta desde el inicio, ya que no se detectaron valores faltantes generalizados en las variables originales utilizadas. Durante el preprocesamiento, se generó un único valor faltante de manera controlada al detectar una inconsistencia en la variable `Application order`, donde se encontró un valor `0` en una variable cuyo orden esperado comienza en `1`.

Este caso fue tratado como faltante y posteriormente imputado utilizando la **moda** de la variable, debido a que correspondía a un único registro y no representaba una ausencia estructural de información.

Tras esta imputación, el dataset final quedó **sin valores faltantes** en las variables incluidas para etapas posteriores.

---

## 4. Consistencia

Se evaluó la consistencia del dataset tanto desde una perspectiva estructural como lógica.

### 4.1 Consistencia estructural

El dataset presenta columnas bien definidas y un formato homogéneo que permitió su lectura y manipulación sin errores de estructura. No se observaron problemas severos de formato, separadores o corrupción del archivo.

### 4.2 Consistencia lógica

Durante la revisión se identificaron algunos casos relevantes:

- La variable `Application order` presentaba un valor `0`, inconsistente con la lógica ordinal de la variable.
- La variable `Nacionality` transmitía en la práctica la misma información que `International`, generando redundancia.
- La variable `Daytime/evening attendance` estaba completamente determinada por `Course`, por lo que también generaba duplicación conceptual.
- Varias variables categóricas contenían muchas categorías con baja frecuencia, lo que complicaba su uso directo y hacía recomendable su reagrupación.

A partir de estas observaciones, se aplicaron transformaciones orientadas a mejorar la consistencia analítica del conjunto de datos.

---

## 5. Duplicados

Se realizó una verificación de registros duplicados exactos en el dataset. Esta revisión tuvo como objetivo detectar filas completamente repetidas que pudieran sesgar los análisis o inflar artificialmente la frecuencia de ciertos patrones.

En caso de no haberse encontrado duplicados, se puede concluir que:

> No se detectaron registros duplicados exactos en el conjunto de datos, lo que indica que cada observación representa un caso único a nivel de fila completa.

Esta verificación contribuye a asegurar la integridad básica del dataset.

---

## 6. Riesgos de calidad de datos

Aunque el dataset presenta una calidad general adecuada, existen algunos riesgos que deben considerarse al interpretar resultados y al avanzar hacia etapas posteriores del proyecto.

### 6.1 Variables desbalanceadas

Algunas variables binarias presentan una fuerte concentración en una sola categoría. Un ejemplo claro es `Educational special needs`, donde la gran mayoría de los registros pertenece a una sola clase. Esto puede limitar su capacidad explicativa y dificultar la interpretación de patrones asociados.

### 6.2 Redundancia entre variables

Se detectaron variables con información altamente solapada, como `Nacionality` con `International`, y `Daytime/evening attendance` con `Course`. Si estas relaciones no se controlan, pueden introducir ruido o duplicidad innecesaria en el análisis.

### 6.3 Categorías poco frecuentes

Varias variables categóricas contenían niveles muy específicos con pocos casos. Esto representa un riesgo porque puede generar una representación excesivamente fragmentada del dato, dificultando tanto la interpretación como la codificación posterior.

### 6.4 Dependencia del contexto

El dataset proviene de una fuente institucional y contexto académico específico. Por ello, algunas relaciones observadas podrían depender de características particulares de esa realidad educativa y no generalizarse automáticamente a otras instituciones o países.

---

## 7. Limitaciones del dataset

A pesar de ser útil para el análisis de deserción estudiantil, el dataset presenta limitaciones que deben ser explicitadas:

- corresponde a un contexto institucional específico, lo que limita la generalización directa de resultados;
- algunas variables administrativas pueden no existir o no comportarse igual en otros entornos educativos;
- la variable objetivo incluye la categoría `Enrolled`, que no representa necesariamente un estado final definitivo del estudiante;
- varias variables categóricas requirieron reagrupación, lo que mejora manejabilidad, pero reduce el nivel de detalle original;
- existen relaciones fuertes entre ciertas variables, por lo que algunas interpretaciones deben hacerse con precaución.

Estas limitaciones no invalidan el uso del dataset, pero sí deben considerarse al momento de extraer conclusiones.

---

## 8. Acciones de mejora aplicadas

Durante el preprocesamiento se aplicaron medidas concretas para mejorar la calidad del dataset:

- reagrupación de categorías en variables con alta fragmentación;
- identificación y corrección de una inconsistencia puntual en `Application order`;
- imputación justificada del único valor faltante generado durante la limpieza;
- eliminación de variables redundantes;
- selección de variables finales para análisis posterior;
- codificación de variables categóricas mediante **one-hot encoding**.

Estas acciones permitieron transformar el dataset en una versión más limpia, consistente y adecuada para etapas posteriores.

---

## 9. Conclusión

En conjunto, el dataset presenta una calidad suficiente para ser utilizado en un proyecto de ciencia de datos, siempre que se realice un preprocesamiento cuidadoso. La completitud fue alta, la consistencia general resultó adecuada y no se detectaron problemas estructurales severos. Sin embargo, sí fue necesario abordar fragmentación de categorías, redundancias e inconsistencias puntuales.

Luego de las transformaciones aplicadas, el conjunto de datos quedó preparado para continuar con etapas posteriores del proyecto, manteniendo trazabilidad de las decisiones tomadas y una base razonablemente sólida desde la perspectiva de calidad de datos.
