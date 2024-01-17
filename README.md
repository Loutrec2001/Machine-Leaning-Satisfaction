## Machine-Leaning-Satisfaction
Análisis de sentimientos sobre APP modelo de Machine Learning - Boosting Gradient, Decision Tree, Naive Bayes

# Datos y ETL
Se realiza la recopilación de los datos (6855) que tienen en cuenta:
*  App Versión: Versión de la App
*  Customer comment date: Fecha de realización del comentario
*  Star Rating: Cantidad de estrellas realaionadas a la calificación de la App
*  Customer_review: Comentario sobre la app

Se realiza del mismo modo, la depuración de los datos, eliminación de datos nulos y normalización de los mismos. Tratamiento de los datos atípicos a través de Box Plot.

# Análisis descriptivo

Se realiza un análisis simple de las distribuciones de probabilidad de algunas variables, se realizan diagramas de conteo y un análisis descriptivo de la versión de la App teniendo en cuenta cuartiles maximos y mínimos.

# Análisis de Sentimientos

Realizamos un análisis de setimientos a través de varias modulos de Python con el fín de encontrar el analizados mas optimo, este análisis se realiza sobre el comentario sobre la app dando como resultado tres opciones, Negativo, Neutro, Positivo. Los modulos utilizados son:

* Hugging Face
* NLTK
* TextBlob
* Spacy
* PySentimiento 

# Tokenizar y Stopwords

Se utiliza NLTK para la tokenización y la eliminación de Stopwords y de este modo poder realizar el modelo de Machine Learning para determinar el sentimiento para cada nuevo comentario sobre una App.

# Modelo Machine Learning

Se realiza la lematizacion, la vectorización y adicionalmente para evaluar el modelo se utilizan las métricas (accuracy_score, classification_report y confusion_matrix).

Los modelos de predicción son:

* Naive Bayes:

1 - En este caso, el modelo tiene una exactitud de aproximadamente 0.94, lo que significa que el 94% de las predicciones son correctas.
2 - La matriz de confusión muestra la cantidad de predicciones correctas e incorrectas para cada clase

Para la clase "Negativo", el modelo hizo 5 predicciones correctas, 48 incorrectas y 0 omisiones.
Para la clase "Neutral", el modelo hizo 1268 predicciones correctas, 0 incorrectas y 0 omisiones.
Para la clase "Positivo", el modelo hizo 22 predicciones correctas, 28 incorrectas y 0 omisiones.

3 - El informe de clasificación proporciona métricas adicionales como precisión, recall y F1-score para cada clase.
  - Las métricas se calculan para cada clase por separado y luego se promedian para obtener métricas macro y ponderadas.
  - Precision (Precisión): La precisión es la proporción de predicciones correctas positivas entre todas las predicciones positivas. Por ejemplo, para la clase "Negativo", todas las predicciones correctas fueron negativas, dando una precisión de 1.00.
  - Recall (Recuperación o Sensibilidad): La recuperación es la proporción de instancias positivas que fueron correctamente identificadas. Por ejemplo, para la clase "Positivo", el modelo identificó correctamente el 44% de las instancias positivas.
  - F1-score (Puntuación F1): El puntaje F1 es una medida que combina precisión y recuperación en un solo número. Es útil cuando hay un desequilibrio entre las clases.

* Arbol de desición:

1 - En este caso, el modelo tiene una exactitud de aproximadamente 0.99, lo que significa que el 99% de las predicciones son correctas. Es un resultado excelente.
2 - Para la matriz de confusión:

* Para la clase "Negativo", el modelo hizo 47 predicciones correctas, 6 incorrectas y 0 omisiones.
* Para la clase "Neutral", el modelo hizo 1263 predicciones correctas, 3 incorrectas y 2 omisiones.
* Para la clase "Positivo", el modelo hizo 48 predicciones correctas, 2 incorrectas y 0 omisiones.

3 - Para el Informe de clasificación:
 - Precision (Precisión): Las clases "Negativo", "Neutral" y "Positivo" tienen altas precisiones, indicando que la mayoría de las
 predicciones positivas son correctas.
 - Recall (Recuperación o Sensibilidad): Todas las clases tienen altos valores de recuperación, lo que sugiere que el modelo identifica
 correctamente la mayoría de las instancias positivas.
 - F1-score (Puntuación F1): Todas las clases tienen altas puntuaciones F1, que es una medida equilibrada entre precisión y recuperación.


* Descenso del gradiente:

1 - En este caso, el modelo de Gradient Boosting tiene una exactitud de aproximadamente 0.99, lo que significa que el 99% de las predicciones son correctas. Esto es consistente con el rendimiento del árbol de decisión.
2- La matriz de confusión es idéntica a la del árbol de decisión:

* Para la clase "Negativo", el modelo hizo 47 predicciones correctas, 6 incorrectas y 0 omisiones.
* Para la clase "Neutral", el modelo hizo 1263 predicciones correctas, 3 incorrectas y 2 omisiones.
* Para la clase "Positivo", el modelo hizo 48 predicciones correctas, 2 incorrectas y 0 omisiones.

3 - El informe de clasificación también es idéntico al del árbol de decisión:
 - Precision (Precisión): Las clases "Negativo", "Neutral" y "Positivo" tienen altas precisiones, indicando que la mayoría de las predicciones positivas son correctas.
 - Recall (Recuperación o Sensibilidad): Todas las clases tienen altos valores de recuperación, lo que sugiere que el modelo identifica correctamente la mayoría de las instancias positivas.
 - F1-score (Puntuación F1): Todas las clases tienen altas puntuaciones F1, que es una medida equilibrada entre precisión y recuperación.

## Conclusión

El modelo Naive tiene una buena exactitud general, pero la clase "Negativo" muestra un rendimiento deficiente en términos de precisión, recuperación y puntuación F1. Puede ser útil examinar más a fondo las características específicas de esa clase o considerar la posibilidad de mejorar el modelo con técnicas más avanzadas o ajustes de parámetros.

El modelo de árbol de decisión muestra un rendimiento muy sólido en la clasificación de las clases de sentimientos, con alta precisión, recuperación y exactitud global.

En resumen, el modelo Gradient Boosting también muestra un rendimiento excepcionalmente alto en la clasificación de las clases de sentimientos, manteniendo una precisión y recuperación robustas en todas las clases. Puedes considerar estos resultados como muy prometedores para tu tarea de análisis de sentimientos.

