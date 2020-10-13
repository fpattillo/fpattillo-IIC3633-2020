# Comentario "Multi-Armed Recommender System Bandit Ensembles"

## Introducción

Este texto profundiza sobre la efectividad de sistemas recomendadores ensamblados, o compuestos por varios algoritmos trabajando en conjunto. La diferencia con los textos anteriores que se han tratado del mismo tema, es que aquí se busca ir aún más allá, tomando en cuenta el output de una iteración para el proceso de la siguiente iteración. De manera resumida, se busca optimizar el proceso adaptando el modelo según las necesidades de la iteración actual, y no manteniendo un modelo estático. Los autores plantean que al mantenerse estático el modelo, este puede ir degradándose y perdiendo efectividad con nuevas iteraciones.

## El problema "Multi Armed Bandit" :slot_machine:

Se menciona a lo largo del texto un problema de probabilidad conocido como el "Multi Armed Bandit", sin embargo no se entra en detalle acerca del origen de este. El nombre viene de las máquinas "tragamonedas" que a veces en inglés se les dice "one-armed bandits" debido a la palanca que posee, que se utiliza para comenzar a jugar. El problema, de manera resumida, consiste en maximizar ganancias eligiendo las máquinas precisas (una por iteración), explotando las máquinas que entregan buenos resultados, y constantemente aprendiendo de todas las máquinas para elegir la mejor opción en cada iteración.

## Aplicación del problema

Análogamente, el problema de la recomendación, y específicamente, los sistemas recomendadores compuestos por varios algoritmos, también se puede optimizar seleccionando en cada iteración el algoritmo más apropiado dado el contexto actual de los datos. En el caso de los autores, seleccionaron tres métodos muy comúnes para recomendar: kNN, factorización matricial y "most popular" (sin personalizar). Los datos usados, el dataset de MovieLens, también es uno usado regularmente para este tipo de experimentos. Luego, cada recomendación se considera negativa (valor 0) si el usuario la califica entre 1-3, y positiva si le asigna un 4 o un 5 (valor 1).

Para elegir entre los tres posibles algoritmos, se utilizan dos métodos, $/epsilon$-greedy y "Thompson sampling". El primero consiste en otorgar un valor 1 - $/epsilon$ al algoritmo que ha retornado los resultados más positivos, luego, con probabilidad $/epsilon$ se definirá un algoritmo distinto, todos con probabilidad uniforme. En el caso del "Thompson sampling", se toman los casos positivos y negativos de cada algoritmo, y se obtiene un valor "p", usando la distribución Beta. Luego se elige el algoritmo de mayor valor "p". En mi opinión, la segunda opción suena más correcta, ya que en el primer caso, la probabilidad de obtener el segundo mejor algoritmo es la misma que para obtener el peor algoritmo. Creo que es mejor tener en cuenta todas las posibilidades para variar de manera sensata el modelo.

En cualquier caso, tanto el $/epsilon$ como el "Thompson sampling" producen resultados favorables cuando se comparan con los algoritmos singulares y con un ensamblaje de los tres. Creo que es una forma muy eficiente de resolver el problema de la recomendación, porque tiene la ventaja de ir evolucionando constantemente, y además se utilizan menos recursos ya que no se tienen que emplear múltiples algoritmos en cada iteración.

## Comentarios adicionales :sparkles:

Una breve investigación me llevó a un método que creo que podría mejorar el modelo en casos donde la cantidad de datos sea más extensa. La estrategia se llama "$/epsilon$-decreasing strategy", y consiste en tener un valor alto inicial para $/epsilon$, que vaya disminuyendo con cada iteración. Esto implica que al principio hay major variación entre las estrategias, y a medida que se conoce más acerca de las distintas alternativas, el $/epsilon$ toma un valor más fijo. El problema que tendría esta estrategia con los cantidades de datos pequeñas, es que se pueden perder iteraciones muy valiosas en encontrar los modelos más efectivos, y se pueden generar muchas iteraciones seguidas con modelos inútiles o ineficientes.
