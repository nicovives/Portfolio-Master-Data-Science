# ⚖️ Neural Network Calibration under Class Imbalance

## 📖 Contexto del Proyecto
Los modelos de Deep Learning modernos a menudo sufren de sobreconfianza (overconfidence), produciendo predicciones con probabilidades muy altas incluso cuando se equivocan. Este problema se agrava significativamente cuando los modelos se entrenan con conjuntos de datos que presentan **desequilibrio de clases**.

El objetivo de este proyecto es analizar cuantitativamente cómo el desequilibrio de clases afecta a la calibración de una red neuronal y evaluar la eficacia de distintas técnicas de regularización y muestreo para mitigar este efecto, logrando modelos más fiables y seguros.

## 🎯 Objetivos Analíticos
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

## 🔬 Metodología y Diseño de Experimentos

El estudio se ha dividido en fases estructuradas, manteniendo un aislamiento estricto entre los conjuntos de Entrenamiento, Validación (para selección de hiperparámetros) y Test (solo para inferencia final).

### Fase 1: Baseline y Evaluación del Desequilibrio
- Entrenamiento de una Red Neuronal base bajo dos escenarios de desequilibrio de clases (moderado y severo).
- Cálculo del ECE baseline como punto de referencia.

### Fase 2: Impacto del Data Augmentation
- Evaluación comparativa del modelo base vs. dos configuraciones avanzadas de Data Augmentation para comprobar si la exposición a mayor variabilidad sintética corrige la sobreconfianza en la clase mayoritaria.

### Fase 3: Mecanismos de Calibración Avanzados
Se ha implementado y comparado el rendimiento de técnicas especializadas en regularización y calibración, tales como:
- **Label Smoothing:** Suavizado de etiquetas para evitar que la red empuje las probabilidades hacia los extremos (0 o 1).
- **Mix-up / Data Blending:** Entrenamiento con combinaciones lineales convexas de pares de imágenes y sus etiquetas.
- **MonteCarlo Dropout:** Inferencia estocástica para aproximar la incertidumbre del modelo.
- **Ensembles:** Combinación de arquitecturas entrenadas con diferentes semillas para estabilizar las predicciones.

## 📊 Resultados y Conclusiones
*En este repositorio se incluye el código fuente (`.ipynb`) con la implementación de los experimentos, las curvas de calibración (Reliability Diagrams) y el análisis de la degradación del ECE frente al desequilibrio.*

---
*Proyecto desarrollado como investigación práctica de técnicas avanzadas de Machine Learning, enfocado en la fiabilidad e interpretabilidad de modelos predictivos.*