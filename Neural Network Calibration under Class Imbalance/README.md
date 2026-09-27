# Neural Network Calibration under Class Imbalance

## Contexto del Proyecto
Los modelos de Deep Learning modernos a menudo sufren de sobreconfianza (overconfidence), produciendo predicciones con probabilidades muy altas incluso cuando se equivocan. Este problema se agrava significativamente cuando los modelos se entrenan con conjuntos de datos que presentan **desequilibrio de clases**.

El objetivo de este proyecto es analizar cuantitativamente cómo el desequilibrio de clases afecta a la calibración de una red neuronal y evaluar la eficacia de distintas técnicas de regularización y muestreo para mitigar este efecto, logrando modelos más fiables y seguros.

## Objetivos Analíticos
1. **Auditoría de Calibración:** Evaluar la divergencia entre la precisión real (*Accuracy*) y la confianza predicha de un modelo base ante diferentes niveles de desequilibrio de clases.
2. **Mitigación mediante Data Augmentation:** Cuantificar el impacto de diferentes estrategias de aumento de datos en la mejora de la calibración.
3. **Mitigación mediante Técnicas Avanzadas:** Explorar e implementar mecanismos algorítmicos y de arquitectura para mejorar la calibración sin sacrificar el poder predictivo del modelo.

## 🛠️ Stack Tecnológico y Herramientas
- **Lenguaje:** Python
- **Entorno:** Google Colab / Jupyter Notebooks
- **Frameworks Deep Learning:** (PyTorch / TensorFlow / Keras)
- **Métricas Clave:** 
  - `ECE` (Expected Calibration Error) - Métrica principal para medir la desviación de la calibración.
  - `Accuracy` (Precisión) - Para garantizar que la mejora en calibración no degrada el rendimiento general.

---

# Neural Network Calibration under Class Imbalance

## Project Context

Modern Deep Learning models often suffer from overconfidence, producing predictions with very high probabilities even when they are incorrect. This problem is significantly exacerbated when models are trained on datasets that present **class imbalance**.

The objective of this project is to quantitatively analyze how class imbalance affects the calibration of a neural network and to evaluate the effectiveness of different regularization and sampling techniques to mitigate this effect, achieving more reliable and safe models.

## Analytical Objectives

1. **Calibration Audit:** Evaluate the divergence between true accuracy (*Accuracy*) and the predicted confidence of a base model under different levels of class imbalance.
2. **Mitigation through Data Augmentation:** Quantify the impact of different data augmentation strategies on improving calibration.
3. **Mitigation through Advanced Techniques:** Explore and implement algorithmic and architectural mechanisms to improve calibration without sacrificing the predictive power of the model.

## 🛠️ Technology Stack and Tools

* **Language:** Python
* **Environment:** Google Colab / Jupyter Notebooks
* **Deep Learning Frameworks:** (PyTorch / TensorFlow / Keras)
* **Key Metrics:**
  * `ECE` (Expected Calibration Error) - Main metric to measure calibration deviation.
  * `Accuracy` - To ensure that the improvement in calibration does not degrade overall performance.
 
