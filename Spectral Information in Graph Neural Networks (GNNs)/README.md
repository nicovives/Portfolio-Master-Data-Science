# 🕸️ Spectral Information in Graph Neural Networks (GNNs)

## 📖 Contexto del Proyecto
La clasificación de grafos es un desafío complejo en el ámbito del Deep Learning, especialmente cuando se trabaja con redes puramente topológicas que carecen de atributos en sus nodos. 

El objetivo de este proyecto es analizar y cuantificar el impacto de **integrar información espectral** en las Redes Neuronales de Grafos (GNNs). Para ello, se evalúa el rendimiento de arquitecturas convolucionales estándar frente a variantes espectrales en tareas de clasificación, prestando especial atención a cómo la topología pura del grafo afecta a la capacidad predictiva del modelo.

## 🧠 Arquitectura y Metodología
En el estudio se han comparado distintas arquitecturas de redes para grafos, sometiéndolas a un proceso riguroso de optimización de hiperparámetros (variación del número de capas, *hidden channels*, tasas de aprendizaje, etc.):

- **Standard GCN (Graph Convolutional Network):** Arquitectura base.
- **GCNEig:** GCN enriquecida con información espectral (eigenvectores/eigenvalores).
- **GCNEigDecoupled:** Variante espectral desacoplada para mayor flexibilidad en la propagación de la información.

### ✨ Innovación: Generación de Características Sintéticas
En los datasets puramente topológicos, la ausencia de atributos *a priori* limita el uso de la GCN estándar (restringiendo el análisis a GCNEig y GCNEigDecoupled). Para solucionar esto, se ha implementado un pipeline de **creación de características sintéticas** para los nodos. Gracias a esta ingeniería de características, los modelos GCN estándar han logrado alcanzar e igualar el rendimiento del estado del arte referenciado en la literatura académica reciente.

## 📊 Fuentes de Datos
Se han utilizado conjuntos de datos de referencia del **TUDataset** proporcionado por `PyTorch Geometric`, divididos en dos categorías principales según su naturaleza:

**Datasets con atributos (Bioinformática / Química):**
- `MUTAG`
- `ENZYMES`
- `PROTEINS`

**Datasets puramente topológicos (Redes Sociales):**
- `IMDB-BINARY`
- `REDDIT-BINARY`
- `COLLAB`

## 🛠️ Stack Tecnológico
- **Framework de Deep Learning:** PyTorch
- **Graph Machine Learning:** PyTorch Geometric (PyG)
- **Entorno de Desarrollo:** Python, Jupyter Notebooks
- **Técnicas Clave:** Spectral Graph Theory, Feature Engineering, Hyperparameter Tuning.

## 📁 Estructura del Repositorio
El repositorio está organizado modularmente por conjunto de datos. Cada directorio contiene el código fuente (`.ipynb`) con la definición de las redes, el proceso de entrenamiento, y los resultados/métricas obtenidos tras la optimización.

```text
├── COLLAB/          # Experimentos y resultados para COLLAB
├── ENZYMES/         # Experimentos y resultados para ENZYMES
├── IMDB-BINARY/     # Experimentos y resultados para IMDB-BINARY
├── MUTAG/           # Experimentos y resultados para MUTAG
├── PROTEINS/        # Experimentos y resultados para PROTEINS
└── REDDIT-BINARY/   # Experimentos y resultados para REDDIT-BINARY