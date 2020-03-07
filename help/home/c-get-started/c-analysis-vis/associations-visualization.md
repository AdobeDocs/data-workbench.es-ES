---
description: La visualización Tabla de asociación permite asociar métricas con métricas, dimensiones y elementos de dimensión mediante el algoritmo V de Cramer.
title: Visualización de tabla de asociación
uuid: 4563c336-3377-4929-8694-8c0d00866825
translation-type: tm+mt
source-git-commit: cb3ca4b3b993f5f04f6b6cee25850600ff3d8986

---


# Visualización de tabla de asociación{#association-table-visualization}

La visualización Tabla de asociación permite asociar métricas con métricas, dimensiones y elementos de dimensión mediante el algoritmo V de Cramer.

La tabla de asociación compara valores con el cálculo V de Cramer en lugar de usar el coeficiente de correlación de Pearson como se usa en las visualizaciones de la matriz [de](https://docs.adobe.com/content/help/en/data-workbench/using/client/analysis-visualizations/correlation-analysis/c-correlation-analysis.html) correlación y del acorde de [correlación](https://docs.adobe.com/content/help/en/data-workbench/using/client/analysis-visualizations/c-chord-visualization.html) (solo pueden comparar métricas, mientras que la tabla de asociación y el acorde de [asociación](../../../home/c-get-started/c-analysis-vis/associations-chord.md#concept-51d0bda998474dd5946cc2a9b8393445) pueden comparar métricas, dimensiones y elementos).

## Crear una tabla de asociación {#section-87ed12ccc1af4196a1b6534e621c4cbb}

La tabla de asociación compara las métricas con respecto a una dimensión contable o no contable. La tabla se puede modificar para resaltar asociaciones dentro de la visualización mediante selección de color o para representarla como mapa de texto, mapa de calor o ambos.

1. Abra una tabla de asociación.

   Haga clic con el botón secundario [!DNL Visualization] > [!DNL Predictive Analytics] > [!DNL Association Table].

   ![](assets/association_table.png)

1. Seleccione una dimensión ampliada: una dimensión de pulsaciones, visitas individuales, productos, visitas o visitantes. Se abrirá una tabla de asociación con la dimensión ampliada identificada en la esquina y su métrica asociada colocada tanto en la fila como en la columna.

   ![](assets/association_table1.png)

   La tabla Asociaciones utiliza la V de Cramer como una correlación simétrica, lo que resulta en métricas, dimensiones y valores de elementos seleccionados reflejados en las columnas y filas de una tabla de asociación. Por ejemplo, al seleccionar la dimensión ampliada **Producto** , se utiliza la **[!UICONTROL Visits]** métrica como métrica asociada tanto en la fila como en la columna de la tabla, lo que resulta en una comparación perfecta pero inútil (1,00) porque los valores comparados son idénticos.

1. Agregue más valores a la tabla de asociación.

   Haga clic con el botón derecho en una columna o fila y seleccione **Agregar métrica** o **Agregar dimensión**. También puede arrastrar métricas y dimensiones desde un panel **Finder** . Los elementos de dimensión también se pueden arrastrar y soltar de una tabla abierta a la visualización de la tabla.

   ![](assets/association_table2.png)

   >[!NOTE]
   >
   >Hay un límite de diez filas y columnas permitidas en la tabla de asociación.

