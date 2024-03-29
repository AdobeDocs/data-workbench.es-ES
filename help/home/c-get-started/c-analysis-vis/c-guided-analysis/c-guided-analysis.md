---
description: Una visualización de análisis guiado proporciona indicaciones para un análisis más profundo en función de las selecciones que realice en un espacio de trabajo.
title: Análisis guiado
uuid: 01ed8207-3a14-45ac-8a1d-4e17ac39bb94
exl-id: c19b52b6-52db-455e-adde-8b2400aae006
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '233'
ht-degree: 1%

---

# Análisis guiado{#guided-analysis}

{{eol}}

Una visualización de análisis guiado proporciona indicaciones para un análisis más profundo en función de las selecciones que realice en un espacio de trabajo.

Esta visualización ayuda a identificar qué dimensiones pueden proporcionarle más información, es decir, las que están más correlacionadas con sus selecciones. La visualización de análisis guiado en la aplicación de Adobe muestra las dimensiones relevantes para el conjunto de datos, como en el siguiente [!DNL Site] visualización de análisis guiado.

![](assets/vis_GuidedAnalysis.png)

>[!NOTE]
>
>Si el nombre de una dimensión aparece en rojo, no se define en el conjunto de datos.

Cuando realiza una selección dentro de un espacio de trabajo, la visualización de análisis guiado muestra marcas de verificación a la izquierda y puntos a la derecha de las dimensiones para mostrar cuáles proporcionan la información más relevante:

* **Marcas de verificación** identifique las dimensiones cuyos valores difieren de la referencia de forma estadísticamente significativa (es decir, la diferencia entre la selección y la referencia no se debe a una probabilidad aleatoria).
* **Puntos** indicar el grado en que la selección difiere de la referencia. El primer punto representa la estadística U y el segundo representa la estadística V. Consulte [Comprensión de las medidas estadísticas](../../../../home/c-get-started/c-analysis-vis/c-guided-analysis/c-stat-measures.md#concept-ba2c7f417f384dc0a3438fcb6e268708). Cuanto más brillantes y grandes sean los puntos, la buena diferencia y cuanto más relevante sea la información para la dimensión en función de su selección (es decir, los puntos más brillantes y grandes representan información más útil).
