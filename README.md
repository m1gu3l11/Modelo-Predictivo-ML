# Predicción de contratación de depósitos bancarios mediante Machine Learning

Proyecto académico colaborativo centrado en el desarrollo y evaluación de modelos de clasificación para predecir si un cliente contratará un depósito bancario a plazo a partir de sus características y su historial de campañas de marketing.

El trabajo abarca el análisis exploratorio de los datos, el diseño del preprocesamiento, la comparación de distintos algoritmos y la optimización de sus hiperparámetros para seleccionar el modelo con mejor capacidad predictiva.

## Objetivos

- Explorar y comprender los datos, identificando patrones relacionados con la contratación de depósitos.
- Diseñar un proceso de preprocesamiento adaptado a variables numéricas y categóricas.
- Comparar distintos algoritmos de clasificación mediante una metodología de evaluación común.
- Optimizar los hiperparámetros y seleccionar el modelo con mejor rendimiento.
- Analizar las variables relevantes y estudiar la evolución del rendimiento mediante curvas de aprendizaje.

## Análisis exploratorio y preprocesamiento

Se trabajó con un conjunto de 11.000 registros y 16 variables predictoras, además de la variable objetivo deposit.

El análisis exploratorio incluyó el estudio de valores ausentes, valores atípicos, distribuciones y relaciones entre variables y objetivo.

Entre las técnicas de preprocesamiento utilizadas se encuentran:

- Imputación de valores ausentes.
- Codificación One-Hot de variables categóricas.
- Escalado de variables numéricas según el algoritmo.
- Transformación de la variable `pdays` y creación de la variable indicadora `contactado_antes`.
- Construcción de pipelines de preprocesamiento y clasificación mediante scikit-learn.

## Modelos y experimentación

Se compararon cuatro algoritmos de clasificación:

- **K-Nearest Neighbors (KNN)**.
- **Árboles de decisión**.
- **Regresión logística**.
- **Support Vector Machines (SVM)**, evaluando distintas configuraciones de kernel.

Se utilizó GridSearchCV con validación cruzada de tres particiones sobre el conjunto de entrenamiento, empleando ROC-AUC como métrica principal para comparar modelos y optimizar sus hiperparámetros.

Además, se aplicó regularización L1 en regresión logística para analizar la relevancia de las variables y se estudiaron curvas de aprendizaje para evaluar cómo influye el tamaño del conjunto de entrenamiento en el rendimiento de los modelos.

## Resultados

El modelo seleccionado fue un SVM con kernel RBF y los hiperparámetros `C=1` y `gamma=0.1`.

| Evaluación |                                                                             | ROC-AUC |
| Validación cruzada durante la optimización                                                  0,9169 |
| Conjunto de prueba                                                                          0,9161 |

Los resultados muestran una capacidad discriminativa elevada en la partición utilizada para la evaluación. El rendimiento puede variar con otros datos y distribuciones.

## Tecnologías utilizadas

- **Python:** desarrollo de la experimentación.
- **pandas y NumPy:** manipulación y preparación de datos.
- **scikit-learn:** preprocesamiento, pipelines, modelos de clasificación, validación cruzada y optimización de hiperparámetros.
- **Matplotlib y Seaborn:** visualización de datos y resultados.
- **Joblib:** serialización del modelo seleccionado.

## Estructura del proyecto

- NoteBook1.ipynb: análisis exploratorio, preprocesamiento, comparación y optimización de modelos, evaluación y análisis de curvas de aprendizaje.
- NoteBook2.ipynb: carga del modelo final y generación de predicciones sobre el conjunto de competición.
- mystreamlit.py: interfaz de predicción proporcionada como parte de la práctica, conectada con el modelo entrenado.
- requirements.txt: dependencias necesarias para reproducir el entorno.

## Trabajo realizado

El trabajo se centró en el análisis de los datos, la preparación de las variables, la experimentación con diferentes algoritmos, la optimización de hiperparámetros y la evaluación crítica de los resultados. La interfaz de Streamlit formaba parte del material proporcionado para la práctica y no constituye el desarrollo principal del proyecto.

Proyecto académico desarrollado en colaboración con otro estudiante.
