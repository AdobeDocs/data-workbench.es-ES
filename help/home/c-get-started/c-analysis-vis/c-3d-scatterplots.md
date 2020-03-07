---
description: Un diagrama de puntos 3D grafica los elementos de una dimensión de datos (como Días o Sitio de referencia) en una cuadrícula tridimensional donde los ejes x, y y z representan varias métricas.
solution: Analytics
title: Diagrama de puntos 3D
topic: Data workbench
uuid: 5e23547c-dbb4-490c-94bc-0731deee612e
translation-type: tm+mt
source-git-commit: 2e4991206394ca0c463210990ea44dfb700341a5

---


# Diagrama de puntos 3D{#d-scatter-plots}

Un diagrama de puntos 3D grafica los elementos de una dimensión de datos (como Días o Sitio de referencia) en una cuadrícula tridimensional donde los ejes x, y y z representan varias métricas.

Al igual que el [diagrama de puntos 2D](https://docs.adobe.com/content/help/en/data-workbench/using/client/t-open-ins.html#Scatter_Plots), esta visualización resulta útil cuando se trata de comprender la relación entre grandes cantidades de elementos dispares que emplean distintas métricas.

**Para utilizar la visualización de diagrama de puntos 3D:**

1. Abra un nuevo espacio de trabajo.

   Después de abrir un nuevo espacio de trabajo, es posible que tenga que hacer clic en **Agregar** > **Desbloquear** temporalmente.
1. Haga clic con el botón derecho y seleccione **Visualización** > Diagrama de puntos **3D**.

   Se **[!UICONTROL Dimensions]** abrirá una lista de menús.

1. Seleccione una dimensión para la consulta.

   El diagrama de puntos 3D abrirá las métricas predeterminadas para esa dimensión.

   ![](assets/3D_main.png)

   Al seleccionar el **[!UICONTROL Days]** menú, se muestra el siguiente diagrama de puntos 3D con estas métricas predeterminadas en los siguientes ejes: **[!UICONTROL x=Visits]**, **[!UICONTROL y=Retention]**, y **[!UICONTROL z=Visits]**.

1. Cambiar métricas. Haga clic con el botón derecho en la etiqueta de métrica en el eje x, y o z y seleccione **[!UICONTROL Change Metric]**. A continuación, seleccione una métrica diferente para el eje seleccionado.

   ![](assets/3D_change.png)

   >[!IMPORTANT]
   >
   >
   >    
   >    
   >    * Arrastre una métrica a una de las tres etiquetas de eje y colóquela para cambiar el eje seleccionado a la métrica colocada.
   >    * Arrastre una métrica en cualquier otro lugar de la visualización y colóquela para cambiar la métrica de radio de ese eje.
   >    * Arrastre una dimensión a cualquier lugar de la visualización y colóquela para cambiar la dimensión de la visualización.


1. Cambie la métrica Radio. Haga clic con el botón derecho en el título en la parte superior de la página (con el título después de la dimensión seleccionada) y seleccione **[!UICONTROL Change Radius Metric]**.

   La métrica de radio define el tamaño del punto trazado en función de la selección de métricas. La posición relativa de los puntos no cambia en el diagrama de puntos, pero los tamaños de puntos trazados dentro de la visualización aumentan en función del valor de la métrica.

   ![](assets/3D_change_radius.png)

1. Emplee el **[!UICONTROL Orthographic Camera]**. Esta opción le permite identificar los puntos trazados en relación con su verdadera perspectiva según la métrica de radio para evitar la distorsión tridimensional.

   Cuando aparece por primera vez el diagrama de puntos 3D, se muestra en una proyección de rotación tridimensional, que provoca alguna distorsión en los puntos trazados más cerca de la perspectiva, o en la &quot;cámara&quot; virtual. (Los gráficos más cercanos a la cámara se muestran mucho más grandes que los puntos que rotan más lejos de la cámara).

   Para evitar esta distorsión de perspectiva, puede seleccionar la **[!UICONTROL Orthographic Camera]** opción haciendo clic con el botón derecho en el título y seleccionando la opción en el menú. Esto le permite representar los objetos tridimensionales en dos dimensiones. Esto representa los puntos trazados como planos y muestra los puntos como relativos a la métrica de radio, disminuyendo así los desplazamientos tridimensionales.

1. Seleccione puntos en el diagrama de puntos.

   * **Para eliminar un punto o grupo de puntos**: Haga clic en el punto.
   * **Para agregar otro punto o grupo de puntos a la selección**: **Ctrl** + **clic** en un punto o **Ctrl** + **arrastrar** en varios puntos.

   * **Para eliminar un punto o grupo de puntos de la selección**: **Mayús** + **clic** en un punto o **Mayús** **+** arrastre **** por varios puntos.

<!-- <a id="section_9C30F9799F1440F09278327002E6B47A"></a> -->

