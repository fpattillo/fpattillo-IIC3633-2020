# Comentario "Performance of Recommender Algorithms on Top-N Recommendation Tasks"
---

De manera resumida, el texto trata de solucionar el problema de recomendar, utilizando feedback implícito, los "Top-N" productos a un usuario. Es decir, encontrará los N productos que considera que más le gustarán al usuario, y los ordena de mejor a peor.
Un problema que se presenta inmediatamente es que, usualmente los algoritmos buscan minimizar las métricas de error (RMSE/MAE). Sin embargo, minimizar estas métricas no necesariamente significa un Top-N más acertado. Por esto, el texto propone fijarnos en métricas de exactitud (recall/precision).
Para describir la situación, se usa el ejemplo de predicciones Top-N con ratings en Netflix y MovieLens.

Un concepto interesante que se introduce es el "short-head/long-tail rating distribution", el cual aplica no solamente para los servicios de películas/series, sino que también aplica para cualquier servicio que implemente una forma de rating. Básicamente, el "short-head" se refiere a los productos populares. Se le llama así porque estos concentran la mayor parte de los ratings en una cantidad baja de productos y, gráficamente genera una región bastante achatada de datos. Inversamente, el "long-tail" contiene (proporcionalmente) muchos menos ratings para muchos más productos. Esta distribución permite separar los datos en populares y no populares. Yo encuentro que la separación es relevante porque no tiene mucha utilidad recomendar siempre lo más popular, ya que los sistemas recomendadores buscan sugerir (en parte) productos que quizás el usuario no encontraría por su cuenta.

Luego de una descripción de tres modelos comunes (no-personalizado, KNN, factor latente) previamente visitados, hablan acerca de un modelo de factor latente que ellos llaman PureSVD. Este consiste en representar a los usuarios y a las películas con un conjunto de factores, y luego con productos matriciales predecir las relaciones que los usuarios pueden tener con las películas. Las cosas que separan a PureSVD de algunos otros modelos similares es que (1) también se consideran los pares user-item que no tienen rating (se reemplazan por ceros), (2) que no existe una parametrización exclusiva para cada usuario y (3) que todo se monta sobre "packages" optimizados SVD. Me imagino que todos estos factores crean un proceso más liviano y confiable. También, volviendo a la separación short-head/long-tail, este "approach" despersonalizado ayudará mucho en los casos "long-tail" donde no hay mucha información.

Observando los resultados, está claro que PureSVD y los otros modelos que buscan exactitud, predicen mejor el Top-N que los modelos que tratan de disminuir error. Además, se puede decir que es un modelo flexible. Es capaz de adaptarse a nuevos ítems, debido a su forma despersonalizada, y también es capaz de adaptarse a los ítems "long-tail", aumentando la cantidad de factores que considera para mayor especificidad.







