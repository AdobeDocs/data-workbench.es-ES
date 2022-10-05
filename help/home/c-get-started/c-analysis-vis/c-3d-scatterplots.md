---
description: Un diagrama de puntos 3D representa los elementos de una dimensión de datos (como Días o Sitio de referencia) en una cuadrícula tridimensional donde los ejes x, y y z representan varias métricas.
title: Diagrama de puntos 3D
uuid: 5e23547c-dbb4-490c-94bc-0731deee612e
exl-id: 18f18cab-a31b-4ffe-89c5-412a5645af2e
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '500'
ht-degree: 1%

---

# Diagrama de puntos 3D{#d-scatter-plots}

{{eol}}

Un diagrama de puntos 3D representa los elementos de una dimensión de datos (como Días o Sitio de referencia) en una cuadrícula tridimensional donde los ejes x, y y z representan varias métricas.

Como el [Diagrama de puntos 2D](https://experienceleague.adobe.com/docs/data-workbench/using/client/t-open-ins.html#Scatter_Plots), esta visualización es útil cuando se intenta comprender la relación entre un gran número de elementos dispares que emplean distintas métricas.

**Para utilizar la visualización del diagrama de puntos 3D:**

1. Abra un nuevo espacio de trabajo.

   Después de abrir un nuevo espacio de trabajo, es posible que tenga que hacer clic en **Agregar** > **Desbloquear temporalmente**.
1. Haga clic con el botón derecho y seleccione **Visualización** > **Diagrama de puntos 3D**.

   Lista de menús **[!UICONTROL Dimensions]** se abrirá.

1. Seleccione una dimensión para la consulta.

   El diagrama de puntos 3D abrirá las métricas predeterminadas para esa dimensión.

   ![](assets/3D_main.png)

   Al seleccionar la variable **[!UICONTROL Days]** muestra el siguiente diagrama de puntos 3D con estas métricas predeterminadas en los siguientes ejes: **[!UICONTROL x=Visits]**, **[!UICONTROL y=Retention]** y **[!UICONTROL z=Visits]**.

1. Cambiar métricas. Haga clic con el botón derecho en la etiqueta de métrica en los ejes x, y o z y seleccione **[!UICONTROL Change Metric]**. A continuación, seleccione una métrica diferente para el eje seleccionado.

   ![](assets/3D_change.png)

   >[!IMPORTANT]
   >
   >
   >    
   >    
   >    * Arrastre una métrica a una de las tres etiquetas de eje y suéltela para cambiar el eje seleccionado a la métrica perdida.
   >    * Arrastre una métrica a cualquier otro lugar de la visualización y suéltela para cambiar la métrica de radio de ese eje.
   >    * Arrastre una dimensión a cualquier lugar de la visualización y suéltela para cambiar la dimensión de la visualización.


1. Cambie la métrica Radio . Haga clic con el botón derecho en el título en la parte superior de la página (con título después de la dimensión seleccionada) y seleccione **[!UICONTROL Change Radius Metric]**.

   La métrica radio define el tamaño del punto trazado en función de la selección de la métrica. La posición relativa de los puntos no cambia en el diagrama de puntos, pero los tamaños de puntos trazados dentro de la visualización aumentan en función del valor de la métrica.

   ![](assets/3D_change_radius.png)

1. Emplee el **[!UICONTROL Orthographic Camera]**. Esta opción le permite identificar los puntos trazados en relación con su verdadera perspectiva basada en la métrica de radio para evitar la distorsión tridimensional.

   Cuando aparece por primera vez el diagrama de puntos 3D, se muestra en una proyección giratoria tridimensional, lo que provoca alguna distorsión en los puntos trazados más cerca de la perspectiva, o &quot;cámara&quot; virtual. (Los gráficos más cercanos a la cámara son mucho más grandes que los puntos que rotan más lejos de la cámara).

   Para evitar esta distorsión de perspectiva, puede seleccionar la opción **[!UICONTROL Orthographic Camera]** al hacer clic con el botón derecho en el título y seleccionar en el menú. Esto le permite representar los objetos tridimensionales en dos dimensiones. De este modo, los puntos trazados se representan como planos y muestran los puntos como relativos a la métrica de radio, lo que reduce los desplazamientos tridimensionales.

1. Seleccione puntos del diagrama de puntos.

   * **Eliminación de un punto o grupo de puntos**: Haga clic en el punto .
   * **Para añadir otro punto o grupo de puntos a la selección**: **Ctrl** + **click** un punto o **Ctrl** + **arrastrar** en varios puntos.

   * **Eliminación de un punto o grupo de puntos de la selección**: **Mayús** + **click** un punto o **Mayús** **+** **arrastrar** en varios puntos.

<!-- <a id="section_9C30F9799F1440F09278327002E6B47A"></a> -->
