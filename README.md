Segundo Parcial - IA para la Economía 2025-2

Universidad de los Andes - Facultad de Economía

📋 Información del Proyecto
Este repositorio contiene el desarrollo del segundo parcial de la materia "IA para la Economía", enfocado en la implementación de modelos predictivos (regresión logística y redes neuronales) utilizando el Adult Dataset de UCI para predecir si una persona gana más de 50k al año.

🎯 Objetivos

Aplicar técnicas de preprocesamiento de datos y codificación de variables.

Construir un modelo baseline con regresión logística.

Implementar y entrenar redes neuronales en PyTorch.

Evaluar y comparar modelos con diferentes configuraciones de hiperparámetros.

Seleccionar el mejor modelo con un criterio que combine desempeño en validación y control de sobreajuste.

📊 Dataset

Fuente: UCI Adult Dataset

Dimensiones: 48,842 registros × 15 características

Variable objetivo: income (>50k o ≤50k)

Variables principales:

Demográficas: age, race, sex, native_country

Educativas: education, education_num

Laborales: workclass, occupation, hours_per_week, capital_gain, capital_loss

Familiares y sociales: marital_status, relationship

🛠 Tecnologías Utilizadas

Python

Librerías principales

pandas, numpy → Manipulación y análisis de datos

scikit-learn → Preprocesamiento, regresión logística y métricas

matplotlib, seaborn → Visualización de datos y curvas de pérdida

torch (PyTorch) → Construcción y entrenamiento de redes neuronales

🔬 Metodología

Exploración y Preprocesamiento

Carga de datos de train/test desde UCI.

Limpieza de etiquetas en test.

División de test en dos subconjuntos (test_1 y test_2).

Análisis de distribuciones de variables categóricas y objetivo.

Codificación de la variable objetivo con LabelEncoder.

One-hot encoding para variables categóricas.

Estandarización de variables numéricas con StandardScaler.

Modelo Baseline

Implementación de regresión logística.

Evaluación en train, test1 y test2 con métricas: accuracy, precisión, recall, F1-score, AUC.

Redes Neuronales (sin regularización)

Construcción de un MLP con PyTorch.

Pruebas con diferentes números de capas ocultas, neuronas y learning rates.

Curvas de pérdida para analizar comportamiento.

Redes Neuronales (con Dropout y Early Stopping)

Arquitectura extendida con Dropout.

Estrategia de Early Stopping para detener entrenamiento cuando la validación deja de mejorar.

Cinco experimentos con diferentes configuraciones de hiperparámetros (capas, neuronas, dropout, lr, weight decay).

Evaluación en train, validación y test.

Selección del Mejor Modelo

Definición de un composite score:

score
=
AUC
𝑣
𝑎
𝑙
−
𝛼
⋅
gap (train-val)
−
𝛽
⋅
val_loss
score=AUC
val
	​

−α⋅gap (train-val)−β⋅val_loss

Criterio balanceado que prioriza buen desempeño en validación y bajo sobreajuste.
