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

### Clase 3 (vie 2/8)

Clase 3:
https://docs.google.com/presentation/d/1mAsJ8XMya1jk2m-DFAP4NW5of5x8x-n0aZM7Tp4SzN4/edit  

Clase 4:
https://docs.google.com/presentation/d/1NPXFe5sgVsL3Cx9d5gt4O0OE0XaEuYbitzbEJQ0FXss/edit?usp=sharing

[Cristian Cardellino]

Ensamble learning: genera varios modelos, no uno solo. Estos modelos tienen la misma precisión y sus errores son independientes.  
En la práctica las precisiones pueden ser distintas y sabemos que no hay independencia pero para calcular asumimos estas cosas.  
Random forest es un tipo de ensamble learning.  

## Métos de ensamble learning

Bagging:  (ver slides)
Contras: Tarda mucho en entrenar. Si es sobre algo paralelizable es mejor.   
Baggin es bueno para árboles de decisión porque anda bien para cosas inestables.  

Random forest: Es un bagging que solo funciona para árboles de decisión.  
Aca simplificamos un poco para bajar el costo/tiempo de entrenamiento.  
Se achican el número de features (solo sirve si tengo muchos atributos).  
Aca no nos preocupamos por el overfit, hay que dejarlos correrlos hasta el final.  
El resultado NO ES un arbol (hay una función de scikit-learn que dibuja uno para representarlo, puede confundir) 
El resultado son muchos árboles, cada dato pasa por todos y devuelve el resultado que más árboles pronosticaron.  
La cantidad de features a utilizar es uno de los hiperparámetros de la función random forest.  

Boosting:  (ver slides)

## Redes Neuronales

Leer sobre algoritmo del perceptron.  
Si decimos que todo esto esta inspirado en la biología, los biólogos se van a enojar. Parece que no es tan así.  
REPASAR QUE ES UNA REGRESION LOGISTICA.  
Estas redes deben saber los mejores pesos para las conexiones de cada neurona en cada cada. El algoritmo de back propagation es muy feo pero muy bueno calculando estos pesos.  
Elegir cuantas capas internas es a ojo. Es una de las críticas a esto. Otro hiperparametro es el tamaño de cada capa.  
ESTO ES UNA TERRIBLE CAJA NEGRA CON NINGUNA POSIBILIDAD DE INTERPRETACIÓN.  
El peso es inicializado al azar.
Funciones de activación: Elegimos nosotros, es un hiperparámetro. Profe sugiere: Rectified linear unit.  
Las redes neuronales NO SIRVEN si tenemos pocos datos.  

## ¿Que es Deep Learning?

Redes neuronales profundas (mas de 10 capas x ejemplo). No hay un número cierto.  
Hay un teorema que dice que con una capa se puede representar cualquier función.  
En la práctica usar varias capas puede simplificar el proceso, puede hacerlo requiriendo menos _neuronas_.  
Las redes convolucionales (?) pueden tener 50 capas y se usan para imágenes o cosas complejas.  
Concejo: no entrenar redes neuronales desde cero con nuestros datos (que seguro van a ser pocos).  
Ej: Quiero identificar marca de autos y tomo una que ya está entrenada para autos, corto las ultimas capas (quizás una o dos) y entreno solo lo que falta.  
Ya hay datasets de imágenes anotadas. Se crearon con el tiempo y son un buen insumo.  

FIN + Cambio de profe 
[Matías Marenchino]

## Sistemas de recomendación
Hay varios tipos.  
Este es uno -> Colaborative filtering: los usuarios que coincidieron en algún _item_ en el pasado, coincidirán en el futuro.  
Acá se tienen en cuenta usuarios + items + score de cada uno. No hay features de los items.  
En _Content based fitering_ (o algo así) si están. Son más datos pero no funciona mejor. Sería mejor si tengo items nuevos muy seguido ya que me guío de sus features.  
Funciona mejor el _colaborative filtering_, al parecer entendemos que todas las features de los items ya están valoradas en las clasificaciones.  

Clase 4, sábado 3/8/2019  

Si tenes mucho más items que usuarios (o al revés) el enfoque puede cambiar.  
Podes usar las similitudes para simplificar el proceso.  
Se usa similitud coseno (leer sobre ella).  
Demo9 en el repo habla sobre esto.  
Crítica a scikit learning: no tiene cosas resueltas para sistemas de recomendación.  
Usamos la librería _surprise_ para estas cosas. En el demo está usado.  
Aca solo usamos usuarios, ratings e items. Si tenemos más features y queremos usarla deberíamos pensar esto como un problema de regresión y usar otras herramientas.  
El profe dice que por más que tuviera otros features, el empezaría por aca descartando todo. Esto es más rápido y barato. Además no tenemos garantías de que un enfoque más complejo daría mejores resultados.  
Recomiendan mucho ver clases online de Andrew Ng. Es buen profe y sabe mucho. El libro de el Machile Learning Yearning se consigue gratis en PDF, es corto y esta bueno.  
En R un compañero dice que si hay cosas para algoritmos de recomendación.  
KNIME y UEKA (o algo así) son productos de software más visuales que podrían ayudar.  

Por mas que el acuraccy y otras métricas den bien a veces mi modelo está clasificando _de pedo_, con poca certeza. Es importante ver esto porque un modelo así posiblemente cuando se empieze a usar no sea muy bueno. Si se identifica un caso así hay que buscar métricas que reflejen esto (creo que dijo [loss](https://developers.google.com/machine-learning/crash-course/descending-into-ml/training-and-loss?hl=es-419)).  






