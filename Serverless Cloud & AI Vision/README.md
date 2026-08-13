# 🏙️ Smart Lighting System (SLS) | Serverless Cloud & AI Vision

## 📖 Contexto del Proyecto
Este proyecto desarrolla una arquitectura de datos e Inteligencia Artificial para una iniciativa de **Smart City**. El objetivo es implementar un Sistema de Iluminación Inteligente (SLS) que optimice el consumo energético de la ciudad controlando dinámicamente el encendido y apagado de las luminarias en función de la presencia en tiempo real de peatones y vehículos.

Para ello, se ha diseñado un pipeline que captura flujos de vídeo de cámaras de tráfico, procesa los fotogramas (frames) mediante modelos de Visión por Computador para detectar entidades, y expone los resultados en un panel de control estático. 

El proyecto evoluciona desde un MVP de procesamiento en el Edge (Local) hacia una **Arquitectura Cloud Serverless** altamente escalable.

## 📊 Fuentes de Datos
- **Input:** Flujos continuos de vídeo en tiempo real (RTSP/HTTP) procedentes de webcams públicas de tráfico y seguridad.
- **Output Analítico:** Datos estructurados (CSV/JSON) con marcas temporales (timestamps), recuento de entidades (personas/vehículos) y metadatos espaciales (Bounding Boxes) para la visualización del frame procesado.

## 🛠️ Stack Tecnológico
- **Cloud Provider:** Microsoft Azure
- **Computación Serverless:** Azure Functions (Blob Triggers)
- **Servicios Cognitivos/IA:** Azure AI Services (Computer Vision API), Ultralytics YOLOv8 (para la fase Edge/Local)
- **Almacenamiento:** Azure Blob Storage (Data Lake para imágenes raw y procesadas)
- **Frontend / Visualización:** HTML5, JavaScript, Chart.js (Hosteado como Azure Static Website)
- **Lenguaje Principal:** Python

## 🏗️ Arquitectura y Fases de Desarrollo

### Fase 1: MVP en Edge (Procesamiento Local)
Desarrollo inicial para validar la viabilidad del modelo de IA en máquinas locales actuando como nodos Edge.
1. **Captura:** Extracción de frames cada 5 segundos del flujo de vídeo.
2. **Inferencia Local:** Uso del modelo **YOLOv8** para detección de objetos, clasificación y dibujo de *bounding boxes* sobre los peatones.
3. **Persistencia y Dashboard:** Almacenamiento del conteo en un CSV local y renderizado en un dashboard HTML/JS estático para monitorizar la evolución temporal.

### Fase 2: Migración a Arquitectura Serverless (Cloud)
Despliegue del procesamiento intensivo en la nube de Azure para garantizar escalabilidad, pagando solo por el tiempo de cómputo consumido.
1. **Ingesta Continua:** Script de captura ligero en el nodo local que envía imágenes raw a un contenedor de **Azure Blob Storage** con alta frecuencia (cada 0.5s).
2. **Procesamiento Orientado a Eventos:** Una **Azure Function** (configurada con un *Blob Trigger*) se activa automáticamente ante la subida de un nuevo frame.
3. **Inferencia Cloud:** La función consume la API de **Azure AI Computer Vision** para etiquetar la imagen, contar entidades y extraer las coordenadas de los *bounding boxes*.
4. **Almacenamiento Desacoplado:** Para evitar ejecuciones recursivas y sobrecostes, los frames procesados y los datos tabulares se escriben en un contenedor independiente que alimenta directamente a la página web estática alojada en Azure.

## 🚀 Optimizaciones y Features Avanzadas
Para mejorar la eficiencia y precisión del sistema en un entorno de producción real, se han implementado/propuesto las siguientes mejoras:
- **Object Tracking:** Implementación de seguimiento de IDs únicos entre frames consecutivos para evitar el doble conteo de una misma persona cruzando la calle.
- **Detección Multiclase:** Ampliación del modelo para identificar no solo peatones, sino también vehículos, permitiendo reglas de iluminación más complejas.
- **Eficiencia de Ancho de Banda y Costes:**
  - Integración de técnicas de detección de movimiento (Motion Detection) previas al envío a la nube, enviando fotogramas **solo** cuando hay cambios significativos.
  - Compresión dinámica y ajuste de resolución mínima que garantice la precisión de la API de Azure reduciendo la latencia de red.
- **Monitorización de Rendimiento:** Tracking de KPIs de la arquitectura Cloud (tiempo de respuesta de la API de Azure, eficiencia de detección frente al modelo YOLO, y coste monetario por cada 1.000 invocaciones).

---
*Este proyecto ha sido desarrollado como prueba de concepto para arquitecturas Serverless e integración de IA en el ámbito del Big Data y el IoT.*