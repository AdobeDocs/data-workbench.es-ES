---
description: Después de agregar el nuevo campo a Log Processing.cfg y crear la nueva transformación Split y dimensión extendida, puede ver la nueva dimensión ampliada que ha creado en cuanto ha finalizado la fase de Entrada rápida del reprocesamiento de datos.
solution: Analytics
title: Visualización de los resultados del experimento
uuid: c0468cad-fb8d-4ecf-8912-bf80b44b0a65
exl-id: cada693c-79cb-4f49-a2f0-6ff60425be1c
source-git-commit: 31f775478b0f0d968310ed10a43ad46791319ee9
workflow-type: tm+mt
source-wordcount: '241'
ht-degree: 4%

---

# Visualización de los resultados del experimento{#viewing-the-experiment-results}

Después de agregar el nuevo campo a Log Processing.cfg y crear la nueva transformación Split y dimensión extendida, puede ver la nueva dimensión ampliada que ha creado en cuanto ha finalizado la fase de Entrada rápida del reprocesamiento de datos.

Esta dimensión, de forma predeterminada, muestra el número de sesiones para cada uno de los grupos de experimentos.

**Para ver la dimensión del experimento**

* Dentro de cualquier espacio de trabajo en [!DNL Insight], abra una tabla con la dimensión de experimento que ha creado.

   Los elementos de dimensión del experimento, que representan cada experimento que está ejecutando y cada grupo dentro de cada experimento, se muestran con el número actual de sesiones para cada grupo. Cada grupo recibe un nombre en el siguiente formato con el nombre del experimento seguido del nombre del grupo:

   *Nombre del experimento.Nombre del grupo*

   Por ejemplo: [!DNL New Homepage.Control]

La tabla siguiente muestra la dimensión Grupos de experimentos controlados que se creó en [!DNL Transformation.cfg] y cada uno de los experimentos y sus grupos.

El experimento Nueva página principal se muestra en la parte inferior de la tabla con sus dos grupos: Control e índice2.

![](assets/controlledexpgrps.png)

Ahora puede utilizar la dimensión del experimento y cualquier métrica relevante para explorar e interpretar los resultados del experimento, así como crear informes útiles que detallen esos resultados.
