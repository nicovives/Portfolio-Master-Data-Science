# Real-Time IoT Data Ingestion Pipeline | EnergoTech

## Contexto del Proyecto
Este proyecto simula el entorno de I+D de **EnergoTech**, una empresa orientada a la gestión energética inteligente para hogares y pymes. El objetivo principal de este repositorio es construir y desplegar la primera fase de una plataforma analítica: un **sistema robusto de ingesta de datos en tiempo real (Edge-to-Cloud)**. 

La arquitectura diseñada recolecta, organiza y almacena datos telemétricos para habilitar futuros análisis y modelos de Machine Learning destinados a la optimización del consumo eléctrico basándose en la volatilidad del mercado.

## Fuentes de Datos
Para que la plataforma ofrezca recomendaciones de ahorro precisas, el pipeline procesa e integra dos flujos de datos en tiempo real:

1. **Datos de Consumo IoT (Edge):** Simulación de dispositivos instalados en hogares que transmiten métricas de consumo eléctrico (kW) con frecuencias de 10 segundos, variando según la franja horaria.
2. **Datos de Contexto Externo (Scraping & APIs):** 
   - Precios del kilovatio-hora extraídos mediante Web Scraping y la API de Red Eléctrica de España (REE).
   - Condiciones meteorológicas locales (temperatura y humedad) para contextualizar los picos de uso de climatización.

## 🛠️ Stack Tecnológico
- **Procesamiento Edge & Orquestación:** `Node.js`, `Node-RED`
- **Extracción de Datos:** `Cheerio` (Web Scraping), REST APIs.
- **Message Brokers (Pub/Sub):** `Eclipse Mosquitto` (On-Premise), `AWS IoT Core` (Cloud).
- **Almacenamiento (Data Lake):** `Amazon S3`
- **Protocolos y Formatos:** `MQTT`, `JSON`

---

## Project Context

This project simulates the R&D environment of **EnergoTech**, a company focused on smart energy management for homes and SMEs. The main objective of this repository is to build and deploy the first phase of an analytical platform: a **robust real-time data ingestion system (Edge-to-Cloud)**.

The designed architecture collects, organizes, and stores telemetric data to enable future analyses and Machine Learning models aimed at optimizing electricity consumption based on market volatility.

## Data Sources

For the platform to offer accurate savings recommendations, the pipeline processes and integrates two real-time data streams:

1. **IoT Consumption Data (Edge):** Simulation of devices installed in homes transmitting electricity consumption metrics (kW) at 10-second frequencies, varying according to the time slot.
2. **External Context Data (Scraping & APIs):**
   * Kilowatt-hour prices extracted via Web Scraping and the Red Eléctrica de España (REE) API.
   * Local weather conditions (temperature and humidity) to contextualize climate control usage peaks.

## 🛠️ Technology Stack

* **Edge Processing & Orchestration:** `Node.js`, `Node-RED`
* **Data Extraction:** `Cheerio` (Web Scraping), REST APIs.
* **Message Brokers (Pub/Sub):** `Eclipse Mosquitto` (On-Premise), `AWS IoT Core` (Cloud).
* **Storage (Data Lake):** `Amazon S3`
* **Protocols and Formats:** `MQTT`, `JSON`
