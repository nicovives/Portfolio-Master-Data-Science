# ⚡ Real-Time IoT Data Ingestion Pipeline | EnergoTech

## 📖 Contexto del Proyecto
Este proyecto simula el entorno de I+D de **EnergoTech**, una empresa orientada a la gestión energética inteligente para hogares y pymes. El objetivo principal de este repositorio es construir y desplegar la primera fase de una plataforma analítica: un **sistema robusto de ingesta de datos en tiempo real (Edge-to-Cloud)**. 

La arquitectura diseñada recolecta, organiza y almacena datos telemétricos para habilitar futuros análisis y modelos de Machine Learning destinados a la optimización del consumo eléctrico basándose en la volatilidad del mercado.

## 📊 Fuentes de Datos
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

## 🏗️ Arquitectura y Flujo de Datos

El proyecto está estructurado en una migración progresiva desde un entorno local hacia una arquitectura Cloud de alta disponibilidad:

1. **Generación y Enriquecimiento (Node-RED):**
   - Creación de flujos para la simulación de telemetría IoT de múltiples hogares.
   - Flujos paralelos de ingesta de datos meteorológicos y precios de la luz usando peticiones HTTP y la librería Cheerio.
2. **Validación Local (Mosquitto):** 
   - Despliegue de un bróker MQTT local para validar la arquitectura de colas (topics) y el patrón Publish/Subscribe en un entorno controlado.
3. **Escalado Cloud y Seguridad (AWS IoT Core):**
   - Migración de los flujos de datos a la nube para garantizar tolerancia a fallos y alta disponibilidad.
   - Autenticación y cifrado TLS mediante certificados X.509 y políticas IAM restrictivas.
4. **Data Lake y Particionado (Amazon S3):**
   - Implementación de reglas de enrutamiento en AWS IoT para almacenar los datos en crudo (Raw Data).
   - Estructuración automática en particiones cronológicas (`/year=YYYY/month=MM/day=DD/hour=HH/`) siguiendo las mejores prácticas de Data Engineering para optimizar futuras consultas con herramientas como AWS Athena.

## 🚀 Mejoras y Extensiones Implementadas
- **Desacoplamiento de Topics:** Refactorización del flujo original para rutear el consumo de cada hogar a un *topic* MQTT independiente (`energo/consumo/home_id`), mejorando la granularidad y seguridad del sistema.
- **Integración API Oficial:** Reemplazo parcial del scraping por integraciones directas con la API de **REE** (Red Eléctrica de España) para una ingesta de precios más estable y escalable.

---
*Este proyecto forma parte de los desarrollos prácticos del Máster en Data Science, enfocado en el diseño de Infraestructuras y Tecnologías para Big Data.*