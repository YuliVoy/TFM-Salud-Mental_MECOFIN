# TFM - Detección de Problemas de Salud Mental en Redes Sociales Basada en Transformers

Código desarrollado para el TFM de Detección de Problemas de Salud Mental en Redes Sociales Basada en Transformers.

El objetivo del proyecto es desarrollar y evaluar modelos basados en Transformers para la clasificación de publicaciones procedentes de redes sociales en tres categorías: sano, depresión y suicidio.

## Modelos

Los modelos utilizados son:

- RoBERTa Base (`roberta-base`)
- DeBERTa v3 Base (`microsoft/deberta-v3-base`)

## Conjuntos de datos

Para el desarrollo del trabajo se utilizan tres conjuntos de datos:

- **DATD**
- **SDCNL**
- **DepressionX**

A partir de estos conjuntos se construye un Dataset Unificado (DU), utilizado posteriormente para la clasificación directa y para la reformulación del primer nivel del sistema en cascada.

Los conjuntos de datos utilizados proceden de trabajos previamente publicados y pueden obtenerse a través de sus fuentes originales. Por este motivo, no se añaden en este repositorio.

## Estrategias de clasificación

Se estudian dos estrategias:

- **Clasificación directa multiclase:** clasificación de las publicaciones entre sano, depresión y suicidio.
- **Sistema de clasificación en cascada:** dividido en dos niveles, donde el primero distingue entre sano y enfermo y el segundo clasifica las publicaciones enfermas entre depresión y suicidio.

Posteriormente, se reformula el primer nivel del sistema en cascada utilizando el Dataset Unificado binarizado.

## Código

Los notebooks incluidos en este repositorio contienen las diferentes etapas del desarrollo experimental, desde la preparación de los datos hasta el entrenamiento y evaluación de los modelos.

| Notebook | Contenido |
|---|---|
| `01a_Preprocesamiento_DATD.ipynb` | Limpieza y preprocesamiento de DATD. |
| `01b_Preprocesamiento_SDCNL.ipynb` | Limpieza y preprocesamiento de SDCNL. |
| `01c_Preprocesamiento_DepressionX.ipynb` | Limpieza y preprocesamiento de DepressionX. |
| `02_Creacion_Dataset_Unificado.ipynb` | Homogeneización de las etiquetas y construcción del Dataset Unificado. |
| `03_Division_Balanceo.ipynb` | División de los conjuntos de datos y balanceo de las clases. |
| `04_Baseline.ipynb` | Desarrollo de la baseline. |
| `05_Optimizacion_Hiperparametros.ipynb` | Búsqueda de hiperparámetros mediante Optuna. |
| `06_FineTuning_Evaluacion.ipynb` | Fine-tuning, evaluación de los modelos, clasificación directa y sistema en cascada inicial. |
| `07_Hipotesis_2.ipynb` | Reformulación del Nivel 1 y evaluación del sistema en cascada mejorado. |

Los notebooks se encuentran numerados siguiendo el orden general utilizado durante el desarrollo del proyecto.
