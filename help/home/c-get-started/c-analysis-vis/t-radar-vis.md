---
description: Los gráficos de radar proporcionan un enfoque rápido en las áreas que más necesitan atención, al proporcionar una vista visual de un conjunto de métricas y de cómo se relacionan o difieren.
solution: Analytics
title: Visualización de radar
topic: Data workbench
uuid: 39d67743-b6c1-46f1-99fd-7c71dfe07932
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Visualización de radar{#radar-visualization}

Los gráficos de radar proporcionan un enfoque rápido en las áreas que más necesitan atención, al proporcionar una vista visual de un conjunto de métricas y de cómo se relacionan o difieren.

Muchas veces necesita más de una métrica para comprender y evaluar las observaciones seleccionadas en un espacio de trabajo.

Esta visualización resulta útil para comparaciones o puntos de referencia entre las selecciones de tabla. Por ejemplo, puede agregar una tabla de área de trabajo que enumere los almacenes y luego agregar una visualización de radar con métricas como Ingresos, Visitantes y Vistas de página. (Como se muestra en la pantalla en el procedimiento siguiente). A medida que realiza selecciones de almacén en la tabla, el espacio del gráfico de radar cambia, identificando debilidades o fortalezas en las métricas del almacén seleccionado.

Cada radio de un gráfico de radar es una métrica y se requiere un mínimo de tres métricas. Los datos de la métrica se representan en relación con una métrica anclada. La métrica anclada y el parámetro Escalar a anclaje para cada métrica determinan la escala de las métricas con respecto a los puntos de referencia.

**Creación de una visualización de radar**

1. Haga clic con el botón secundario en el espacio de trabajo y, a continuación, haga clic en **[!UICONTROL Visualization]** > **[!UICONTROL Radar]**.

   ![](assets/client-rad.png)

1. Para agregar métricas, haga clic con el botón derecho en la visualización y seleccione **[!UICONTROL Add Metric]**.
1. Para anclar una métrica al gráfico, haga clic con el botón derecho en una métrica y elija la siguiente opción:

   **Anclar a esta métrica:** Utiliza esta métrica como la referencia a la que se extraen otras métricas. Puede anclar una métrica a la vez. Cada métrica del gráfico se filtra mediante la selección del espacio de trabajo activo o sin ningún filtro. La relación de referencia entre estos dos valores se representa en el eje entre el centro del gráfico y el nombre de la métrica en el radar. Cero se representa en el centro.

1. Para escalar una métrica con la métrica anclada, haga clic con el botón derecho en la métrica y elija la siguiente opción:

   **Escalar con anclaje:** Cuando está activado, el eje de esta métrica se redimensiona de modo que la relación de referencia de la métrica de anclaje seleccionada se representa en el círculo, con cero en el centro. Si no se selecciona, el círculo representa una relación de referencia de 1. Normalmente, se activa Escalar con anclaje para métricas contables, como Visitantes o Vistas de página, y se desactiva para métricas de proporción, como Conversión, Duración promedio de la sesión o Vistas de página por sesión.

