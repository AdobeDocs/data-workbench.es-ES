---
description: Los gráficos de puntos representan los elementos de una dimensión de datos (como Página o Ciudad) en una cuadrícula en la que los ejes X e Y representan métricas diferentes.
solution: Analytics
title: Diagrama de puntos 2D
topic: Data workbench
uuid: 73c23d22-3c3a-4535-b66b-0e3508bd904c
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Diagrama de puntos 2D{#d-scatter-plots}

Los gráficos de puntos representan los elementos de una dimensión de datos (como Página o Ciudad) en una cuadrícula en la que los ejes X e Y representan métricas diferentes.

Las gráficas de puntos pueden ser útiles cuando se trata de comprender la relación entre grandes cantidades de elementos dispares mediante dos métricas diferentes. En el siguiente ejemplo, el diagrama de puntos muestra cada ciudad según el número de visitantes y la tasa de retención correspondiente.

![](assets/vis_ScatterPlot_City.png)

El diagrama de puntos permite ver rápidamente los valores periféricos. Salt Lake City, por ejemplo, tiene una tasa de retención por visitante superior a la promedio.

También se pueden utilizar gráficos de puntos para mostrar la coherencia de los datos. En el siguiente ejemplo, el diagrama de puntos muestra el número de visitantes con sesiones de una duración determinada.

![](assets/vis_ScatterPlot_SessionDuration.png)

El tamaño de cada punto del diagrama de puntos viene determinado por la métrica de radio. La métrica de radio predeterminada difiere para cada aplicación de Adobe. Por ejemplo: en [!DNL Site], la métrica de radio se basa de forma predeterminada en Sesiones. Puede cambiar la métrica de radio para que los puntos de las tablas de puntos representen cualquier métrica disponible. Para ver los pasos a seguir, consulte [Cambio de las métricas](../../../home/c-get-started/c-analysis-vis/c-scat-plots.md#section-fd80576d583c430cb469daf12e39aa2a) de radio. El color de los puntos se basa en la leyenda del color que está abierta en el espacio de trabajo. Para obtener más información sobre las leyendas de color, consulte Leyendas [de color](../../../home/c-get-started/c-analysis-vis/c-legends/c-color-leg.md#concept-f84d51dc0d6547f981d0642fc2d01358).

## Seleccionar puntos {#section-4b4d45f39b884d54bb7407b3b2f4ea50}

**Seleccionar un solo punto**

* Haga clic en el punto.

**Para agregar otro punto o grupo de puntos a la selección**

* Ctrl+clic en un punto o Ctrl+arrastrar en varios puntos.

**Quitar un punto o grupo de puntos de la selección**

* Mayús + clic en un punto o Mayús + arrastrar en varios puntos.

## Cambio de dimensiones {#section-796cd962ef3f476caa89d99083782ed1}

* Haga clic con el botón secundario en la etiqueta de la dimensión en la parte superior del gráfico y haga clic en **[!UICONTROL Change Dimension]** > *&lt;**[!UICONTROL dimension name]**>*.

## Cambio de las métricas {#section-44b8be9215cd4039b1eeb98ae1b31445}

**Cambiar la métrica mostrada en el eje x o y de un diagrama de puntos**

* Haga clic con el botón secundario en la etiqueta de la métrica que desee cambiar y haga clic en **[!UICONTROL Change Metric]** > *&lt;**[!UICONTROL metric name]**>*.

## Cambio de las métricas de radio {#section-fd80576d583c430cb469daf12e39aa2a}

**Cambiar la métrica de radio de un diagrama de puntos**

Haga clic con el botón secundario en la etiqueta de la dimensión en la parte superior del gráfico y haga clic en **[!UICONTROL Change Radius Metric]** > *&lt;**[!UICONTROL metric name]**>*.

![](assets/mnu_ScatterPlot_Change.png)

