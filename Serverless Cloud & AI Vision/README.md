# Smart Lighting System (SLS) | Serverless Cloud & AI Vision

## Contexto del Proyecto
Este proyecto desarrolla una arquitectura de datos e Inteligencia Artificial para una iniciativa de **Smart City**. El objetivo es implementar un Sistema de Iluminación Inteligente (SLS) que optimice el consumo energético de la ciudad controlando dinámicamente el encendido y apagado de las luminarias en función de la presencia en tiempo real de peatones y vehículos.

Para ello, se ha diseñado un pipeline que captura flujos de vídeo de cámaras de tráfico, procesa los fotogramas (frames) mediante modelos de Visión por Computador para detectar entidades, y expone los resultados en un panel de control estático. 

El proyecto evoluciona desde un MVP de procesamiento en el Edge (Local) hacia una **Arquitectura Cloud Serverless** altamente escalable.

## Fuentes de Datos
- **Input:** Flujos continuos de vídeo en tiempo real (RTSP/HTTP) procedentes de webcams públicas de tráfico y seguridad.
- **Output Analítico:** Datos estructurados (CSV/JSON) con marcas temporales (timestamps), recuento de entidades (personas/vehículos) y metadatos espaciales (Bounding Boxes) para la visualización del frame procesado.

## 🛠️ Stack Tecnológico
- **Cloud Provider:** Microsoft Azure
- **Computación Serverless:** Azure Functions (Blob Triggers)
- **Servicios Cognitivos/IA:** Azure AI Services (Computer Vision API), Ultralytics YOLOv8 (para la fase Edge/Local)
- **Almacenamiento:** Azure Blob Storage (Data Lake para imágenes raw y procesadas)
- **Frontend / Visualización:** HTML5, JavaScript, Chart.js (Hosteado como Azure Static Website)
- **Lenguaje Principal:** Python

---

## Project Context

This project develops a data and Artificial Intelligence architecture for a **Smart City** initiative. The objective is to implement a Smart Lighting System (SLS) that optimizes the city's energy consumption by dynamically controlling the switching on and off of streetlights based on the real-time presence of pedestrians and vehicles.

To this end, a pipeline has been designed that captures video streams from traffic cameras, processes the frames using Computer Vision models to detect entities, and exposes the results on a static dashboard.

The project evolves from an Edge (Local) processing MVP towards a highly scalable **Serverless Cloud Architecture**.

## Data Sources

* **Input:** Continuous real-time video streams (RTSP/HTTP) from public traffic and security webcams.
* **Analytical Output:** Structured data (CSV/JSON) with timestamps, entity counts (people/vehicles), and spatial metadata (Bounding Boxes) for the visualization of the processed frame.

## 🛠️ Technology Stack

* **Cloud Provider:** Microsoft Azure
* **Serverless Computing:** Azure Functions (Blob Triggers)
* **Cognitive/AI Services:** Azure AI Services (Computer Vision API), Ultralytics YOLOv8 (for the Edge/Local phase)
* **Storage:** Azure Blob Storage (Data Lake for raw and processed images)
* **Frontend / Visualization:** HTML5, JavaScript, Chart.js (Hosted as an Azure Static Website)
* **Main Language:** Python
