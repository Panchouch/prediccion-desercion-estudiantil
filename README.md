# 1. Formulación de la problemática, objetivos y KPIs

## Problemática

En las instituciones de educación superior, la deserción estudiantil representa un problema relevante, ya que impacta negativamente la trayectoria académica de los estudiantes, reduce los indicadores de retención y titulación, y dificulta la planificación eficiente de los recursos destinados a apoyo estudiantil.

Uno de los principales desafíos institucionales es la falta de mecanismos oportunos y basados en datos para identificar tempranamente a los estudiantes con mayor riesgo de abandonar sus estudios. Como resultado, muchas intervenciones se realizan de forma tardía, generalizada o poco focalizada, disminuyendo su efectividad.

Frente a esta situación, surge la necesidad de desarrollar un enfoque analítico que permita predecir el riesgo de deserción y apoyar la toma de decisiones en los procesos de seguimiento y retención estudiantil.

## Pregunta analítica

**¿En qué medida un modelo predictivo puede apoyar la detección temprana de estudiantes con riesgo de abandono para fortalecer la gestión de retención institucional?**

## Objetivo general

Desarrollar un modelo analítico que permita predecir el riesgo de deserción estudiantil a partir de variables académicas, personales y socioeconómicas, con el fin de apoyar la toma de decisiones en los procesos institucionales de retención y acompañamiento estudiantil.

## Objetivos específicos tipo SMART

- Identificar y depurar las variables del dataset que presentan mayor relación con la deserción estudiantil, durante la etapa de análisis exploratorio de datos.
- Analizar el comportamiento de variables académicas, demográficas y socioeconómicas para detectar patrones asociados al abandono, permanencia o graduación de los estudiantes.
- Construir y evaluar al menos un modelo de clasificación capaz de predecir el riesgo de deserción estudiantil con métricas de desempeño definidas previamente.
- Determinar las variables más influyentes en la predicción de la deserción, para generar información útil en la focalización de intervenciones institucionales.
- Proponer criterios de uso del modelo como apoyo a la gestión de retención estudiantil, considerando sus alcances y limitaciones.

## KPIs

- Recall de la clase `Dropout`
- F1-score de la clase `Dropout`
- Accuracy balanceado del modelo
- Porcentaje de estudiantes en riesgo correctamente identificados
- Nivel de interpretabilidad de las variables más influyentes

## Criterios de aceptación

- Recall de deserción igual o superior a 75%
- F1-score aceptable en la clase `Dropout`
- Identificación clara de variables clave asociadas a deserción
- Capacidad del modelo para apoyar decisiones de intervención temprana

## Justificación de los KPIs del proyecto

Para evaluar la propuesta, se seleccionaron indicadores que permiten medir no solo el desempeño técnico del modelo, sino también su utilidad dentro del problema de retención estudiantil. La elección de estos KPIs responde a la necesidad de priorizar la correcta detección de estudiantes con riesgo de deserción y generar resultados útiles para la toma de decisiones institucionales.

### Recall de la clase `Dropout`

Se prioriza este indicador porque, en este problema, resulta más importante identificar la mayor cantidad posible de estudiantes que realmente podrían desertar. Su utilidad radica en reducir los casos en que un estudiante en riesgo no es detectado por el modelo, lo que permitiría focalizar apoyos de manera más oportuna.

### F1-score de la clase `Dropout`

Se incorpora porque no basta con detectar muchos posibles desertores; también es necesario que esa detección mantenga un equilibrio razonable y no genere demasiadas alertas incorrectas. Este KPI es útil para evaluar si el modelo logra un desempeño consistente en la clase más relevante del problema.

### Accuracy balanceado del modelo

Se elige porque el problema presenta clases que no necesariamente están distribuidas de forma uniforme. Su utilidad está en ofrecer una evaluación más justa del rendimiento general del modelo, evitando que los resultados se vean sobreestimados por la clase con mayor frecuencia.

### Porcentaje de estudiantes en riesgo correctamente identificados

Se considera importante porque traduce el rendimiento del modelo a un lenguaje más comprensible desde la perspectiva organizacional. Su utilidad está en mostrar, de forma directa, cuántos estudiantes que efectivamente requerían atención fueron detectados por la solución propuesta.

### Interpretabilidad de las variables más influyentes

Se selecciona porque el objetivo del proyecto no es solo predecir, sino también comprender qué factores se asocian con la deserción. Su utilidad radica en aportar evidencia para orientar decisiones institucionales, permitiendo identificar variables académicas, personales o socioeconómicas que podrían ser abordadas mediante intervenciones tempranas.

## Criterios de aceptación del proyecto

Se considerará que la solución cumple con los requisitos del proyecto si alcanza un recall igual o superior al 75% en la clase `Dropout`, ya que esto aseguraría una capacidad adecuada para detectar estudiantes en riesgo. Además, deberá presentar un F1-score satisfactorio en esa misma clase, de modo que la detección de desertores no se realice a costa de un número excesivo de clasificaciones erróneas.

También se espera que el análisis permita una identificación clara de variables relevantes asociadas a la deserción, con el fin de entregar hallazgos útiles para la comprensión del fenómeno. Finalmente, el modelo deberá demostrar que sus resultados pueden apoyar decisiones de intervención temprana, aportando valor al proceso institucional de retención estudiantil.

---

# 2. Selección, carga y pertinencia del dataset

Para este proyecto se seleccionó el dataset **“Predict Students' Dropout and Academic Success”** del repositorio **UCI Machine Learning Repository**, debido a su relación directa con la problemática de la deserción estudiantil.

Este conjunto de datos contiene **4424 registros**, donde cada fila representa a un estudiante, e incluye **36 variables predictoras** asociadas a antecedentes académicos, factores demográficos, condiciones socioeconómicas y desempeño durante el primer y segundo semestre.

Su pertinencia radica en que la variable objetivo clasifica a los estudiantes en **`dropout`**, **`enrolled`** y **`graduate`**, lo que permite analizar y predecir el riesgo de abandono académico. Además, las variables incluidas son coherentes con el problema planteado, ya que entregan información relevante para identificar patrones asociados a la deserción y apoyar decisiones de retención estudiantil.

En cuanto a la carga, el dataset puede ser utilizado en formato **CSV** o mediante herramientas de Python, lo que facilita su integración en el proceso de análisis. Como principal restricción, se debe considerar que corresponde a un dataset académico previamente procesado y con desbalance de clases, por lo que los resultados deben interpretarse dentro de ese contexto.

En síntesis, se trata de un dataset pertinente, suficiente y técnicamente justificable, ya que su contenido, cobertura y estructura se ajustan de manera adecuada al objetivo de predecir la deserción estudiantil.
