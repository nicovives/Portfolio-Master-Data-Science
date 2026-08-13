# 📊 Análisis Exploratorio de Datos (EDA): Criminalidad en la Ciudad de Los Ángeles

## 📖 Contexto del Proyecto
Este proyecto presenta un **Análisis Exploratorio de Datos (EDA)** exhaustivo sobre el conjunto de datos públicos de incidentes criminales registrados en la ciudad de Los Ángeles.

El objetivo principal es transformar datos policiales crudos en información de valor (insights) mediante la aplicación de técnicas de limpieza, análisis estadístico descriptivo y visualización avanzada, documentando cada decisión tomada durante el ciclo de vida del dato para entender los patrones delictivos de la ciudad.

## 🗂️ Origen y Naturaleza de los Datos
El dataset seleccionado destaca por su complejidad y riqueza estructural, permitiendo un análisis criminológico multidimensional:
- **Fuente:** Catálogo de Datos Abiertos (Open Data / Data.gov).
- **Tipología:** Combinación de variables categóricas (tipo de delito, arma utilizada), numéricas (coordenadas espaciales, edad de la víctima) y datos temporales (fecha y hora del incidente).

## 🛠️ Stack Tecnológico
- **Lenguaje:** Python
- **Manipulación de Datos:** `pandas`, `numpy`
- **Visualización:** `matplotlib`, `seaborn`
- **Entorno:** Jupyter Notebooks / Kaggle

## 🔬 Pipeline Analítico

El desarrollo del proyecto sigue una metodología estructurada en 4 fases clave:

### 1. Data Preprocessing & Feature Engineering
- **Limpieza de datos (Data Cleaning):** Tratamiento de valores nulos (como armas no identificadas o edades desconocidas) y detección de errores de tipiado en los registros policiales.
- **Transformación:** Conversión y estandarización de tipos de datos, prestando especial atención al parseo de fechas y horas.
- **Ingeniería de variables:** Extracción de nuevas características temporales (día de la semana, franja horaria) para optimizar el análisis de tendencias.

### 2. Análisis Estadístico Descriptivo
- Análisis univariante y bivariante para entender la demografía de las víctimas y la frecuencia de los distintos tipos de delitos.
- Evaluación de métricas de tendencia central y medidas de dispersión en variables cuantitativas.

### 3. Análisis de Series Temporales
- Detección de patrones temporales, analizando la evolución histórica de la criminalidad y la estacionalidad de ciertos delitos a lo largo del año.

### 4. Visualización Avanzada de Datos
- Creación de un dashboard narrativo de gráficas (histogramas, heatmaps de correlación espacio-temporal, gráficas de barras) priorizando la calidad, variedad y legibilidad para comunicar eficazmente las zonas y momentos de mayor riesgo.

## 💡 Conclusiones y Business Insights
Tras el procesamiento y análisis de los datos, se han extraído las siguientes conclusiones clave sobre la criminalidad en Los Ángeles:
- **Patrones Temporales:** Existe una clara estacionalidad, con repuntes específicos de incidentes durante ciertas franjas horarias nocturnas y días concretos de la semana.
- **Tipología de Delitos:** Los delitos contra la propiedad (como hurtos y robos de vehículos) representan un volumen significativamente mayor en comparación con los delitos violentos.
- **Distribución Demográfica:** El análisis bivariante revela correlaciones importantes entre el tipo de delito sufrido y los grupos de edad de las víctimas.
- **Concentración Espacial:** El mapeo de los incidentes confirma la existencia de "hotspots" o áreas calientes con una densidad criminal superior a la media del resto de distritos.

## 🤖 Transparencia y Uso de IA
Como parte de las buenas prácticas de desarrollo, se ha utilizado Inteligencia Artificial Generativa como herramienta de asistencia en este proyecto:
- Se ha empleado **ChatGPT** para asistir en la refactorización y optimización de funciones de limpieza de datos con Pandas.
- Se utilizó el prompt *"Revisa y corrige la gramática de este documento"* para asegurar la calidad estilística y ortográfica de las conclusiones redactadas en el notebook.

---
*Análisis Exploratorio de Datos desarrollado originalmente como notebook interactivo en Kaggle para el Máster en Ciencia de Datos.*