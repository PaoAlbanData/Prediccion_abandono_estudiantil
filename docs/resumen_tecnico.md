# Resumen técnico del proyecto

# Predicción del Abandono Estudiantil con Machine Learning

## 1. Contexto del proyecto

Este proyecto analiza el abandono estudiantil en educación superior mediante técnicas de análisis de datos y Machine Learning.

El abandono académico es un problema relevante porque puede afectar tanto al estudiante como a las instituciones educativas. Desde el punto de vista institucional, anticipar posibles casos de abandono permite diseñar estrategias de seguimiento, orientación y prevención más oportunas.

El análisis se basa en el dataset **Predict Students' Dropout and Academic Success**, disponible en el UCI Machine Learning Repository. Este conjunto de datos contiene información académica, personal, socioeconómica y administrativa de estudiantes de educación superior.

La variable objetivo clasifica el resultado académico final del estudiante en tres categorías:

- Dropout: estudiante que abandona.
- Enrolled: estudiante que continúa matriculado.
- Graduate: estudiante que se gradúa.

Por tanto, el problema se plantea como una tarea de **clasificación multiclase supervisada**.

## 2. Objetivo del proyecto

El objetivo principal del proyecto es desarrollar un modelo de Machine Learning capaz de predecir la situación académica final de los estudiantes a partir de variables disponibles en el dataset.

El modelo busca clasificar a los estudiantes en una de las tres categorías posibles: abandono, continuidad o graduación.

Además de construir un modelo predictivo, el proyecto busca comprender qué variables tienen mayor influencia en la predicción del abandono estudiantil. Por esta razón, la interpretación del modelo es una parte importante del análisis.

Los objetivos específicos del proyecto son:

1. Analizar la estructura y calidad del dataset.
2. Explorar la distribución de la variable objetivo.
3. Identificar patrones relacionados con el abandono estudiantil.
4. Preparar los datos para el entrenamiento de modelos supervisados.
5. Comparar diferentes algoritmos de clasificación.
6. Seleccionar y optimizar el modelo con mejor rendimiento.
7. Evaluar el modelo mediante métricas adecuadas para clasificación multiclase.
8. Interpretar los resultados mediante técnicas de explicabilidad, especialmente SHAP.

## 3. Metodología CRISP-DM aplicada

El proyecto se desarrolló siguiendo una lógica alineada con la metodología **CRISP-DM**.

CRISP-DM es una metodología utilizada en proyectos de minería de datos y ciencia de datos. Permite organizar el trabajo en fases, desde la comprensión inicial del problema hasta la evaluación e interpretación de los resultados.

En este proyecto, las fases se aplicaron de la siguiente manera:

## 3.1 Comprensión del problema

La primera fase consistió en entender el abandono estudiantil como un problema educativo y analítico.

El abandono no se interpretó únicamente como una categoría dentro de un dataset, sino como un fenómeno influido por múltiples factores: rendimiento académico, trayectoria previa, condiciones socioeconómicas, características personales y comportamiento durante los primeros semestres.

Desde la perspectiva de Data Science, el problema se formuló como una pregunta predictiva:

**¿Es posible predecir el abandono estudiantil a partir de variables académicas, personales y socioeconómicas?**

Esta pregunta permitió definir el objetivo del modelo y orientar el análisis hacia la identificación de patrones útiles para la toma de decisiones.

## 3.2 Comprensión de los datos

En esta fase se revisó la estructura del dataset.

Se analizaron aspectos como:

- Número de registros.
- Número de variables.
- Tipos de datos.
- Distribución de la variable objetivo.
- Presencia de valores faltantes.
- Variables académicas del primer y segundo semestre.
- Variables personales y socioeconómicas.
- Relaciones entre variables predictoras y resultado académico.

Una observación relevante fue que las variables académicas relacionadas con el rendimiento temprano del estudiante tenían un peso importante dentro del conjunto de datos.

Entre estas variables se encontraban las relacionadas con unidades curriculares matriculadas, acreditadas, evaluadas, aprobadas y calificaciones obtenidas durante el primer y segundo semestre.

También se observó que la variable objetivo no estaba perfectamente equilibrada entre clases. Esta situación hizo necesario utilizar métricas de evaluación más completas que la accuracy.

## 3.3 Preparación de los datos

La preparación de datos fue una fase central del proyecto.

Antes de entrenar los modelos, fue necesario revisar y transformar las variables para que pudieran ser utilizadas correctamente por los algoritmos de Machine Learning.

Las principales tareas realizadas fueron:

