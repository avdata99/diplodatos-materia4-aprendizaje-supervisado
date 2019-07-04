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

