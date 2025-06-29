# NEURAL_STYLE_TRANSFER
En este repositorio, almaceno un proyecto relacionado a la transferencia de estilo usando redes neuronales convolucionales.

- Código: [¡Click aquí!](./NeuralStyleTransfer_FromScratch.ipynb)

-----
# 1) INTRODUCCIÓN
## ¿QUÉ ES "NEURAL STYLE TRANSFER"?
Es una técnica que usa redes neuronales convolucionales para combinar el contenido de una imagen con el estilo artístico de la otra.

----
## DESCRIPCIÓN DEL PROYECTO
Dada una imagen de contenido y una imagen de estilo, se obtendrá, como resultado final, una imagen resultante que combina el estilo de una con el contenido de la otra.

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
* ### Arquitectura
* ### Función de pérdida
* ### Proceso de optimización:
  Nota: A partir de la época 3000, con un l_r=0.005 el modelo ya no tiene mejoras en el style loss. Por ese motivo, el entrenamiento se detiene en dicha iteración para evitar un mal performance.