- Revisión de valores faltantes.
- Verificación de tipos de datos.
- Transformación de variables categóricas.
- Codificación de variables no numéricas.
- Tratamiento de variables con alta cardinalidad.
- Separación entre variables predictoras y variable objetivo.
- División del dataset en entrenamiento y prueba.
- Aplicación de una división estratificada para mantener la proporción de clases.

En esta fase se prestó especial atención a las variables categóricas, ya que algunos modelos no aceptan variables en formato texto. Por ello fue necesario aplicar técnicas de codificación para convertirlas en variables numéricas.

También se revisaron variables con muchas categorías, como algunas relacionadas con ocupaciones o modos de aplicación. Estas variables podían generar problemas si se codificaban de forma directa sin control.

## 3.4 Modelado

En la fase de modelado se entrenaron y compararon varios algoritmos de clasificación supervisada.

Los modelos evaluados fueron:

- Regresión Logística.
- Árbol de Decisión.
- Random Forest.
- XGBoost.

Cada modelo permitió observar un comportamiento diferente.

La Regresión Logística sirvió como modelo base y referencia inicial. El Árbol de Decisión permitió una interpretación más sencilla mediante reglas, aunque con mayor riesgo de sobreajuste. Random Forest mejoró la estabilidad al combinar múltiples árboles. XGBoost ofreció el mejor equilibrio entre rendimiento predictivo, capacidad de generalización e interpretación posterior mediante técnicas como SHAP.

Por este motivo, XGBoost fue seleccionado como modelo final.

## 3.5 Evaluación

La evaluación del modelo se realizó utilizando métricas adecuadas para un problema de clasificación multiclase.

Las principales métricas utilizadas fueron:

- Accuracy.
- Precision.
- Recall.
- F1-score.
- F1-macro.
- Matriz de confusión.
- AUC-ROC multiclase.
- Validación cruzada estratificada.

Aunque la accuracy permite conocer el porcentaje global de aciertos, no fue suficiente como única métrica. En problemas donde las clases no están perfectamente equilibradas, la accuracy puede ocultar un mal rendimiento en clases minoritarias o más difíciles de clasificar.

Por esta razón, se prestó especial atención al **F1-macro**, ya que esta métrica calcula el promedio del F1-score dando el mismo peso a cada clase. Esto permite evaluar mejor el comportamiento del modelo en las tres categorías: abandono, continuidad y graduación.

La matriz de confusión también fue importante para identificar en qué clases el modelo acertaba más y en cuáles se producían más errores.

## 3.6 Interpretación de resultados

La fase final consistió en interpretar el modelo seleccionado.

Para ello se utilizaron técnicas de explicabilidad, especialmente **SHAP values**.

El objetivo de esta fase fue comprender qué variables influían más en las predicciones del modelo y cómo contribuían a clasificar a los estudiantes en una categoría concreta.

Esta fase es importante porque permite que el modelo no se entienda únicamente como una herramienta predictiva, sino también como una fuente de conocimiento sobre los factores asociados al abandono estudiantil.

## 4. Análisis exploratorio de datos

El análisis exploratorio permitió comprender mejor el comportamiento del dataset antes de aplicar modelos predictivos.

Se revisó la distribución de la variable objetivo y se observó que las clases no estaban perfectamente equilibradas. Esta situación justificó el uso de métricas más completas que la accuracy.

También se analizaron variables académicas del primer y segundo semestre. Estas variables resultaron especialmente relevantes porque reflejan el desempeño temprano del estudiante.

Entre las variables académicas analizadas se encontraban:

- Unidades curriculares acreditadas.
- Unidades curriculares matriculadas.
- Unidades curriculares evaluadas.
- Unidades curriculares aprobadas.
- Calificaciones obtenidas.
- Unidades curriculares sin evaluación.

El análisis mostró que el rendimiento académico temprano puede aportar señales importantes sobre la trayectoria posterior del estudiante.

En particular, las variables relacionadas con unidades aprobadas y calificaciones obtenidas mostraron una relación importante con la situación académica final.

También se observaron relaciones entre variables académicas del primer y segundo semestre. Algunas de estas variables estaban altamente correlacionadas, lo que indica que podían estar midiendo aspectos similares del rendimiento académico.

Esta observación fue relevante para la interpretación posterior del modelo, ya que una alta correlación entre variables puede hacer que varias características compartan información parecida.

## 5. Preparación y transformación de variables

La preparación de variables incluyó diferentes decisiones técnicas.

## 5.1 Revisión de valores faltantes

