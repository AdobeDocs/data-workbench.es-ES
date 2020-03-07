---
description: Una visualización de análisis guiado proporciona indicaciones para un análisis más profundo en función de las selecciones que se realicen en un espacio de trabajo.
solution: Analytics
title: Análisis guiado
topic: Data workbench
uuid: 01ed8207-3a14-45ac-8a1d-4e17ac39bb94
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Análisis guiado{#guided-analysis}

Una visualización de análisis guiado proporciona indicaciones para un análisis más profundo en función de las selecciones que se realicen en un espacio de trabajo.

Esta visualización ayuda a identificar qué dimensiones pueden proporcionarle más información, es decir, aquellas que están más estrechamente relacionadas con sus selecciones. La visualización de análisis guiado en la aplicación de Adobe muestra las dimensiones relevantes para el conjunto de datos, como en la visualización de análisis guiado siguiente [!DNL Site] .

![](assets/vis_GuidedAnalysis.png)

>[!NOTE]
>
>Si el nombre de una dimensión aparece en rojo, no se define en el conjunto de datos.

Cuando realiza una selección dentro de un espacio de trabajo, la visualización de análisis guiado muestra las marcas de verificación a la izquierda y los puntos a la derecha de las dimensiones para mostrar cuáles proporcionan la información más relevante:

* **Las marcas** de verificación identifican las dimensiones cuyos valores difieren de la referencia de una manera estadísticamente significativa (es decir, la diferencia entre la selección y la referencia no se debe a una casualidad aleatoria).
* **Los puntos** indican el grado en que la selección difiere de la referencia. El primer punto representa la estadística U y el segundo punto representa la estadística V. Consulte [Explicación de las medidas](../../../../home/c-get-started/c-analysis-vis/c-guided-analysis/c-stat-measures.md#concept-ba2c7f417f384dc0a3438fcb6e268708)estadísticas. Cuanto más brillantes y grandes sean los puntos, más buena será la diferencia y más relevante será la información para la dimensión basada en la selección (es decir, los puntos más brillantes y grandes representan información más útil).

