# 🏥 Análisis del Perfil de Salud en EE.UU.: Modelado Predictivo y Segmentación

## 📖 Contexto del Proyecto
El sistema de salud y el estilo de vida en Estados Unidos presentan dinámicas complejas que impactan directamente en el bienestar de su población. Este proyecto de **Machine Learning** tiene como objetivo analizar el perfil de salud de los estadounidenses para extraer patrones ocultos, predecir indicadores médicos y segmentar a la población según sus características de salud.

A través de un pipeline analítico completo, se aplican técnicas de aprendizaje supervisado (Regresión y Clasificación) y no supervisado (Clustering), haciendo especial énfasis en la interpretabilidad de los modelos y el análisis de posibles sesgos en los datos médicos.

## 🗂️ Origen y Naturaleza de los Datos
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

## 🔬 Pipeline Analítico y Metodología

El proyecto está estructurado en tres fases técnicas principales:

### 1. Preprocesamiento e Ingeniería de Datos
- **Data Cleaning & Imputation:** Tratamiento exhaustivo de valores nulos y atípicos (outliers) en registros médicos.
- **Feature Engineering:** Selección y extracción de características, aplicación de diferentes escaladores (StandardScaler, MinMaxScaler) para evaluar su impacto en el rendimiento algorítmico.

### 2. Aprendizaje Supervisado: Regresión y Clasificación
- **Regresión:** Predicción de indicadores continuos de salud (ej. Índice de Masa Corporal o gasto médico) utilizando Árboles de Decisión como modelo base.
- **Clasificación Multiclase:** Categorización del estado de salud de los pacientes. 
- **Interpretabilidad:** Análisis profundo de la estructura de los Árboles de Decisión, interpretando los nodos y las reglas de partición generadas.

### 3. Modelado Avanzado: Ensembles y Clustering
- **Ensembles:** Implementación de modelos combinados (ej. Random Forest, Gradient Boosting) para la tarea de clasificación multiclase, buscando superar las limitaciones de los árboles individuales.
- **Clustering (No Supervisado):** Segmentación de la población estadounidense en grupos homogéneos basados en sus similitudes biométricas y de estilo de vida, sin etiquetas previas.

## 📊 Evaluación de Modelos e Insights
El valor diferencial de este proyecto radica en la evaluación crítica de los resultados:
- **Métricas de Rendimiento:** Interpretación detallada de errores (MSE/RMSE en regresión), Matrices de Confusión y Curvas ROC multiclase.
- **Comparativa de Algoritmos:** Contraste de resultados entre los modelos simples y los ensembles, analizando cómo varía la **importancia de las variables (Feature Importance)** dependiendo del algoritmo utilizado.
- **Análisis de Relaciones:** Extracción de conclusiones holísticas que conectan los descubrimientos del clustering con las reglas de decisión de los clasificadores.
- **Análisis de Sesgos (Bias):** Evaluación crítica sobre posibles sesgos demográficos o socioeconómicos presentes en el dataset y cómo estos afectan a las predicciones de salud, un factor crucial en *Healthcare Analytics*.

---
*Proyecto de Machine Learning enfocado en Healthcare Data Science, desarrollado originalmente como notebook interactivo para el análisis avanzado de datos.*