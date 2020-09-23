---
description: Después de agregar el nuevo campo a Log Processing.cfg y crear la nueva transformación Dividir y la dimensión ampliada, puede realizar la vista de la nueva dimensión ampliada que ha creado en cuanto termine la etapa de Introducción rápida del reprocesamiento de datos.
solution: Analytics,Analytics
title: Visualización de los resultados del experimento
topic: Data workbench
uuid: c0468cad-fb8d-4ecf-8912-bf80b44b0a65
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '241'
ht-degree: 4%

---


# Visualización de los resultados del experimento{#viewing-the-experiment-results}

Después de agregar el nuevo campo a Log Processing.cfg y crear la nueva transformación Dividir y la dimensión ampliada, puede realizar la vista de la nueva dimensión ampliada que ha creado en cuanto termine la etapa de Introducción rápida del reprocesamiento de datos.

De forma predeterminada, esta dimensión muestra el número de sesiones para cada uno de los grupos de experimentos.

**Vista de la dimensión del experimento**

* En cualquier espacio de trabajo de [!DNL Insight], abra una tabla con la dimensión de experimento que ha creado.

   Los elementos de dimensión del experimento, que representan cada experimento que está ejecutando y cada grupo dentro de cada experimento, se muestran con el número actual de sesiones para cada grupo. Cada grupo recibe el siguiente formato con el nombre del experimento seguido del nombre del grupo:

   *Nombre del experimento.Nombre del grupo*

   Por ejemplo: [!DNL New Homepage.Control]

La siguiente tabla muestra la dimensión Grupos de experimentos controlados que se creó en [!DNL Transformation.cfg] y cada uno de los experimentos y sus grupos.

El experimento Nueva página principal se muestra en la parte inferior de la tabla con sus dos grupos: Control e índice2.

![](assets/controlledexpgrps.png)

Ahora puede utilizar la dimensión del experimento y cualquier métrica relevante para explorar e interpretar los resultados del experimento, así como crear informes útiles que detallen dichos resultados.
