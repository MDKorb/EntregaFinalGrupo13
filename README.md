# Entrega 4 de Data scientist: Recomendación de películas


## Introducción


En esta era de la conectividad constante, las plataformas de streaming ofrecen una amplia gama de programas, películas y documentales. Seleccionar qué mirar puede tomar gran parte del tiempo disponible del espectador. Por ello, este proyecto propone un análisis para guiar la elección de películas de forma rápida y personalizada según las preferencias del usuario, además de ser útil para empresas cinematográficas. Se aplican técnicas de data science para explorar los datos y construir modelos de aprendizaje supervisado y no supervisado.


## Objetivo


# Objetivo general:  elaborar un sistema de recomendación tomando la calificación final de una película como indicador de aceptación por el público.


# Objetivo específico 1: analizar la aceptación de películas por protagonista, director, genero y país de origen según calificación promedio y una nueva variable, Porcentaje_likes.


# Objetivo específico 2: determinar si existe relación, y cómo se comporta, entre las variables vistas, duración y likes con la calificación final.



## Integrantes


Grupo Nº 13  

Natalia Machetti y Melisa Korb


## Dataset utilizado


El dataset fue extraído de [Kaggle - 10000 Movies Letterboxd Data](https://www.kaggle.com/datasets/ky1338/10000-movies-letterboxd-data). Contiene 10.002 registros de películas de diversos géneros y décadas, recopilados el 8/4/2025 desde una lista de Letterboxd diseñada como una ruleta de películas.


## Estructura del repositorio


- `Movie_Data_File2.csv

- `Peliculas_4preentrega.ipynb

- `README.md


## Metodología


1. **Limpieza de datos:**  

   - Tratamiento de variables categóricas (separación, unificación de valores).  

   - Creación de la variable `Porcentaje_likes`.  

   - Imputación de datos faltantes y eliminación de filas con valores categóricos faltantes.  

   - Análisis y manejo de outliers, incluyendo eliminación de series por no formar parte del objetivo de nuetro trabajo.


2. **Análisis exploratorio:**  

   - Caracterización del dataset por cantidad y tipo de variables.  

   - Análisis de distribución y tratamiento de variables.


3. **Visualización**

   - Histograma

   - Correlación 


### Modelo de aprendizaje supervisado


   **Escalado de las variables:** las variables con distribución normal (Calificación_promedio y Duración) fueron Estandarizadas con z-score y las que presentaban sesgo (Vistas, Ratings, y Porcentaje_likes) Normalización con Min-MaxScaler.


   **Exploración, eliminación y renombramiento luego de la Normalización y Estandarización:** se realizó una nueva exploración de las columnas y tipos de variables, se dejaron aquellas objeto de análisis ya estandarizadas o normalizadas. Se renombraron las columnas numéricas.


   **Transformación con One Hot Encoding:** Debido a que las variables a transformar son categóricas y no tienen un orden predeterminado utilizamos OneHotEncoding. Las variables categóricas transformadas son 'Director', 'Genero', 'Pais', 'Lenguaje', 'Productora', 'Protagonista' y 'Coprotagonista'.


Debido a que la variable a predecir ‘Calificación’ es numérica optamos por aplicar modelos de regresión.


##### Árbol de decisión


Aplicamos el modelo, ajustamos algunos hiperparámetros, evaluamos las metricas y visualizamos el gráfico.


##### Random Forest


Aplicamos el modelo Random Forest por defecto, luego ajustamos parámetros con RandomizedSearchCV, ampliamos el número de iteraciones y por ultimo realizamos una busqueda fina alrededor de los hiperparámetros del mejor modelo. 


Realizamos el gráfico y visualizamos las 10 variables más importantes para la predicción del modelo.


##### Comparación de mejor modelo entre árbol de desición y random forest.


##### Utilización de Cross_validation sobre el mejor modelo y visualización de la curva de aprendizaje.


##### Regresión lineal


##### Concluiones Modelo aprendizaje supervizado


### Modelo de aprendizaje no supervisado


   **Transformación de datos:**  

   - Aplicación de One Hot Encoding a variables categóricas: Director, Género, País, Lenguaje, Productora, Protagonista y Coprotagonista.  

   - Conversión de variables booleanas a enteros.


##### KMeans 


Se optimizó el numero de clusters optimizando parametros con Elbow, Silhouette Score, PCA y Elbow y modificando el rango. Se realizo K-Means aplicando los diferentes valores de k hallados y se visualizaron los resultados.


##### DBSCAN 


Se optimizaron los parámetros Eps y Min-samples. Luego se aplicó el modelo, las métricas y se visualizaron los resultados.


##### Gaussian Mixture Models (GMM).  


Se optimizaron parámetros con Silhouette Score, BIC y AIC para mejorar resultados. Se realizó el analisis de clusters. 

 

##### Conclusiones Modelo aprendizaje no supervizado

      

## Herramientas utilizadas


- Python  

- Librerías: pandas, numpy, scikit-learn, matplotlib, seaborn, scipy


