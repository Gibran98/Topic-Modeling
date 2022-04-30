# Modelo para Topic Modeling
Aquí se incluye el código para nuestra implementación del proyecto para topic modeling. Primeramente se incluyen funciones para recopilar datos de las siguientes fuentes:
* Twitter
* Reddit
* Facebook
* Youtube

Posteriormente, se incluyen funciones para hacer un pre-procesamiento de los datos. Principalmente se quería remover información sensible de estos como nombres propios, ubicaciones, emails y teléfonos. Se implementaron los siguientes dos modelos de topic modeling, por los cuales se pueden pasar los textos procesados:

### BERTopic
Es el modelo principal en el Notebook, se utilizó el paquete que se puede instalar con PyPi. En la siguiente [liga](https://maartengr.github.io/BERTopic/algorithm/algorithm.html) se puede encontrar la documentació del modelo así como el tutorial básico que seguimos para su implementación.

### Latent Dirichlet Allocation (LDA)
**Video de explicación:** https://www.youtube.com/watch?v=B4LpDi9tBUE

Hicimos un video que explica conceptualmente cómo funciona este modelo. Adicionalmente, en el Notebook se explica paso a paso su implementación.

### Evaluación con LDAvis
Finalmente, incluímos una implementación de pyLDAvis para hacer una evaluación de los modelos. Lo hicimos siguiendo el tutorial [aquí](https://towardsdatascience.com/topic-model-visualization-using-pyldavis-fecd7c18fbf6).

## Para correr la aplicación
Aquí se proporcionan todos los archivos relevantes para correr la aplicación. El archivo principal es el Jupyter Notebook, y los demás archivos son necesarios para poder correr correctamente este Notebook. Dentro de este se proporcionan explicaciones del código que se realizó, así como el razonamiento detrás de la lógica que se usó en el desarrollo de este proyecto.

Para correr el Notebook en Google Colab, este se debe cargar al ambiente, y además, los otros archivos (especialmente el requirements.txt) deben subirse al ambiente para que todo funcione adecuadamente.

## Funcionalidades Adicionales
A contuación se describen las 3 funcionalidades adicionales que se implementaron además de lo que se mencionó arriba:

### 1. Comentarios de Youtube
Utilizando la [API de Youtube](https://developers.google.com/youtube/v3/docs/commentThreads/list) pudimos realizar requests para traer los comentarios de un video 
en especifico. Una vez que se tienen los comentarios, podemos procesarlos y usarlos para pasarlos por los modelos.

### 2. Posts de Facebook
Usamos el paquete de **facebook-scraper** para obtener los textos de publicaciones realizadas por un usuario. Para su funcionamiento es necesario contar con el archivo **'facebook.com_cookies.txt'** que se puede obtener utilizando el add-on de Chrome llamado **Get cookies.txt** tras haber iniciado sesión en Facebook. La función en el notebook está esperando este archivo para poder funcionar.

Usamos esta [liga](https://pypi.org/project/facebook-scraper/) para ayudarnos

### 3. Amazon Comprehend
Finalmente, la tercera funcionalidad adicional fue implementar el modelo de Amazon Comprehend para topic modeling. Esto lo hicimos debido a que nos resultó interesante poder comparar los resultados de este con los otros dos modelos.

Esta es la [liga](https://docs.aws.amazon.com/comprehend/latest/dg/topic-modeling.html) a la documentación sobre la cual nos basamos para implementar el modelo.
