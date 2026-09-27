# Neural Network Calibration: Temperature Scaling & Focal Loss

## Contexto del Proyecto
En aplicaciones críticas de Machine Learning (como medicina o conducción autónoma), no basta con que un modelo tenga una alta precisión (*Accuracy*); también es fundamental que sus predicciones estén correctamente calibradas. Un modelo sobreconfiado puede predecir resultados erróneos con un 99% de seguridad.

Este proyecto explora e implementa dos enfoques analíticos avanzados para mitigar la mala calibración (sobreconfianza) en redes neuronales profundas:
1. **Métodos Post-Hoc:** Ajuste de las probabilidades emitidas por un modelo ya entrenado mediante **Temperature Scaling**.
2. **Mecanismos de Aprendizaje (Training-Time):** Modificación de la función de coste utilizando **Focal Loss** para penalizar dinámicamente la confianza excesiva en ejemplos "fáciles".

## Conjuntos de Datos
Para evaluar la calibración en un escenario realista, los experimentos se han ejecutado sobre benchmarks estándar de clasificación de imágenes donde los modelos tienden a mostrar descalibración:
- **CIFAR-10:** Colección de imágenes a color distribuidas en 10 clases.
- **Fashion-MNIST:** Dataset alternativo de imágenes en escala de grises.

## 🛠️ Stack Tecnológico
- **Lenguaje:** Python
- **Deep Learning:** PyTorch / TensorFlow (Frameworks base)
- **Métricas de Evaluación:** 
  - `ECE` (Expected Calibration Error) - Métrica core de calibración.
  - `Accuracy` - Para monitorizar la degradación del rendimiento.
- **Visualización:** *Reliability Diagrams* (Diagramas de Fiabilidad).

## Diseño de Experimentos y Metodología

### Fase 1: Calibración Post-Hoc (Temperature Scaling)
- **Baseline:** Entrenamiento de una arquitectura base evaluando su ECE y precisión.
- **Optimización:** Ajuste del hiperparámetro de temperatura ($T$) utilizando el conjunto de validación para suavizar la distribución de probabilidad (Softmax) sin alterar el orden de las predicciones.
- **Evaluación:** Comparativa visual y cuantitativa antes y después del escalado, verificando la corrección de la sobreconfianza sin pérdida de *Accuracy*.

### Fase 2: Calibración Dinámica (Focal Loss)
- Reemplazo de la *Cross-Entropy* tradicional por *Focal Loss*, que reduce el impacto de los ejemplos bien clasificados mediante un factor de modulación ($\gamma$):
  
  $$ FL(p_t) = -(1 - p_t)^\gamma \log(p_t) $$

- **Hyperparameter Tuning:** Exploración de diferentes configuraciones para el parámetro $\gamma$ (rango `[1, 5]`) sobre el conjunto de validación.
- **Análisis de Trade-off:** Evaluación del compromiso analítico entre la mejora de la calibración (ECE) y la conservación del poder predictivo del modelo.

### Fase 3: Enfoque Híbrido Avanzado
- Evaluación de un pipeline combinado: Aplicación de *Temperature Scaling* sobre modelos robustos entrenados previamente con *Focal Loss*, buscando el límite de optimización del ECE.

---

## Project Context

In critical Machine Learning applications (such as medicine or autonomous driving), it is not enough for a model to have high accuracy (*Accuracy*); it is also fundamental that its predictions are correctly calibrated. An overconfident model can predict erroneous results with 99% certainty.

This project explores and implements two advanced analytical approaches to mitigate miscalibration (overconfidence) in deep neural networks:

1. **Post-Hoc Methods:** Adjustment of the probabilities output by an already trained model through **Temperature Scaling**.
2. **Learning Mechanisms (Training-Time):** Modification of the cost function using **Focal Loss** to dynamically penalize excessive confidence in "easy" examples.

## Datasets

To evaluate calibration in a realistic scenario, the experiments have been executed on standard image classification benchmarks where models tend to show miscalibration:

* **CIFAR-10:** Collection of color images distributed across 10 classes.
* **Fashion-MNIST:** Alternative dataset of grayscale images.

## 🛠️ Technology Stack

* **Language:** Python
* **Deep Learning:** PyTorch / TensorFlow (Base frameworks)
* **Evaluation Metrics:**
* `ECE` (Expected Calibration Error) - Core calibration metric.
* `Accuracy` - To monitor performance degradation.


* **Visualization:** *Reliability Diagrams*.

## Experimental Design and Methodology

### Phase 1: Post-Hoc Calibration (Temperature Scaling)

* **Baseline:** Training of a base architecture evaluating its ECE and accuracy.
* **Optimization:** Adjustment of the temperature hyperparameter ($T$) using the validation set to smooth the probability distribution (Softmax) without altering the order of predictions.
* **Evaluation:** Visual and quantitative comparison before and after scaling, verifying the correction of overconfidence without loss of *Accuracy*.

### Phase 2: Dynamic Calibration (Focal Loss)

* Replacement of the traditional *Cross-Entropy* with *Focal Loss*, which reduces the impact of well-classified examples through a modulating factor ($\gamma$):

$$FL(p_t) = -(1 - p_t)^\gamma \log(p_t)$$

* **Hyperparameter Tuning:** Exploration of different configurations for the $\gamma$ parameter (range `[1, 5]`) on the validation set.
* **Trade-off Analysis:** Evaluation of the analytical compromise between calibration improvement (ECE) and the preservation of the model's predictive power.

### Phase 3: Advanced Hybrid Approach

* Evaluation of a combined pipeline: Application of *Temperature Scaling* on robust models previously trained with *Focal Loss*, seeking the optimization limit of the ECE.
