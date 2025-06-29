# NEURAL_STYLE_TRANSFER
En este repositorio, almaceno un proyecto relacionado a la transferencia de estilo usando redes neuronales convolucionales.

- Código: [¡Click aquí!](./NeuralStyleTransfer_FromScratch.ipynb)

-----
# 1) INTRODUCCIÓN
## ¿QUÉ ES "NEURAL STYLE TRANSFER"?
Es una técnica que usa redes neuronales convolucionales para combinar el contenido de una imagen con el estilo artístico de la otra.

----
## DESCRIPCIÓN DEL PROYECTO
Dada una imagen de contenido y una imagen de estilo, se obtendrá, como resultado final, una imagen que combina el estilo de una con el contenido de la otra.

Luego de entrenar el modelo, realicé el testeo con las siguientes 2 imágenes de contenido:
- Imagen de Macchu Picchu, Perú
- Imagen de 2 juguetes

Y 2 imágenes de estilo:
- La noche estrellada, Van Gogh
- Cubismo, Pablo Picasso

Sin embargo, se puede usar cualquier otra imagen de contenido y estilo. ¡Igual podrás ver el resultado! 


----

## IMPLEMENTACIÓN


----
# 2) RESULTADOS
A continuación, se mostrarán las imágenes resultantes que obtuve al aplicar la red neuronal de transferencia de estilo:
- **PRUEBA 1**:
    - **Imagen de contenido: Machu Picchu, Perú**
      
    ![MachuPicchu](https://github.com/DianaMLlamocaZ/NEURAL_STYLE_TRANSFER/blob/main/IMAGENES/imagen_contenido_machu_picchu.JPG)

  - **Imagen de estilo: La noche estrellada, Van Gogh**
    
    ![ImagenEstilo](https://github.com/DianaMLlamocaZ/NEURAL_STYLE_TRANSFER/blob/main/IMAGENES/imagen_estilo_2.JPG)

  - **Imagen resultante:**
  - 
    ![ImagenResultante](https://github.com/DianaMLlamocaZ/NEURAL_STYLE_TRANSFER/blob/main/IMAGENES/ResultadoFinal1.JPG)

- **PRUEBA 2**:
  - **Imagen de contenido: Juguetes**
      
    ![Muñecos](https://github.com/DianaMLlamocaZ/NEURAL_STYLE_TRANSFER/blob/main/IMAGENES/imagen_contenido.JPG)

  - **Imagen de estilo: Cubismo**
    
    ![ImagenEstilo](https://github.com/DianaMLlamocaZ/NEURAL_STYLE_TRANSFER/blob/main/IMAGENES/imagen_estilo.JPG)

  - **Imagen resultante:**
    
    ![ImagenResultante](https://github.com/DianaMLlamocaZ/NEURAL_STYLE_TRANSFER/blob/main/IMAGENES/ImagenResultado2.JPG)

----
# 3) CÓMO FUNCIONA
* ### Arquitectura:
  - Se usó el modelo VGG19 para la extracción de características (lo convolucional, no el MLP). Por ese motivo, los pesos del modelo NO tienen por qué cambiar en cada iteración/época.
  - Para extraer el contenido, se usó la capa conv4_2.
  - Para extraer el estilo, se usaron las capas conv_0, conv_5, conv_10, conv_19, conv_28.
    
* ### Función de pérdida
  - Content loss: Usé el mse para calcular la 'diferencia' entre la imagen de contenido y la imagen generada.
  - Style loss: Para calcular la pérdida de estilo, se debe calcular la matriz de Gram para cada imagen: la imagen de estilo y la imagen generada.
      Debido a que son 5 capas convolucionales por las que debe pasar cada una de las imágenes, la pérdida para la imagen generada deberá ser el 'error acumulado' de la imagen generada a través de estas 5 capas que se obtiene de calcular el mse al compararla con la imagen de estilo. 
    
* ### Proceso de optimización:
  Nota: A partir de la época 3000, con un l_r=0.005 el modelo ya no tiene mejoras en el style loss. Por ese motivo, el entrenamiento se detiene en dicha iteración para evitar un mal performance.