Se revisó la presencia de valores nulos en el dataset. Esta revisión permitió confirmar si era necesario aplicar imputación o si el conjunto de datos podía trabajarse sin una intervención significativa en este aspecto.

## 5.2 Codificación de variables categóricas

Las variables categóricas fueron transformadas para que pudieran ser utilizadas por los modelos.

Este paso fue necesario porque algoritmos como XGBoost, Random Forest o Regresión Logística requieren que las variables de entrada estén en formato numérico.

Durante esta fase se encontraron errores relacionados con variables en formato no numérico. Estos errores fueron corregidos revisando los tipos de datos y aplicando codificación adecuada.

## 5.3 Tratamiento de variables de alta cardinalidad

Algunas variables categóricas presentaban muchas categorías. Este tipo de variables puede generar problemas si se codifica de forma directa, porque puede aumentar demasiado la dimensionalidad o introducir ruido.

Por ello se consideró el tratamiento de categorías poco frecuentes y la transformación controlada de estas variables.

## 5.4 Separación de variables predictoras y variable objetivo

El dataset se separó en:

- Variables predictoras.
- Variable objetivo.

La variable objetivo corresponde al estado académico final del estudiante: abandono, continuidad o graduación.

## 5.5 División en entrenamiento y prueba

El dataset se dividió en conjuntos de entrenamiento y prueba.

La división permitió entrenar los modelos con una parte de los datos y evaluar su rendimiento en datos no vistos.

Se utilizó una estrategia estratificada para mantener la proporción de clases en ambos conjuntos. Esto fue importante porque la variable objetivo no estaba perfectamente equilibrada.

## 6. Modelos evaluados

## 6.1 Regresión Logística

La Regresión Logística se utilizó como modelo base.

Su principal ventaja es la interpretabilidad y simplicidad. Permite tener una primera referencia del rendimiento del problema de clasificación.

Sin embargo, puede presentar limitaciones cuando las relaciones entre variables y clases no son lineales.

## 6.2 Árbol de Decisión

El Árbol de Decisión permite representar el proceso de clasificación mediante reglas.

Es un modelo fácil de interpretar, pero puede ser sensible al sobreajuste si no se controla correctamente su profundidad o complejidad.

## 6.3 Random Forest

Random Forest combina múltiples árboles de decisión para mejorar la estabilidad y reducir el riesgo de sobreajuste.

Este modelo suele ofrecer mejor generalización que un árbol individual, aunque puede ser menos interpretable de forma directa.

## 6.4 XGBoost

XGBoost fue el modelo final seleccionado.

Este algoritmo se basa en boosting, construyendo modelos de forma secuencial para corregir errores de modelos anteriores.

En este proyecto, XGBoost mostró un buen equilibrio entre rendimiento predictivo, capacidad de generalización e interpretación mediante técnicas como feature importance y SHAP.

## 7. Optimización del modelo XGBoost

Después de seleccionar XGBoost como modelo principal, se realizó una optimización mediante GridSearchCV.

El objetivo fue probar distintas combinaciones de hiperparámetros para encontrar una configuración más adecuada para el problema.

Los hiperparámetros evaluados incluyeron:

- learning_rate.
- max_depth.
- n_estimators.
- subsample.

La mejor combinación encontrada fue:

```python
{
    "learning_rate": 0.1,
    "max_depth": 5,
    "n_estimators": 100,
    "subsample": 0.8
}
```

Esta configuración permitió obtener una mejora leve pero consistente en el rendimiento del modelo.

La optimización no produjo un cambio drástico, pero sí aportó una configuración más justificada y estable para el modelo final.

## 8. Evaluación del modelo final

## 8.1 Accuracy

La accuracy permitió medir el porcentaje global de predicciones correctas.

Sin embargo, no fue interpretada como única medida de éxito, ya que puede ser insuficiente en problemas con varias clases y distribución desigual.

## 8.2 F1-score y F1-macro

El F1-score combina precision y recall en una sola métrica.

El F1-macro fue especialmente importante porque calcula el promedio del F1-score por clase, dando el mismo peso a todas las categorías.

Esto resulta relevante en un problema como el abandono estudiantil, donde no interesa únicamente acertar en la clase mayoritaria, sino también analizar el comportamiento del modelo en las clases más sensibles o difíciles de clasificar.

## 8.3 Matriz de confusión

La matriz de confusión permitió observar los aciertos y errores del modelo por clase.

Esta herramienta ayudó a identificar en qué categorías el modelo clasificaba mejor y dónde se producían más confusiones.

En un contexto educativo, este análisis es especialmente importante porque no todos los errores tienen el mismo impacto. Por ejemplo, clasificar erróneamente a un estudiante con riesgo de abandono puede limitar la posibilidad de intervención temprana.

