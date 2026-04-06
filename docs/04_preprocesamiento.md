# Resumen del preprocesamiento de datos

## 1. Objetivo del preprocesamiento

El preprocesamiento tuvo como objetivo preparar el dataset para etapas posteriores del proyecto, asegurando una estructura más limpia, consistente y adecuada para análisis futuros. Para ello, se trabajó sobre variables categóricas, binarias, numéricas y ordinales, aplicando transformaciones justificadas según la naturaleza de cada caso.

---

## 2. Revisión y tratamiento de variables

Durante esta etapa se revisaron las variables del dataset para decidir si debían:

- mantenerse en su formato original;
- reagruparse;
- eliminarse por redundancia;
- imputarse en caso de inconsistencia;
- o codificarse para su uso posterior.

### 2.1 Variables categóricas reagrupadas

Se reagruparon las siguientes variables debido a la alta fragmentación de categorías o a la existencia de niveles con muy baja frecuencia:

- `Mother's qualification`
- `Father's qualification`
- `Previous qualification`
- `Mother's occupation`
- `Father's occupation`
- `Marital status`
- `Application mode`

Además, se creó una versión agrupada de `Course` con fines comparativos e interpretativos, aunque para el conjunto final de modelado se decidió conservar la variable `Course` original.

La reagrupación permitió reducir la dispersión de categorías y obtener variables más manejables e interpretables.

---

## 3. Redundancias identificadas

Se detectaron variables que transmitían información repetida o altamente solapada.

### 3.1 `Nacionality` e `International`

Se observó que `Nacionality` resultaba equivalente, en la práctica, a `International`, ya que la nacionalidad portuguesa coincidía con estudiantes no internacionales y el resto de las nacionalidades con estudiantes internacionales. Por esta razón, se decidió eliminar `Nacionality` y conservar `International`.

### 3.2 `Course` y `Daytime/evening attendance`

Se detectó que la variable `Daytime/evening attendance` estaba completamente determinada por `Course`, ya que ciertas carreras aparecían únicamente en una modalidad horaria específica. Por ello, esta variable fue considerada redundante respecto de `Course` y se excluyó del conjunto final destinado a etapas posteriores.

---

## 4. Tratamiento de inconsistencias y valores faltantes

Se identificó una inconsistencia en la variable `Application order`, donde apareció un valor `0`, a pesar de que esta variable representa un orden de preferencia que lógicamente debería comenzar en `1`.

Este valor se consideró anómalo y fue transformado en faltante. Posteriormente, dado que correspondía a un único caso y que la variable es de naturaleza ordinal, se imputó utilizando la moda de la variable.

Con esta decisión, se resolvió la inconsistencia sin afectar de manera relevante la distribución general del dataset.

---

## 5. Variables mantenidas sin transformación estructural

Algunas variables se mantuvieron en su formato original porque ya presentaban una estructura adecuada para el análisis.

### 5.1 Variables binarias
Se mantuvieron sin modificaciones las variables binarias:

- `Displaced`
- `Educational special needs`
- `Debtor`
- `Tuition fees up to date`
- `Gender`
- `Scholarship holder`
- `International`

En estos casos no se aplicó recodificación adicional, ya que ya se encontraban representadas de forma adecuada como variables binarias.

### 5.2 Variables numéricas y ordinales
También se conservaron en su formato original variables como:

- `Application order`
- `Previous qualification (grade)`
- `Admission grade`
- `Age at enrollment`
- variables académicas de primer y segundo semestre
- `Unemployment rate`
- `Inflation rate`
- `GDP`

Estas variables se mantuvieron sin agrupación para evitar pérdida innecesaria de información.

---

## 6. Selección final de variables

Una vez aplicadas las decisiones anteriores, se definió un conjunto final de variables para las etapas posteriores del proyecto. En este proceso se conservaron:

- variables numéricas continuas;
- variables binarias;
- variables ordinales;
- versiones agrupadas de variables categóricas seleccionadas;
- y la variable `Course` original.

Asimismo, se eliminaron del dataset final las versiones originales de variables ya reagruparon, así como aquellas columnas consideradas redundantes.

---

## 7. Codificación de variables categóricas

Como parte del cierre del preprocesamiento, se aplicó **one-hot encoding** a las variables categóricas nominales seleccionadas. Esto permitió transformar dichas variables en una representación numérica adecuada para etapas posteriores, evitando imponer un orden artificial entre categorías.

Las variables binarias se mantuvieron en formato `0/1`, mientras que las variables numéricas y ordinales conservaron su escala original.

---

## 8. Resultado final del preprocesamiento

Como resultado del proceso, se obtuvo un dataset:

- limpio;
- consistente;
- sin valores faltantes pendientes;
- con redundancias controladas;
- y con variables categóricas correctamente codificadas.

De esta forma, el conjunto de datos quedó preparado para continuar con etapas posteriores del proyecto, manteniendo trazabilidad sobre las decisiones tomadas y coherencia con los objetivos del análisis.

---

## 9. Conclusión

El preprocesamiento permitió transformar un dataset inicialmente útil, pero con categorías fragmentadas, variables redundantes y una inconsistencia puntual, en una versión más robusta y adecuada para su análisis posterior. Las decisiones tomadas fueron coherentes con la naturaleza de las variables y estuvieron orientadas a mejorar la calidad, interpretabilidad y usabilidad del conjunto de datos.
