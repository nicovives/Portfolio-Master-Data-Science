# 🏖️ Urban Analytics & Data Mining Torrevieja Smart Destination

## 📖 Contexto del Proyecto
La gestión de un destino turístico residencial como Torrevieja requiere trascender la intuición para tomar decisiones basadas en datos. Este proyecto aplica metodologías de Minería de Datos (Data Mining) y análisis descriptivo para abordar cuatro retos estratégicos clave de la ciudad. 

El objetivo no es solo responder a preguntas de negocio mediante fuentes de datos abiertos (Open Data), sino también evaluar de forma crítica las limitaciones de las fuentes actuales y proponer una estrategia de ingesta de nuevos datos para el futuro.

## 🎯 Objetivos Estratégicos (Retos)
El análisis se divide en cuatro ejes temáticos fundamentales para comprender la presión y el desarrollo del destino

1. Población Real (Demanda Efectiva) Estimación de la población flotante más allá de los registros del padrón, midiendo la carga real de personas en el municipio utilizando, entre otros, datos de movilidad basados en telefonía móvil.
2. Análisis de Estacionalidad Caracterización temporal de la presión turística. Identificación de picos, valles e impacto socioeconómico en la ciudad cruzando datos de ocupación, empleo y variables meteorológicas.
3. Viviendas de Uso Turístico (VUT) Análisis espacial y temporal de la oferta de alojamiento turístico. Se estudia su concentración en determinadas áreas urbanas, cruzando registros oficiales de turismo con datos catastrales.
4. Sostenibilidad y Cohesión Social Evaluación de indicadores de presión sobre los recursos municipales (agua, residuos) e impacto en la cohesión social (renta, criminalidad) debido al modelo residencial-turístico intensivo.

## 🛠️ Stack Metodológico y Tecnológico
- Dominio Urban Analytics, Tourism Data Science.
- Técnicas aplicadas EDA (Análisis Exploratorio de Datos), Análisis Espacial, Análisis de Series Temporales.
- Herramientas de Análisis Python (Pandas, GeoPandas, Matplotlib, Seaborn)  R.
- Entregables Informes de resultados, cuadros de mando y propuesta estratégica de Data Governance.

## 🗂️ Fuentes de Datos Abiertos (Open Data) Integradas
Para construir los modelos analíticos, se ha extraído, limpiado e integrado información de múltiples orígenes oficiales

- Movilidad y Demografía [INE Experimental (Telefonía Móvil)](httpswww.ine.esexperimentalturismo_movilesexperimental_turismo_moviles.htm), Censo de Población (INE), Institut Valencià d’Estadística.
- Turismo y Empleo [Registro de VUTs de la GVA](httpscindi.gva.eseswebturismellistat-oficial-empreses-turistiques), Informes de Ocupación Hotelera, Datos de paro registrado (SEPELabora).
- Urbanismo y Clima [Sede Electrónica del Catastro](httpswww.sedecatastro.gob.es), AEMET OpenData API.
- Medioambiente y Sociedad MITECO, Náyade (calidad de playas), SINAC, Portal Estadístico de Criminalidad (Ministerio del Interior), Atlas de Distribución de Renta de los Hogares (INE).

## 🚀 Limitaciones y Propuesta Estratégica (Data Strategy)
El verdadero valor de la analítica de datos en Smart Cities reside en conocer los límites de la información. Como parte integral de este proyecto, se ha desarrollado un Gap Analysis
- Identificación de preguntas críticas (por ejemplo, presión exacta sobre redes de saneamiento locales) que no pueden resolverse con la granularidad temporal o espacial del Open Data actual.
- Diseño de un roadmap de recolección de datos Propuestas para la instalación de sensórica IoT, convenios institucionales y encuestas dirigidas que permitan a la administración un monitoreo en tiempo real del destino turístico.

---
Proyecto integral de Minería de Datos enfocado a la toma de decisiones estratégicas y desarrollo sostenible en destinos turísticos inteligentes.