## 8.4 AUC-ROC multiclase

El AUC-ROC multiclase se utilizó como métrica complementaria para evaluar la capacidad del modelo de distinguir entre categorías.

Esta métrica permitió tener una visión adicional del rendimiento del modelo más allá de la matriz de confusión y el F1-score.

## 8.5 Validación cruzada estratificada

Además de evaluar el modelo sobre el conjunto de prueba, se aplicó validación cruzada estratificada.

La validación cruzada permite entrenar y evaluar el modelo varias veces sobre distintas particiones del dataset.

Al ser estratificada, mantiene la proporción de clases en cada partición, lo que aporta una evaluación más robusta y reduce la dependencia de una única división entrenamiento-prueba.

## 9. Interpretabilidad con SHAP

La interpretabilidad fue una parte clave del proyecto.

XGBoost puede ofrecer buen rendimiento predictivo, pero no siempre es fácil entender directamente por qué realiza una predicción determinada.

Por esta razón se utilizaron **SHAP values**.

SHAP permite estimar la contribución de cada variable a la predicción del modelo. Cada valor SHAP indica cuánto empuja una variable la predicción hacia una clase determinada o en sentido contrario.

En este proyecto, SHAP permitió analizar:

- Qué variables tenían mayor importancia global.
- Qué peso tenían las variables académicas.
- Cómo influían las calificaciones y unidades aprobadas.
- Qué señales estaban asociadas al riesgo de abandono.
- Cómo interpretar el modelo en un problema multiclase.

## 9.1 SHAP summary plot tipo bar

El gráfico SHAP tipo bar permitió identificar las variables con mayor importancia global.

Este gráfico resume la magnitud media del impacto de cada variable en las predicciones del modelo.

Las variables con mayor valor absoluto medio de SHAP son las que más influyen en el comportamiento general del modelo.

En este proyecto, las variables académicas del primer y segundo semestre destacaron como especialmente relevantes.

Esto refuerza la idea de que el rendimiento académico temprano es una señal importante para anticipar la trayectoria académica del estudiante.

## 9.2 SHAP beeswarm plot

El gráfico beeswarm permitió analizar no solo qué variables eran importantes, sino también cómo se distribuía su impacto entre los distintos estudiantes.

Cada punto representa una observación del dataset. El gráfico permite ver cómo los valores altos o bajos de una variable influyen en las predicciones.

Este tipo de gráfico es útil porque muestra la dispersión del impacto de cada variable. Una misma variable puede influir de forma diferente según el perfil del estudiante.

El beeswarm aportó una interpretación más rica que una simple lista de importancia de variables, ya que permitió observar patrones de comportamiento dentro del modelo.

## 9.3 Valor añadido de SHAP

El uso de SHAP permitió transformar el modelo en una herramienta más explicable.

En lugar de limitarse a indicar que XGBoost obtuvo determinado rendimiento, SHAP permitió responder preguntas como:

- Qué variables influyen más en la predicción.
- Qué papel tiene el rendimiento académico temprano.
- Cómo contribuyen las unidades aprobadas y las calificaciones.
- Qué señales pueden ser útiles para estrategias de seguimiento académico.

Esto es especialmente importante en un contexto educativo, donde las predicciones deben interpretarse con cuidado y no utilizarse como decisiones automáticas.

## 10. Errores, dificultades y correcciones realizadas

Durante el desarrollo del proyecto se encontraron diferentes dificultades técnicas y metodológicas.

Estos errores forman parte normal de un proyecto real de análisis de datos y permitieron mejorar el flujo de trabajo.

## 10.1 Errores relacionados con variables categóricas

Uno de los errores encontrados estuvo relacionado con variables categóricas no transformadas.

Algunos modelos no aceptan columnas en formato texto, por lo que fue necesario revisar los tipos de datos y aplicar codificación.

La corrección consistió en transformar las variables categóricas a formato numérico antes del entrenamiento.

## 10.2 Problemas por alta cardinalidad

Algunas variables tenían muchas categorías distintas.

Esto podía generar problemas al codificarlas directamente, ya que podía aumentar la complejidad del dataset y añadir ruido al modelo.

La solución fue revisar estas variables con más cuidado y aplicar un tratamiento más controlado.

## 10.3 Variables académicas altamente correlacionadas

Durante el análisis exploratorio se identificaron variables académicas muy relacionadas entre sí.

Esto ocurrió especialmente con variables como unidades curriculares acreditadas, matriculadas, evaluadas y aprobadas en ambos semestres.

