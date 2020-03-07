---
description: La visualización de acordes le permite mostrar tanto la proporción como la correlación entre las métricas, mostrando coros más grandes como una indicación de una correlación más fuerte.
title: Visualización de acordes
uuid: 3f322f58-f8f5-4d91-bdf8-4b5f9d7fb072
translation-type: tm+mt
source-git-commit: cb3ca4b3b993f5f04f6b6cee25850600ff3d8986

---


# Visualización de acordes{#chord-visualization}

La visualización de acordes le permite mostrar tanto la proporción como la correlación entre las métricas, mostrando coros más grandes como una indicación de una correlación más fuerte.

La visualización de acordes le permite identificar correlaciones entre métricas, lo que le permite agregar y evaluar fácilmente posibles correlaciones. También proporciona otra vista en cualquier matriz de [correlación](https://docs.adobe.com/content/help/en/data-workbench/using/client/analysis-visualizations/correlation-analysis/c-correlation-analysis.html)previamente creada. Con la visualización de acordes, no se puede identificar una correlación positiva o negativa entre las métricas, solo que exista una correlación. En algunos casos, la determinación de una relación directa o inversa se puede identificar aplicando métricas de contador.

1. **Abra la **[!UICONTROL Chord]**visualización**.

   En el espacio de trabajo, haga clic con el botón derecho [!DNL Visualization > Predictive Analytics > Chord].

1. **Seleccione una dimensión en el menú**.

   Se abrirá una visualización en blanco que le permitirá seleccionar una dimensión. El nombre de la dimensión aparecerá en la parte superior de la visualización de acordes en blanco.

   >[!NOTE]
   >
   >Si ya tiene abierta una matriz de correlación en el espacio de trabajo, también puede procesarla como una visualización de acordes.

1. **Elija métricas para correlacionar**.

   Arrastre las métricas desde el **[!UICONTROL Finder]** gráfico haciendo clic en **[!UICONTROL Ctrl-Alt]** para arrastrar las métricas de la tabla al gráfico. Después de seleccionar dos o más métricas, el gráfico se actualizará automáticamente y comenzará a mostrar los datos de correlación. Continúe agregando métricas según sea necesario para correlacionar puntos de datos.

   ![](assets/chord_drag_metric.png)

   La visualización de acordes muestra la proporción del total representado por el área de cada segmento. Continúe agregando métricas según sea necesario para identificar e investigar las relaciones significativas.

   ![](assets/chord_selected.png)

1. **Vea la visualización** de acordes.

   Pase el ratón sobre cada métrica en la visualización para ver las relaciones. En el ejemplo, puede ver una correlación entre Unidades y la mayoría de las demás métricas (excepto la métrica Duración **de la** visita).

   ![](assets/chord_visualization_1.png)

   Al pasar el ratón por encima de la métrica Duración **de la** visita en la visualización de acordes, verá que existe una correlación muy escasa o, como máximo, débil entre todas las demás métricas.

   ![](assets/chord_visualization_2.png)

1. **Cambiar configuración.** Haga clic con el botón derecho en la visualización de acordes para abrir un menú para cambiar la dimensión, mostrar las dimensiones como números absolutos o como porcentajes, eliminar la métrica seleccionada o todas las métricas, editar colores y detalles y exportar valores a una matriz de correlación.

   ![](assets/chord_menu.png)

