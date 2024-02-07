# clasificacionNumeros
Modelo de regresion para clasificar numeros 
Trabajo de maestría UIDE - Modelos de datos
#Integrantes GRUPO 1
    - Sebastián Vaca Alarcón
    - Edwin Chacón cajamarca
    - Ivonne Campoverde Pilco
    - Jimmy Tarira Pérez
    - Sandra Montúfar Rivera
    
#Fuentes de datos
 - mnist_test.csv
 -   test_df = pd.read_csv('./data/mnist_test.csv')
 - mnist_train.csv
 -   train_df = pd.read_csv('./data/mnist_train.csv')

#Liberias Utilizadas
    -Pandas ->import pandas as pd -> utilizada para cargar u manipular los datos de los csv's.
    -Sklearn -> utilizada para aplicar los algoritmos de clasificación.
           - from sklearn.model_selection import train_test_split - dividir el conjunto de datos de entrenamiento
              -  X_train, X_test, y_train, y_test = train_test_split(X, y, test_size = 0.33, random_state = 42)
           - from sklearn.linear_model import LinearRegression - generar una regresión lineal de los datos de entrenamiento
              - %%time
                reg = LinearRegression()
                y_train = reg.fit(X_train, y_train)
           - import sklearn.metrics as sklm - utilizada para evaluar la metricas que evaluan el porcentaje de error y predicción
                mse = mean_squared_error(y_test, y_predict)
                  r2s = r2_score(y_test, y_predict)

  #Descripción general
   Creación de característica: 
      - "cuanto_mancha"  - train_df['cuanto_mancha'] = train_df.iloc[:, 1:].sum(axis=1)
     -  "simetia". train_df['simetria'] = train_df['sum_left'] - train_df['sum_right']
       Nota: La simetría se la realizó restando la parte de arriba menos la parte de abajo. 
   
   #Creación del modelo
   1. Para crear el modelo y entrenarlo se tomaron las 2 características nuevas creadas.
   2. Se eligió el modelo de regresión lineal. 
   3. Una vez entrenado el modelo se lo evaluó con la matriz de confusión de sklearn. 
   4. Se dibujó la matriz de confusión lo que nos ilustra que las características elegidas no son suficiente para que se reconozcan los números.
    
    
    
