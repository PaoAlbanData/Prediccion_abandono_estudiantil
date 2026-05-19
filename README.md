# Predicción del Abandono Estudiantil con Machine Learning

## 📝 Descripción del proyecto

Este proyecto aplica técnicas de análisis de datos y aprendizaje automático para predecir el abandono estudiantil en educación superior.

El objetivo principal es identificar patrones académicos, personales y socioeconómicos asociados al riesgo de abandono, con el fin de construir un modelo predictivo capaz de clasificar a los estudiantes según su situación académica: abandono, continuidad o graduación.

El proyecto incluye análisis exploratorio de datos, preparación de variables, comparación de modelos supervisados, optimización del modelo final e interpretación de resultados mediante técnicas de explicabilidad.

---

## 🎯 Objetivo

Desarrollar un modelo de Machine Learning que permita anticipar posibles casos de abandono estudiantil a partir de información académica y socioeconómica, aportando una visión analítica útil para la toma de decisiones en contextos educativos.

---

## 📁 Dataset utilizado

El proyecto utiliza el dataset **Predict Students' Dropout and Academic Success**, disponible en el UCI Machine Learning Repository.

El conjunto de datos contiene información académica, demográfica y socioeconómica de estudiantes de educación superior, junto con una variable objetivo que clasifica el resultado académico final en tres categorías:

- Dropout
- Enrolled
- Graduate

---

## 🧪 Proceso desarrollado

El proyecto se estructura en las siguientes fases:

1. Carga y revisión inicial de los datos.
2. Análisis exploratorio de datos.
3. Limpieza y transformación de variables.
4. Codificación de variables categóricas.
5. División del dataset en entrenamiento y prueba.
6. Entrenamiento y comparación de modelos supervisados.
7. Optimización del modelo final.
8. Evaluación mediante métricas de clasificación.
9. Interpretación del modelo con técnicas de explicabilidad.

---

## 🤖 Modelos evaluados

Durante el desarrollo se compararon distintos modelos de clasificación supervisada:

- Regresión Logística
- Árbol de Decisión
- Random Forest
- XGBoost

El modelo final seleccionado fue **XGBoost**, debido a su mejor equilibrio entre rendimiento predictivo, capacidad de generalización e interpretación de variables relevantes.

---

## 📈 Resultados principales

El modelo permitió identificar variables académicas especialmente relevantes para la predicción del abandono, destacando el rendimiento del estudiante durante los primeros semestres.

Las variables relacionadas con unidades curriculares aprobadas, calificaciones obtenidas y desempeño académico temprano mostraron un peso importante en la clasificación de los estudiantes.

Además, se utilizaron técnicas de interpretación como **SHAP** para analizar la influencia de las variables en las predicciones del modelo.

---

## 🛠️ Herramientas y tecnologías

- Python
- Pandas
- NumPy
- Scikit-learn
- XGBoost
- Matplotlib
- Seaborn
- SHAP
- Google Colab / Jupyter Notebook

---

## 🚀 Acceso al proyecto

Puedes consultar el desarrollo completo del proyecto en el siguiente archivo:

- **[Ver notebook del proyecto](./Prediccion_abandono_estudiantil_Paola_Alban.ipynb)**

---

## 📌 Conclusión

Este proyecto muestra cómo el Machine Learning puede aplicarse en el ámbito educativo para apoyar la detección temprana de estudiantes en riesgo de abandono.

Más allá de la predicción, el análisis permite comprender qué factores influyen con mayor intensidad en el desempeño académico, aportando información útil para diseñar estrategias de seguimiento, orientación y prevención.

---

## 👩‍💻 Autora

**Paola Alban**  
Perfil orientado a Data Analytics, Business Intelligence y Machine Learning aplicado.

GitHub: [PaoAlbanData](https://github.com/PaoAlbanData)
