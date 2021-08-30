---
description: Las líneas de tendencias le permiten superponer gráficos para comparar e interpretar los datos.
title: Líneas de tendencia
uuid: b1d81973-2181-4507-a0a5-adf5eeb9f926
exl-id: 3e7e9218-49b2-4877-a4bd-318b838089e8
source-git-commit: 232117a8cacaecf8e5d7fcaccc5290d6297947e5
workflow-type: tm+mt
source-wordcount: '206'
ht-degree: 1%

---

# Líneas de tendencia{#trend-lines}

Las líneas de tendencias le permiten superponer gráficos para comparar e interpretar los datos.

Al igual que la visualización [Diagrama de puntos](https://experienceleague.adobe.com/docs/data-workbench/using/client/analysis-visualizations/c-scat-plots.html), ahora puede establecer líneas de tendencia en una visualización de gráfico para mostrar la tasa de cambio en función de líneas lineales, exponenciales, de potencia o polinómicas. La función Línea de tendencia permite superponer líneas de tendencia en un gráfico, normalmente a lo largo de una dimensión de tiempo.

Por ejemplo, en esta comparación de gráficos, podemos ver que las visitas están aumentando, pero los pedidos están descendiendo.

![](assets/trend_line.png)

Para agregar una línea de tendencia

1. Abra un gráfico y haga clic con el botón derecho en el nombre de la métrica en la esquina superior izquierda.
1. Haga clic en **[!UICONTROL Trend Lines]** y seleccione entre las opciones.

   ![](assets/trend_line_graph.png)

   Puede seleccionar la línea de tendencia para que aparezca sobre el gráfico como **Lineal simple**, **Exponencial**, **Potencia** o **Polinomial**. La polinomial creará una línea de tendencia de regresión polinómica. Lineal simple creará una línea de tendencia como la tasa de cambio a lo largo de la línea de regresión. Exponencial calcula una línea de tendencia como y = b*exp( a*x ) y Potencia como y = b*x`<sup>a</sup>`.

   La tendencia se calculará y procesará en el gráfico, y se abrirá una llamada que mostrará información detallada de la ecuación de tendencia.

   ![](assets/trend_line_detail.png)
