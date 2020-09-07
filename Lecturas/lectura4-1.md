# Comentario "Document Clustering Based On Non-negative Matrix Factorization"

El texto describe un algoritmo cuya finalidad es clasificar documentos para facilitar su búsqueda. Los autores comienzan describiendo un espectro de "especificidad" donde a un extermo, se tiene una búsqueda puntual de algún archivo (query). En el otro extremo se tiene una búsqueda general de un tema mucho más amplio, como lo son los eventos del año 2001. El algoritmo que proponen los autores es uno que destaca en este último extremo.

La factorización de matrices con valores no-negativos tiene varias ventajas que permiten que sea un buen candidato para este proceso. En primer lugar, su implementación requiere menos operaciones que, por ejemplo, el SVD (single value decomposition) o métodos basados en "eigenvectors" (vectores propios).

Lo que pude rescatar del texto es que el método propuesto se basa en categorizar documentos según sus temas, sumando valores representativos de dichos temas para generar una matriz. Creo que es un método que suena bastante intuitivo, ya que si le podemos asignar valores concretos a las características del texto es fácil acceder a ellos según una aproximación bastante acertada de lo que el usuario busca.

Agrego también que fue bastante desafiante entender el texto en su totalidad y puede que no esté pensado para gente con poca experiencia, ya que me fue dificil internalizar la información cuando aumentaba la complejidad.
