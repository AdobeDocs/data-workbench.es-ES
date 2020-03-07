---
description: Un visor de modelos permite generar un modelo de regresión logística mediante la función Puntuación de tendencia.
solution: Analytics
title: Visor de modelos
topic: Data workbench
uuid: 7ee8ff29-21c2-4721-804a-c7a5d101b50b
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Model Viewer{#model-viewer}

Un visor de modelos permite generar un modelo de regresión logística mediante la función Puntuación de tendencia.

El visor de modelos muestra los coeficientes de ponderación de cada variable de entrada (incluido el término constante) y su rango de errores estadísticos. Las variables de entrada que muestran un coeficiente absoluto alto y un margen de error pequeño son los predictores más significativos del modelo.

**Apertura de un gráfico de visor de modelos**

1. Select [!DNL Add Visualization > Predictive Analytics > Scoring] .
1. Pase el ratón sobre el modelo completado de una puntuación guardada.

![](assets/propensity_model_viewer.png)

Las variables de entrada con un coeficiente >= 1 son influencias positivas en el modelo de propensión. Los coeficientes que son &lt; 1 son influencias negativas en el modelo de propensión. El intervalo definido entre paréntesis es el error e indica la coherencia de la variable de entrada en la población correcta.
