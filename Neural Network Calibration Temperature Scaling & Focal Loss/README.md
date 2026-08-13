# 🎯 Neural Network Calibration: Temperature Scaling & Focal Loss

## 📖 Contexto del Proyecto
En aplicaciones críticas de Machine Learning (como medicina o conducción autónoma), no basta con que un modelo tenga una alta precisión (*Accuracy*); también es fundamental que sus predicciones estén correctamente calibradas. Un modelo sobreconfiado puede predecir resultados erróneos con un 99% de seguridad.

Este proyecto explora e implementa dos enfoques analíticos avanzados para mitigar la mala calibración (sobreconfianza) en redes neuronales profundas:
1. **Métodos Post-Hoc:** Ajuste de las probabilidades emitidas por un modelo ya entrenado mediante **Temperature Scaling**.
2. **Mecanismos de Aprendizaje (Training-Time):** Modificación de la función de coste utilizando **Focal Loss** para penalizar dinámicamente la confianza excesiva en ejemplos "fáciles".

## 📊 Conjuntos de Datos
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

## 🔬 Diseño de Experimentos y Metodología

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

## 📈 Resultados y Visualización
En los notebooks de este repositorio se incluye el código modular completo, los resultados tabulados de los experimentos en el conjunto de *Test*, y la generación automatizada de **Diagramas de Fiabilidad (Reliability Diagrams)** que ilustran cómo la curva de confianza del modelo se ajusta a la precisión real tras aplicar las distintas técnicas.

---
*Proyecto analítico centrado en la interpretabilidad, fiabilidad y calibración probabilística de modelos de Deep Learning.*