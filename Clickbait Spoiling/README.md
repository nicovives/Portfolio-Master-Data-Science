# 🎣 Clickbait Spoiler Classification (SemEval 2023) | NLP & Transformers

## 📖 Contexto del Proyecto
Este proyecto aborda la subtarea 1 del benchmark internacional **SemEval 2023 (Task 5): Webis Clickbait Spoiling Corpus 2022**. El objetivo es desarrollar un sistema de Procesamiento de Lenguaje Natural (NLP) capaz de clasificar qué tipo de "spoiler" (respuesta) requiere un titular de tipo *clickbait* para ser resuelto satisfactoriamente.

Las respuestas se clasifican en tres categorías lógicas:
- **Phrase:** Una frase corta o un dato concreto.
- **Passage:** Un pasaje o párrafo explicativo.
- **Multi:** Múltiples fragmentos distribuidos a lo largo del texto.

## 🛠️ Stack Tecnológico
- **Modelos de Lenguaje (Transformers):** DistilBERT, RoBERTa, DeBERTa-v3, Longformer.
- **Generación & Explicabilidad (XAI):** Modelos generativos (LLMs) auxiliares.
- **Procesamiento de Texto:** TF-IDF, Extracción de metadatos.
- **Entorno y Despliegue:** UI interactiva para experimentación en tiempo real.

## 🔬 Arquitectura y Pipeline de Desarrollo

El sistema se ha construido siguiendo un flujo de trabajo estructurado en 4 fases incrementales:

### 1. Data Preprocessing & Manejo de Desequilibrio
- **Análisis Exploratorio (EDA):** Evaluación de la distribución de categorías y detección de sesgos subyacentes en el corpus.
- **Optimización de Input:** Estructuración del texto en múltiples formatos para analizar cómo asimilan mejor la información las distintas arquitecturas.
- **Mitigación de Desequilibrio:** Diseño de un experimento específico para contrastar la eficacia de asignar pesos a las clases (*Class Weights*) frente a técnicas de sobremuestreo (*Oversampling*).

### 2. Exploración Arquitectónica (Model Selection)
- **Baseline:** Establecimiento de métricas de referencia utilizando un modelo ligero (DistilBERT).
- **Hibridación de Features:** Evaluación del impacto de concatenar representaciones tradicionales (matrices TF-IDF) con los *embeddings* densos generados por el Transformer.
- **Benchmarking de Modelos:** Comparativa exhaustiva entre familias avanzadas de Transformers (RoBERTa, DeBERTa-v3 y Longformer) para identificar los motores de clasificación con mayor potencial.

### 3. Entrenamiento Profundo y Arquitecturas Mixtas
- **Inyección de Metadatos:** Evolución de los finalistas hacia arquitecturas mixtas, inyectando características diseñadas manualmente (metadatos del titular) directamente en las capas de clasificación de la red neuronal.
- **Advanced Fine-Tuning:** Aplicación de técnicas de ajuste fino profundo sobre el modelo ganador para maximizar la capacidad de generalización y extraer el máximo rendimiento posible.

### 4. Explainable AI (XAI) & Despliegue
- **Transparencia Algorítmica:** Integración de un modelo de lenguaje generativo acoplado al clasificador, diseñado para redactar justificaciones en lenguaje natural que expliquen el razonamiento detrás de cada predicción.
- **Interfaz de Usuario (UI):** Desarrollo de una aplicación visual interactiva que permite a los usuarios introducir enlaces o textos de noticias reales para poner a prueba las predicciones y las explicaciones del sistema en vivo.

---
*Proyecto avanzado de Procesamiento de Lenguaje Natural enfocado en arquitecturas Transformer, ingeniería de características mixtas y explicabilidad algorítmica (XAI).*