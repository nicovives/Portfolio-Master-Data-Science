# 🏙️ AI-Driven Urban Architecture Analysis: Expanding OpenFACADES

## 📖 Contexto del Proyecto
El análisis morfológico y arquitectónico a escala urbana ha dependido tradicionalmente de un costoso y lento trabajo de campo manual. Las bases de datos espaciales (GIS) convencionales carecen de la granularidad visual necesaria a nivel de calle. 

Para resolver este desafío, este proyecto adapta, expande y optimiza el *framework* de código abierto **OpenFACADES**. Mediante la integración de Imágenes a Nivel de Calle (SVI - *Street View Imagery*) y Modelos de Visión-Lenguaje (VLMs) avanzados, se ha desarrollado un pipeline de catalogación automatizada de fachadas. El sistema se ha puesto a prueba en un estudio comparativo a gran escala de cuatro metrópolis globales: **Madrid, París, Ámsterdam y Nueva York (Manhattan)**.

## 🛠️ Stack Tecnológico
- **Fuentes de Datos (SVI):** Mapillary API
- **Computer Vision (Zero-Shot Detection):** GroundingDINO
- **Vision-Language Models (VLM):** InternVL
- **Procesamiento de Datos y GIS:** Python, Pandas, JSON Parsing, Análisis Geoespacial.

## ⚙️ Arquitectura del Pipeline y Mejoras de Ingeniería

El proyecto no solo implementa el modelo base, sino que introduce mejoras arquitectónicas críticas para habilitar la extracción masiva de datos estructurados:

1. **Pre-filtrado y Aislamiento de Fachadas:** Implementación de un sistema de filtrado previo de estructuras antes de aplicar el modelo de detección *Zero-Shot* (GroundingDINO), aislando con precisión geométrica las fachadas del entorno.
2. **Split-Prompt Engineering (Inferencia VLM):** Para extraer métricas complejas sin saturar la ventana de contexto de **InternVL**, se diseñó una estrategia de *prompts* divididos. Esto permitió no solo extraer características morfológicas, sino emular el etiquetado humano en percepción estética (evaluando *complejidad, originalidad, monotonía, orden y atractivo*).
3. **Robustez Predictiva (JSON Recovery System):** Debido a la naturaleza probabilística y alucinaciones sintácticas inherentes a los LLMs/VLMs, se desarrolló un algoritmo de postprocesamiento y corrección de formato. Este módulo logró **recuperar con un 95,12% de éxito** los JSON corruptos generados por el modelo, consolidando un dataset final robusto de **2.400 registros arquitectónicos válidos**.

## 📊 Resultados y Business Insights (EDA)
El Análisis Exploratorio de Datos reveló profundas divergencias estructurales y estéticas entre el urbanismo americano y el europeo:

- 🇺🇸 **La Anomalía de Manhattan:** Destaca por un tejido arquitectónico dominado por estructuras comerciales modernas, una altísima varianza en altura y fuertes contrastes estéticos en sus edificaciones corporativas e industriales.
- 🇪🇺 **El Modelo de "Ciudad Mixta" Europea:**
  - **Ámsterdam:** Identificada por la IA por su masiva presencia de ladrillo visto y una densidad inusualmente alta de ventanas por fachada.
  - **París:** Dominancia clara de elementos del clasicismo y uniformidad estética (orden).
  - **Madrid:** Fuerte prevalencia de arquitecturas tradicionales locales y patrones morfológicos consistentes.

## 💡 Impacto
Este proyecto demuestra la viabilidad técnica y el enorme ahorro de costes de integrar **Inteligencia Artificial Generativa** con **Sistemas de Información Geográfica (GIS)**. Permite extraer información semántica y estética profunda de entornos urbanos a escala masiva, eliminando la necesidad de encuestas manuales y abriendo nuevas vías para el urbanismo inteligente (*Smart Cities*).

---
*Investigación y desarrollo aplicados al cruce entre Inteligencia Artificial, Computer Vision y Urban Analytics.*