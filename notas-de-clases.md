# Aprendizaje Supervisado 

## Repo de las clases

[Acá](https://github.com/DiploDatos/AprendizajeSupervisado/tree/master/archive/2018).  

## Notas de clase

Dados un conjunto de datos _anotados_ (con resultados) aprender un modelo que va a predecir el estado de nuevos datos no anotados.  

Una _regresión_ es un tipo de estos modelos.
Otro tipo de problema es el de _clasificación_ (los resultados pertenecen o no a una categoría).  

Otra vez, separar los datos anotados en:
 - Entrenamiento: Aca obtengo el modelo y sus parametros
 - Validación: Me ayudo a definir los hiperparámetros
 - Test: solo uso **al final**. Si no anda, tiro **todo** a la basura y empiezo de nuevo. No uso _test_ para seguir ajustando.


Normalizar y estandarizar (uno es poner todos los valores en el mismo rango y el otro es ponerlos específicamente entre 0 y 1) todos los valores es útil por cuetiones internas de muchos algoritmos (por ejemplo el descenso por gradiente se agiliza en muchos casos).  

Ver la ley de Zipf (las cosas humanas tienen distribucion exponencial): ej la palabra mas usada de un texto aparece el doble de veces de la segunda y la tercera la mitad que la segunda.  

## Algoritmo del perceptron. 

Propuesta en 1958. Son la base de las redes neuronales.  

## Ejemplo de SVM

Link al kernel de Clasificacion SVM con tarjetas de crédito: https://www.kaggle.com/pierra/credit-card-dataset-svm-classification  
Jugar con este que es un ejemplo real.  
 
## Sobre el práctico de esta materia

Es una competencia en Kaggle.

