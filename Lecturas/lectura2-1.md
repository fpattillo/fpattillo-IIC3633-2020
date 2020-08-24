# Comentario "Collaborative Filtering for Implicit Feedback Datasets"

Este texto plantea un sistema capaz de predecir los gustos de personas a partir de información implícita, es decir, la persona no necesita ingresar un rating o sus preferencias para que el algoritmo funcione. El funcionamiento de este proceso puede basarse en varios indicadores dependiendo del área de interés del sistema.

En el caso de este paper, se busca implementar para un servicio de televisión. El indicador que utiliza el programa para conocer los gustos de los clientes es, en pocas palabras, el "watch time". Se define una variable (en números reales) r_ui que indica la cantidad de veces que el usuario u ve el show i. Por ejemplo, si el usuario ve la mitad de una función, el valor de r será de 0.5.