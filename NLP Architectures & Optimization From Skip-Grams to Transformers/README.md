# 🧠 NLP Architectures & Optimization: From Skip-Grams to Transformers

## 📖 Contexto del Proyecto
Este repositorio contiene una colección de implementaciones avanzadas de Procesamiento de Lenguaje Natural (NLP) desarrolladas desde cero. El proyecto traza una evolución técnica desde los modelos lineales fundamentales y la representación distribuida del lenguaje, hasta la optimización de arquitecturas Transformer modernas para inferencia eficiente.

El objetivo principal no es solo entrenar modelos, sino **auditar su comportamiento, optimizar las operaciones tensoriales subyacentes y reducir los cuellos de botella computacionales** en la generación autorregresiva.

## 🛠️ Stack Tecnológico
- **Lenguaje:** Python
- **Deep Learning:** PyTorch / NumPy 
- **Visualización:** Matplotlib / Seaborn
- **Técnicas Clave:** Multi-Query Attention (MQA), KV Caching, Einstein Summation (`einsum`), Word Embeddings (Skip-Grams).

## 🏗️ Módulos del Proyecto

El proyecto está dividido en tres áreas analíticas y de desarrollo:

### 1. Clasificación Lineal y Dinámicas de Entrenamiento
Implementación robusta de clasificadores base para auditar la confianza predictiva y evitar el sobreajuste.
- **Validación y Early Stopping:** Refactorización de un regresor logístico binario integrando particiones estrictas (Train/Val/Test) y detención temprana (*Early Stopping*) monitorizando las curvas de pérdida.
- **Análisis de Incertidumbre (Multinomial):** Auditoría de las probabilidades *Softmax* emitidas por un regresor logístico multinomial. Se sometió al modelo a *Edge Cases* y frases semánticamente ambiguas (límites de decisión) para evaluar la entropía y calibración de sus predicciones ante datos fuera de distribución.

### 2. Representation Learning (Skip-Grams)
Optimización matemática y arquitectónica del algoritmo de Word2Vec (Skip-Grams) para la generación de *Word Embeddings*.
- **Ablation Study del Contexto (L):** Parametrización del tamaño de la ventana de contexto ($L$) para analizar su impacto en el espacio latente. 
- **Profiling Computacional:** Sustitución de la notación de Einstein (`einsum`) por multiplicaciones matriciales convencionales matriciales encadenadas (`matmul`). Se incluyó un análisis de tiempos de ejecución (*benchmarking*) para determinar qué enfoque es más eficiente a nivel de hardware y caché de CPU/GPU.

### 3. Optimización de Transformers (MQA & KV Cache)
Implementación customizada de mecanismos de atención avanzados para maximizar la eficiencia en la inferencia de *Language Models* (LLMs).
- **Multi-Query Attention (MQA):** Modificación del bloque *Multi-Head Attention* estándar para compartir un único *head* de *Keys* y *Values* a través de todos los *Query heads*.
- **Key-Value (KV) Caching:** Implementación de una caché de estados para el decodificador autorregresivo, evitando el recálculo redundante de *tokens* pasados.
- **Impacto en la Calidad:** Evaluación de la degradación probabilística de las predicciones tras aplicar MQA frente a la ganancia en eficiencia de memoria (Memory Bandwidth).

---
*Proyecto enfocado en la ingeniería interna de modelos NLP, optimización de inferencia algorítmica y eficiencia computacional.*