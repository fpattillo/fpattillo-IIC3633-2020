# Comentario "Item-Based Collaborative Filtering Recommendation Algorithms"

Este paper describe las recomendaciones generadas de manera "item-based", y cómo se comparan con otras técnicas de recomendación, como "user-based recommendations".

Si nos centramos en un usuario X, la diferencia principal entre los dos métodos mencionados es que en el caso "user-based" se generan recomendaciones basadas en los usuarios similares a X. Si los usuarios similares evalúan de buena manera un item, se le recomendará a nuestro usuario X.

En el caso "item-based", si a nuestro usuario X le gusta un item Y, el sistema le recomendará otros items que considera que son similares a Y. Esta metodología tiene una ventaja clara por sobre "user-based", y es que cuando el sistema se comienza a poblar de manera masiva, iterar sobre millones de usuarios es muy costoso. En cambio si buscamos items, es probable que sean datos mucho más estáticos y menores en tamaño.

Una parte importante de la recomendación "item-based" es encontrar la similitud entre items. Hay métodos que consideran los items como vectores que personalmente no me quedaron claros y no encuentro que fueron explicados con mucho detalle. El método restante para encontrar similitud entre dos items busca los usuarios que hayan calificado a ambos items, y si la calificación es la misma, o muy similar, hace que el algoritmo piense que los items son más similares. En mi opinión, este método solo sirve cuando hay una gran cantidad de datos, ya que puede ocurrir que a una persona simplemente le gustan varios items sin que tengan similitud alguna y se entrenaría el algoritmo para que piense que son similares. Sin embargo, con un flujo grande de entradas, se eligiría los que tengan más índice de similitud y en este caso se elimina el posible error. Otro fuente de error puede ser que un item sea transversalmente popular, y que calce con muchos perfiles, por lo que se podría recomendar de manera indiscriminada.

El paso más importante, según los autores, es la predicción de la calificación de nuestro usuario X. Dados los ratings de items similares, el sistema busca predecir el rating que nuestro usuario le daría a un item particular.

También se toca en temas de notación "big O", donde explica que un algoritmo "item-based" debe ir acompañado de un "model-based approach". A diferencia del "memory-based approach", este no guarda todos los datos conocidos para predecir, sino que utiliza probabilidades y algoritmos de Machine Learning. Esto me imagino que reduce drásticamente el uso de memoria y el tiempo de ejecución (big O). Otra medida para reducir complejidad, es que se eligen los k items más parecidos en vez de utilizar el set completo. Esto, en mi opinión, también reduce el error posible ya que los items con pocos casos de similitud no se considerarían en el proceso.

A modo de cierre, creo que es un texto con mucha información valiosa, que está presentada de manera formal e informativa. Creo que no es difícil de entender en su mayoría pero puede que los aspectos más técnicos requieran algo de experiencia para entender y aplicar. Creo que pudo haber aprovechado de usar más ejemplos, ya que en la actualidad estos sistemas están presentes en todos lados y ayuda tanto a la explicación como a la entretención del lector cuando se hacen estas relaciones.




