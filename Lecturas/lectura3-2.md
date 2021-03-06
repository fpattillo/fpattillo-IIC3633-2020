# Comentario "Evaluating Recommendation Systems"
---
Este capítulo se centra en describir cómo encontrar el mejor algoritmo de recomendaciones para una situación dada. Comienza con tres tests posibles que se pueden hacer con el sistema, con distintos propósitos y también distintos costos. Estos tienen el fin de descartar algoritmos hasta encontrar al mejor. No son excluyentes, (de hecho, en mi opinión son bastante complementarios) por lo que se pueden usar los recursos necesarios para tomar la decisión más informada posible.

Después, los autores definen distintas áreas en las que un sistema recomendador debe ser fuerte, y cómo se puede testear el sistema en esa área específica. Esto, aparte de dar una idea de la eficacia y de lo robusto que es un algoritmo, también debe ser útil para descartar algoritmos según las prioridades que tenga el desarrollador. Por ejemplo, puede ver mucho valor en que un algoritmo sea mantenible en el tiempo, pero no necesariamente tenga como primera prioridad la privacidad de las preferencias de los usuarios. Esta categorización permite al desarrollador considerar todo un espectro de posibilidades para cumplir sus necesidades y las de sus clientes.

Me gustaría profundizar el tema que toqué en el primer párrafo de introducción, que hablaba acerca de los tres tests que los autores sugieren para ir filtrando los candidatos y elegir un algoritmo competente.

El primer test (offline) consiste en usar datasets antiguos para intentar simular el comportamiento de usuarios en el futuro. La principal desventaja que sugieren es que esto no refleja el comportamiento de un usuario usando el programa real con su interfaz, y con sus decisiones en tiempo real. Sin embargo, creo que si el sistema es suficientemente parecido, y el dataset es de buen tamaño, el comportamiento debería traducirse bien al nuevo sistema. En cualquier caso, concuerdo con que este test se debería hacer siempre en etapas tempranas por su bajo costo y bajo riesgo.

El siguiente test (user studies) consiste en que usuarios puedan ingresar al sistema y utilizar la interfaz con el fin de analizar su comportamiento y su reacción al usarlo. Creo que esta opción es genial debido a que la amplia gama de preguntas que se le pueden hacer (questionnaire) son de muy alto valor. No se tiene la restricción del feedback implícito y creo que el problema que se plantea de encontrar al sujeto adecuado no es un gran problema ya que se puede hacer un proceso de filtrado para seleccionar gente.

Finalmente, el último test (online evaluation) consiste en liberar los candidatos de sistemas a usuarios online, redirigiendo grupos de personas a distintos sistemas y luego comparar las experiencias. Creo que es un método costoso y bastante arriesgado, por el tema de que los usuarios pueden quedar con una mala impresión si el sistema no es adecuado. Por otro lado, creo que puede aportar mucha información de la calidad del sistema y de su capacidad de sobrevivir en el tiempo, pero eso es solamente si se filtran anteriormente los sistemas inferiores usando los otros dos métodos. Creo que si se logra un "shortlist" de unos tres sistemas candidatos, este método será un gran aporte. Si por un lado los user studies dan una explicación mucho más "in-depth" de lo que los usuarios buscan en un sistema, este método puede pintar una imagen mucho más clara del sistema a gran escala, funcionando con una gran cantidad de usuarios que contribuyen a su funcionamiento.