Esta situación no se interpretó como un error, sino como un aspecto técnico a tener en cuenta.

Algunas variables podían estar capturando dimensiones similares del rendimiento académico, por lo que fue necesario interpretar los resultados con cautela.

## 10.4 Diferencia entre resultados en test y validación cruzada

Otro punto importante fue distinguir entre la evaluación sobre el conjunto de prueba y los resultados obtenidos mediante validación cruzada.

El conjunto de prueba permite evaluar el modelo en una partición concreta de datos no vistos.

La validación cruzada permite estimar la estabilidad del modelo a través de varias particiones.

Comprender esta diferencia fue importante para interpretar correctamente las métricas y evitar conclusiones basadas en una única división de los datos.

## 10.5 Ajuste de hiperparámetros

Durante el ajuste de hiperparámetros con GridSearchCV se probaron distintas combinaciones.

El resultado mostró que la mejora del modelo optimizado fue moderada.

Esto es habitual en proyectos reales: la optimización no siempre produce grandes saltos de rendimiento, pero permite justificar mejor la configuración final del modelo.

## 10.6 Correcciones en gráficos SHAP

Durante la generación de gráficos SHAP fue necesario ajustar el código.

La principal dificultad estuvo relacionada con la estructura de los valores SHAP en un problema multiclase.

En clasificación multiclase, SHAP puede devolver los valores en una estructura diferente a la esperada, por lo que fue necesario revisar la salida del explainer y adaptar el código.

Finalmente se generaron correctamente dos gráficos principales:

- SHAP summary plot tipo bar.
- SHAP beeswarm plot.

Estos gráficos permitieron interpretar tanto la importancia global de las variables como la dispersión de su impacto.

## 11. Consideraciones sobre el desbalance de clases

El dataset no presentaba una distribución perfectamente equilibrada entre clases.

Por este motivo, el rendimiento del modelo no se evaluó únicamente con accuracy.

Se utilizaron estrategias como:

- División estratificada de entrenamiento y prueba.
- Validación cruzada estratificada.
- Métricas por clase.
- F1-macro.
- Matriz de confusión.

En este proyecto no se aplicó sobremuestreo o submuestreo como estrategia principal. Se priorizó mantener una evaluación cuidadosa del rendimiento por clase y evitar interpretar la accuracy como única medida de éxito.

## 12. Limitaciones del proyecto

El proyecto presenta algunas limitaciones importantes.

En primer lugar, el dataset corresponde a un contexto institucional específico. Por tanto, los resultados no deben generalizarse automáticamente a cualquier universidad o sistema educativo.

En segundo lugar, el análisis está condicionado por las variables disponibles. Puede haber factores relevantes para el abandono que no estén incluidos en el dataset, como motivación personal, salud mental, apoyo familiar, distancia al centro educativo o situación laboral detallada.

En tercer lugar, el modelo identifica patrones estadísticos, pero no establece causalidad. Que una variable sea importante para el modelo no significa necesariamente que sea la causa directa del abandono.

También debe considerarse que la clase de estudiantes matriculados puede ser más difícil de clasificar, ya que representa una situación intermedia o no definitiva.

## 13. Consideraciones éticas

El uso de Machine Learning en educación requiere especial cuidado.

Un modelo de predicción de abandono no debe utilizarse para etiquetar negativamente a los estudiantes ni para tomar decisiones automáticas sin intervención humana.

Su uso adecuado sería como herramienta de apoyo para:

- Identificar señales tempranas.
- Priorizar seguimiento académico.
- Diseñar estrategias de acompañamiento.
- Mejorar la orientación estudiantil.
- Apoyar decisiones institucionales basadas en datos.

La interpretación humana sigue siendo fundamental.

El modelo puede actuar como un sistema de alerta, pero no debe sustituir el criterio académico, pedagógico o institucional.

## 14. Conclusión técnica

Este proyecto muestra cómo un flujo completo de Data Science puede aplicarse a un problema educativo real.

A través de la metodología CRISP-DM, se abordó el problema desde la comprensión inicial del contexto hasta la interpretación final de resultados.

El modelo XGBoost fue seleccionado como modelo final por su rendimiento y por su capacidad de ser interpretado mediante SHAP.

Los resultados mostraron que el rendimiento académico temprano es uno de los factores más relevantes en la predicción del abandono estudiantil.

Más allá de la clasificación, el proyecto aporta una lectura analítica del fenómeno del abandono y muestra cómo el Machine Learning puede apoyar procesos de seguimiento, prevención y toma de decisiones en educación superior.
