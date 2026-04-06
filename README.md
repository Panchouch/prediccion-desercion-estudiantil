# Proyecto de Ciencia de Datos: Deserción Estudiantil

## 1. Descripción del proyecto

Este proyecto aborda el análisis de un dataset de deserción estudiantil en educación superior, con el propósito de identificar factores académicos, administrativos y sociodemográficos asociados a la permanencia, graduación o abandono de los estudiantes.

El trabajo se desarrolló siguiendo una lógica de ciencia de datos que incluye selección del dataset, análisis exploratorio, preprocesamiento, evaluación de calidad de datos y documentación del flujo reproducible de transformación.

## 2. Problemática abordada

La deserción estudiantil constituye una problemática relevante dentro de la gestión de permanencia y retención en educación superior. Comprender los factores asociados a este fenómeno resulta útil tanto para interpretar el comportamiento de los estudiantes como para apoyar futuras decisiones institucionales orientadas a la continuidad académica.

## 3. Objetivo general

Analizar variables académicas, administrativas y sociodemográficas para identificar factores asociados a la deserción, permanencia y graduación de estudiantes de educación superior.

## 4. Dataset utilizado

Se utilizó el dataset **Predict Students’ Dropout and Academic Success**, obtenido desde el repositorio **UCI Machine Learning Repository**.

Este conjunto de datos contiene 4424 registros e incluye variables relacionadas con:

- antecedentes académicos;
- características personales;
- situación administrativa;
- desempeño en primer y segundo semestre;
- estado final del estudiante (`Dropout`, `Enrolled`, `Graduate`).

## Ejecución
1. Abrir el notebook en Google Colab o Jupyter Notebook.
2. Instalar las dependencias necesarias.
3. Ejecutar las celdas en orden.

## Dependencias
- Python 3
- pandas
- numpy
- matplotlib
- seaborn
- scikit-learn
- ucimlrepo

## Autores
- Francisco Espinoza
- Felipe Chavez

## 5. Estructura del repositorio

```text
proyecto-desercion-estudiantil/
│
├── README.md
├── data/
│   └── data.csv
│
├── notebooks/
│   └── eda_preprocesamiento.ipynb
│
└── docs/
    ├── 01_problematicas_objetivos_kpis.md
    ├── 02_dataset_pertinencia.md


    ├── 03_data_quality_report.md
    └── 04_data_flow.md
