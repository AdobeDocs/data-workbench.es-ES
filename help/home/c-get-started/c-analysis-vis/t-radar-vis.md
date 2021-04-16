---
description: Los gráficos de radar proporcionan un enfoque rápido en las áreas que más necesitan atención, ya que proporcionan una vista visual de un conjunto de métricas y cómo se relacionan o difieren entre sí.
title: Visualización de radar
uuid: 39d67743-b6c1-46f1-99fd-7c71dfe07932
exl-id: 5385d903-422b-4936-bbb3-0d5ee4d286de
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '400'
ht-degree: 1%

---

# Visualización de radar{#radar-visualization}

Los gráficos de radar proporcionan un enfoque rápido en las áreas que más necesitan atención, ya que proporcionan una vista visual de un conjunto de métricas y cómo se relacionan o difieren entre sí.

Muchas veces necesita más de una métrica para comprender y evaluar las observaciones seleccionadas en un espacio de trabajo.

Esta visualización es útil para comparaciones o puntos de referencia entre las selecciones de tabla. Por ejemplo, puede agregar una tabla de espacio de trabajo que enumere las tiendas y luego agregar una visualización de radar con métricas como Ingresos, Visitantes y Vistas de página. (Como se muestra en la pantalla en el siguiente procedimiento). A medida que realiza selecciones de tienda en la tabla, la huella del gráfico de radar cambia, identificando debilidades o fortalezas en las métricas del almacén seleccionado.

Cada radio de un gráfico de radar es una métrica y se requieren como mínimo tres métricas. Los datos de la métrica se trazan en relación con una métrica anclada. La métrica anclada y el parámetro Escala a anclar para cada métrica determinan la escala de las métricas con respecto a los puntos de referencia.

**Creación de una visualización de radar**

1. Haga clic con el botón derecho en el espacio de trabajo y, a continuación, haga clic en **[!UICONTROL Visualization]** > **[!UICONTROL Radar]**.

   ![](assets/client-rad.png)

1. Para agregar métricas, haga clic con el botón derecho en la visualización y seleccione **[!UICONTROL Add Metric]**.
1. Para anclar una métrica al gráfico, haga clic con el botón derecho en una métrica y elija la siguiente opción:

   **Anclaje a esta métrica:** utiliza esta métrica como referencia con la que se dibujan otras métricas. Puede anclar una métrica a la vez. Cada métrica del gráfico se filtra mediante la selección activa del espacio de trabajo o sin filtro. La relación de referencia entre estos dos valores se representa en el eje entre el centro del gráfico y el nombre de la métrica en el radar. Cero se traza en el centro.

1. Para escalar una métrica con la métrica anclada, haga clic con el botón derecho en la métrica y elija la siguiente opción:

   **Escala con anclaje:** cuando está activado, el eje de esta métrica se escala para que la relación de referencia de la métrica de anclaje seleccionada se trunque en el círculo, con cero en el centro. Cuando no está seleccionado, el círculo representa una relación de referencia de 1. Normalmente, se activa Escala con delimitador para métricas contables, como Visitantes o Vistas de página, y se desactiva para métricas de proporción, como Conversión, Duración promedio de la sesión o Vistas de página por sesión.
