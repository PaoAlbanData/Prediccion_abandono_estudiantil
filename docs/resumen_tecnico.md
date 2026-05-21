# Resumen técnico del proyecto

## 1. Contexto del proyecto

Este proyecto analiza el abandono estudiantil en educación superior mediante técnicas de análisis de datos y Machine Learning. El objetivo es construir un modelo capaz de clasificar a los estudiantes según su situación académica: abandono, continuidad o graduación.

El análisis se basa en variables académicas, personales y socioeconómicas disponibles en el dataset Predict Students' Dropout and Academic Success, del UCI Machine Learning Repository.

## 2. Flujo de trabajo desarrollado

El proyecto se desarrolló siguiendo un proceso estructurado de análisis y modelado:

1. Carga y revisión inicial del dataset.
2. Análisis exploratorio de datos.
3. Revisión de la variable objetivo.
4. Limpieza y transformación de variables.
5. Codificación de variables categóricas.
6. División del dataset en entrenamiento y prueba.
7. Entrenamiento y comparación de modelos supervisados.
8. Optimización del modelo seleccionado.
9. Evaluación mediante métricas de clasificación.
10. Interpretación de resultados con técnicas de explicabilidad.

## 3. Modelos evaluados

Durante el desarrollo se compararon varios modelos de clasificación supervisada:

- Regresión Logística.
- Árbol de Decisión.
- Random Forest.
- XGBoost.

El modelo final seleccionado fue XGBoost, debido a su equilibrio entre rendimiento predictivo, capacidad de generalización e interpretación de variables relevantes.

## 4. Métricas utilizadas

Para evaluar los modelos se utilizaron métricas adecuadas para un problema de clasificación multiclase:

- Accuracy.
- F1-score.
- F1-macro.
- Matriz de confusión.
- AUC-ROC multiclase.

Se prestó especial atención al F1-macro, ya que permite valorar el rendimiento del modelo considerando todas las clases, no solo la clase mayoritaria.

## 5. Resultados principales

Los resultados mostraron que las variables académicas tienen un peso importante en la predicción del abandono estudiantil.

Destacan especialmente las variables relacionadas con el rendimiento académico temprano, como unidades curriculares aprobadas, calificaciones obtenidas y desempeño durante los primeros semestres.

Esto indica que el comportamiento académico inicial puede aportar señales relevantes para identificar perfiles con mayor riesgo de abandono.

## 6. Interpretabilidad del modelo

Para interpretar el modelo final se utilizaron técnicas de explicabilidad, especialmente SHAP.

El análisis permitió identificar qué variables influyen con mayor intensidad en las predicciones del modelo y aportar una lectura más comprensible de los resultados.

Esta parte es importante porque permite que el modelo no se entienda solo como una herramienta predictiva, sino también como una fuente de información útil para apoyar decisiones educativas.

## 7. Conclusión técnica

El proyecto muestra cómo el Machine Learning puede aplicarse al ámbito educativo para detectar patrones asociados al abandono estudiantil.

Más allá de clasificar estudiantes, el análisis permite comprender qué factores tienen mayor influencia en el resultado académico, aportando información útil para estrategias de seguimiento, orientación y prevención.
