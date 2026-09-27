# Análisis del Perfil de Salud en EE.UU.: Modelado Predictivo y Segmentación

## Contexto del Proyecto
El sistema de salud y el estilo de vida en Estados Unidos presentan dinámicas complejas que impactan directamente en el bienestar de su población. Este proyecto de **Machine Learning** tiene como objetivo analizar el perfil de salud de los estadounidenses para extraer patrones ocultos, predecir indicadores médicos y segmentar a la población según sus características de salud.

A través de un pipeline analítico completo, se aplican técnicas de aprendizaje supervisado (Regresión y Clasificación) y no supervisado (Clustering), haciendo especial énfasis en la interpretabilidad de los modelos y el análisis de posibles sesgos en los datos médicos.

## Origen y Naturaleza de los Datos
Para abarcar la complejidad del problema, se han procesado conjuntos de datos multidimensionales que cumplen con los siguientes criterios estructurales:
- **Volumen y Diversidad:** Múltiples variables demográficas, biométricas y de estilo de vida.
- **Dimensionalidad:** Espacio de características superior a 4 dimensiones para los modelos predictivos, y superior a 3 dimensiones para el análisis de clustering.
- **Variable Objetivo (Target):** Definición de una variable multiclase (mínimo 3 categorías, ej. *Nivel de Riesgo de Salud: Bajo, Medio, Alto*) para las tareas de clasificación.

## 🛠️ Stack Tecnológico
- **Lenguaje:** Python
- **Machine Learning:** `scikit-learn` (Árboles de Decisión, Ensembles, Clustering).
- **Manipulación de Datos:** `pandas`, `numpy`
- **Visualización:** `matplotlib`, `seaborn` (Curvas ROC, Matrices de Confusión, Visualización de Árboles).
- **Entorno:** Jupyter Notebooks / Kaggle

---

# Health Profile Analysis in the USA: Predictive Modeling and Segmentation

## Project Context

The healthcare system and lifestyle in the United States present complex dynamics that directly impact the well-being of its population. This **Machine Learning** project aims to analyze the health profile of Americans to extract hidden patterns, predict medical indicators, and segment the population based on their health characteristics.

Through a complete analytical pipeline, supervised (Regression and Classification) and unsupervised (Clustering) learning techniques are applied, with special emphasis on model interpretability and the analysis of potential biases in medical data.

## Origin and Nature of the Data

To encompass the complexity of the problem, multidimensional datasets have been processed that meet the following structural criteria:

* **Volume and Diversity:** Multiple demographic, biometric, and lifestyle variables.
* **Dimensionality:** Feature space greater than 4 dimensions for predictive models, and greater than 3 dimensions for clustering analysis.
* **Target Variable:** Definition of a multiclass variable (minimum 3 categories, e.g., *Health Risk Level: Low, Medium, High*) for classification tasks.

## 🛠️ Technology Stack

* **Language:** Python
* **Machine Learning:** `scikit-learn` (Decision Trees, Ensembles, Clustering).
* **Data Manipulation:** `pandas`, `numpy`
* **Visualization:** `matplotlib`, `seaborn` (ROC Curves, Confusion Matrices, Tree Visualization).
* **Environment:** Jupyter Notebooks / Kaggle
