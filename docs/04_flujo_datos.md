# Flujo de datos del proyecto

## 1. Objetivo del flujo de datos

Este documento describe el flujo de datos seguido en el proyecto de análisis del dataset **Predict Students’ Dropout and Academic Success**, desde la obtención de la fuente original hasta la generación del conjunto de datos preparado para etapas posteriores del análisis.

El propósito de este flujo es asegurar trazabilidad, orden en las transformaciones y reproducibilidad del proceso.

---

## 2. Etapas del flujo de datos

### 2.1 Fuente de datos

La fuente original del proyecto corresponde al dataset **Predict Students’ Dropout and Academic Success**, obtenido desde el repositorio **UCI Machine Learning Repository**.

En esta etapa los datos se encuentran en su estado original, sin modificaciones realizadas por el equipo de trabajo.

---

### 2.2 Ingesta

La ingesta corresponde a la descarga del archivo y su posterior carga en el entorno de trabajo mediante Python y pandas.

En esta fase se realiza:
- lectura del archivo CSV,
- verificación de dimensiones,
- revisión de nombres de columnas,
- inspección general de tipos de datos.

La ingesta permite incorporar el dataset al entorno de análisis sin modificar aún su contenido.

---

### 2.3 Staging

La etapa de **staging** funciona como una zona temporal de inspección inicial. Aquí se examinan los datos para comprender su estructura y detectar posibles problemas antes de aplicar transformaciones definitivas.

En esta fase se revisan aspectos como:
- tipos de variables,
- categorías existentes,
- valores únicos,
- posibles inconsistencias,
- presencia de valores faltantes,
- duplicados,
- distribución de variables relevantes.

Esta etapa permite diagnosticar el estado del dataset antes de pasar a una limpieza formal.

---

### 2.4 Raw

La capa **raw** corresponde a la versión original del dataset, preservada sin modificaciones.

Su propósito es mantener una referencia estable del archivo tal como fue obtenido desde la fuente. Esto permite:
- volver al estado inicial si es necesario,
- comparar versiones transformadas,
- asegurar trazabilidad en el proyecto.

Ejemplo:
- `data/raw/data.csv`

---

### 2.5 Curated

La capa **curated** corresponde a una versión depurada y organizada del dataset, luego de aplicar decisiones de preprocesamiento.

En esta etapa se realizan transformaciones como:
- tratamiento de inconsistencias,
- imputación justificada de valores faltantes,
- reagrupación de categorías,
- eliminación de redundancias,
- selección de variables relevantes.

Aquí los datos ya no están “crudos”, sino corregidos y preparados para un uso analítico más consistente.

Ejemplo:
- `data/curated/data_curated.csv`

---

### 2.6 Procesamiento

La etapa de **procesamiento** corresponde a la transformación final de los datos para etapas posteriores del proyecto.

En este trabajo, esta fase incluye:
- codificación de variables categóricas mediante **one-hot encoding**,
- construcción del dataset final de modelado,
- separación lógica entre variables categóricas, binarias, ordinales y numéricas.

El resultado es un dataset estructurado para ser utilizado posteriormente en tareas de análisis más avanzadas o modelado.

Ejemplo:
- `data/processed/df_model.csv`

---

### 2.7 Consumo

La capa de **consumo** corresponde al uso final de los datos procesados en el proyecto.

En este caso, el consumo contempla:
- análisis posteriores,
- construcción de visualizaciones,
- interpretación de variables,
- preparación para modelado,
- documentación de hallazgos y conclusiones.

Esta etapa representa el punto en que el dataset deja de ser solo un insumo técnico y pasa a ser utilizado para generar conocimiento útil dentro del proyecto.

---

## 3. Diagrama del flujo de datos

```text
[Fuente: UCI Repository]
        ↓
[Ingesta: descarga y carga en pandas]
        ↓
[Staging: inspección inicial y validación]
        ↓
[Raw: dataset original sin modificaciones]
        ↓
[Curated: limpieza, recodificación, imputación y selección]
        ↓
[Procesamiento: one-hot encoding y construcción de df_model]
        ↓
[Consumo: análisis posterior, interpretación y uso del dataset]