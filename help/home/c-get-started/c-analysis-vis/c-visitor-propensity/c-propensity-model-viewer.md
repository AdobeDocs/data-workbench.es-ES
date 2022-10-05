---
description: Un visor de modelos permite generar un modelo de regresión logística mediante la función Puntuación de tendencia.
title: Visualizador de modelos
uuid: 7ee8ff29-21c2-4721-804a-c7a5d101b50b
exl-id: e0e4acd4-76a2-436a-993b-2bb7ca91ae1a
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '134'
ht-degree: 3%

---

# Visualizador de modelos{#model-viewer}

{{eol}}

Un visor de modelos permite generar un modelo de regresión logística mediante la función Puntuación de tendencia.

El visor de modelos muestra las ponderaciones de coeficiente de cada variable de entrada (incluido el término constante) y su intervalo de errores estadístico. Las variables de entrada que muestran un coeficiente absoluto alto y un margen de error pequeño son los predictores más significativos del modelo.

**Apertura de un gráfico de visualizador de modelo**

1. Seleccione [!DNL Add Visualization > Predictive Analytics > Scoring] .
1. Pase el ratón sobre la finalización del modelo de una puntuación guardada.

![](assets/propensity_model_viewer.png)

Las variables de entrada con un coeficiente >= 1 son influencias positivas en el modelo de propensión. Los coeficientes que son &lt; 1 son influencias negativas en el modelo de propensión. El intervalo definido entre paréntesis es el error e indica la coherencia de la variable de entrada en la población correcta.
