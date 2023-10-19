<p align="center">
<img src=doc/inicio.png>
</p>

## En este repositorio se encuentran el trabajo final de la materia Visión por computadora II de la especialización de inteligencia artificial de la FIUBA
**Autor:** Juan Ignacio Ribet

Este trabajo es complemento del proyecto final de la especialización que se puede encontrar en el repositorio [Yoga-Pose-Estimation---CEIA](https://github.com/Juaniribet/Yoga-Pose-Estimation---CEIA.git) 

### Planteo del problema

En el siguiente trabajo se busca clasificar imágenes de diferentes posturas de yoga utilizando
redes neuronales

- Objetivo: estimar posturas por video en tiempo real
- Problema: clasificación multiclase
- Cantidad de clases: 4
- Nombre de las clases: 'downdog', 'goddess', 'tree', 'warrior'
- Total de imágenes del dataset: 1102
- División Train-Test: 80-20%
- Arquitecturas de modelos: ResNet18, ResNet50, VGG19
- Transfer Learning: IMAGENET
- Data Augmentation: Horizontal Flip - Resized Crop - Normalize
- Visualización GradCAM (mejor modelo)

Además se utiliza el framework de MediaPipe para realizar una clasificación obteniendo los puntos
característicos de la postura

### *Clases*
<img src=doc/clases.png>

### *Balance de Clases*

<p align="center">
<img src=doc/balance_clases.png>
</p>

## *Resultados*

La arquitectura VGG19 con el entrenamiento de todos los parametros dio los mejores resultados en el accuracy de la clasificaion de las imagenes con un 95,59%.

<p align="center">
<img src=doc/resultados.png>
</p>

Matriz de confusión del modelo VGG19 en Test Set

<p align="center">
<img src=doc/matriz_confusion.png width='700'>
</p>

## *Visualización Grad-CAM*

<p align="center">
<img src=doc/MaxPool2d-10.png width='450'><img src=doc/architecture_VGG19.png width='392'>
</p>

## *Estimación por video*

Se realizó la estimación con un video de muestra para verificar el funcionamiento del modelo y los resultados no fueron los esperados, muchas posturas mal clasificadas.

<img src=doc/video_pred_gradcam.png width='700'>

-------------------------------------

## *Clasificación con framework MediaPipe*

Creaciónn del dataset obteniendo los puntos claves de cada imagen .

<img src=doc/output.png>

Luego se entrenó un modelo de clasificación simple de regresión logística obteniendo un accuracy del 99.5%.

Al realizar la estimación por video la clasificación de la postura mejoro sustancialmente solo teniendo falsos positivos en las transiciones entre posturas.

<img src=doc/pred_mediapipe.png width='700'>
