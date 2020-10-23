# Comentario "Deep Learning based Recommender System: A Survey and New Perspectives" (primera mitad)

Esta primera mitad del texto busca introducir el tema de Deep Learning en el ámbito de los sistemas recomendadores. En primer lugar, se definen los términos claves,
como sistema recomendador, Deep Learning, red neuronal, etc. También explica cómo estos conceptos se pueden relacionar y de qué forma se pueden complementar.
En el tema de Deep Learning, el autor separa el tema en varias implementaciones (MLP, AE, etc.). Estas técnicas son todas aplicables a los sistemas recomendadores,
y en la sección 3 se encarga de explicar cómo implementarlas. 

Es muy evidente que el Deep Learning ha aumentado rápidamente en popularidad en esta última década debido a la precisión extrema de sus resultados. En muchos ámbitos de nuestra
actividad online podemos encontrar cantidades enormes de información, con la cual podemos entender mucho acerca de los usuarios, los servicios y los productos. Es importante
destacar que la obtención de información tan específica se puede lograr solamente con un flujo gigante de datos, ya que se obtienen comportamientos que, en muchos casos, ni el
usuario sabe que tiene, y esto solo es posible con las correlaciones que se generan en las extensas redes de datos. Es por esto que, en mi opinión, esta tecnología no podría haber
llegado más temprano. Estamos viviendo una época en que la información es prácticamente dinero que se transa, y genera miles de millones de transacciones todos los días. Por eso,
hoy en día se puede superar fácilmente la barrera más grande que tiene el Deep Learning, que es su "arranque en frío" deficiente, es decir, su baja capacidad para funcionar con
poca información. Por esto es mala idea implementar esta técnica en ámbitos con poco acceso a información, como podría ser un "start-up".

Para aplicar Deep Learning a la recomendación, se ven tres técnicas (en esta mitad del texto): Multilayer Perceptron (MLP), Autoencoder (AE) y Convolutional Neural Network (CNN).
Se entiende que el MLP se complementa muy bien con la factorización matricial (un proceso lineal) debido a que puede agregar un "approach" no-lineal (por el uso de redes
neuronales) a la obtención de los factores latentes de los productos. Además, su estructura en capas puede aumentar significativamente la precisión de la recomendación. 
