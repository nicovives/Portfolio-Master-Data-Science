# NLP Architectures & Optimization: From Skip-Grams to Transformers

## Contexto del Proyecto
Este repositorio contiene una colección de implementaciones avanzadas de Procesamiento de Lenguaje Natural (NLP) desarrolladas desde cero. El proyecto traza una evolución técnica desde los modelos lineales fundamentales y la representación distribuida del lenguaje, hasta la optimización de arquitecturas Transformer modernas para inferencia eficiente.

El objetivo principal no es solo entrenar modelos, sino **auditar su comportamiento, optimizar las operaciones tensoriales subyacentes y reducir los cuellos de botella computacionales** en la generación autorregresiva.

## 🛠️ Stack Tecnológico
- **Lenguaje:** Python
- **Deep Learning:** PyTorch / NumPy 
- **Visualización:** Matplotlib / Seaborn
- **Técnicas Clave:** Multi-Query Attention (MQA), KV Caching, Einstein Summation (`einsum`), Word Embeddings (Skip-Grams).

## Módulos del Proyecto

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

## Project Context

This repository contains a collection of advanced Natural Language Processing (NLP) implementations developed from scratch. The project traces a technical evolution from fundamental linear models and distributed language representation, to the optimization of modern Transformer architectures for efficient inference.

The main objective is not only to train models, but to **audit their behavior, optimize the underlying tensor operations, and reduce computational bottlenecks** in autoregressive generation.

## 🛠️ Technology Stack

* **Language:** Python
* **Deep Learning:** PyTorch / NumPy
* **Visualization:** Matplotlib / Seaborn
* **Key Techniques:** Multi-Query Attention (MQA), KV Caching, Einstein Summation (`einsum`), Word Embeddings (Skip-Grams).

## Project Modules

The project is divided into three analytical and development areas:

### 1. Linear Classification and Training Dynamics

Robust implementation of base classifiers to audit predictive confidence and prevent overfitting.

* **Validation and Early Stopping:** Refactoring of a binary logistic regressor integrating strict partitions (Train/Val/Test) and *Early Stopping* by monitoring loss curves.
* **Uncertainty Analysis (Multinomial):** Auditing of the *Softmax* probabilities output by a multinomial logistic regressor. The model was subjected to *Edge Cases* and semantically ambiguous phrases (decision boundaries) to evaluate the entropy and calibration of its predictions against out-of-distribution data.

### 2. Representation Learning (Skip-Grams)

Mathematical and architectural optimization of the Word2Vec algorithm (Skip-Grams) for the generation of *Word Embeddings*.

* **Context Ablation Study (L):** Parameterization of the context window size ($L$) to analyze its impact on the latent space.
* **Computational Profiling:** Replacement of Einstein notation (`einsum`) with conventional chained matrix multiplications (`matmul`). A runtime analysis (*benchmarking*) was included to determine which approach is more efficient at the hardware and CPU/GPU cache level.

### 3. Transformer Optimization (MQA & KV Cache)

Custom implementation of advanced attention mechanisms to maximize efficiency in the inference of *Language Models* (LLMs).

* **Multi-Query Attention (MQA):** Modification of the standard *Multi-Head Attention* block to share a single *head* for *Keys* and *Values* across all *Query heads*.
* **Key-Value (KV) Caching:** Implementation of a state cache for the autoregressive decoder, preventing the redundant recalculation of past *tokens*.
* **Quality Impact:** Evaluation of the probabilistic degradation of predictions after applying MQA versus the gain in memory efficiency (Memory Bandwidth).

