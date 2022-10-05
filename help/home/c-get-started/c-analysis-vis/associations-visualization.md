---
description: La visualización Tabla de asociación permite asociar métricas con métricas, dimensiones y elementos de dimensión mediante el algoritmo V de Cramer.
title: Visualización de tabla de asociación
uuid: 4563c336-3377-4929-8694-8c0d00866825
exl-id: 3fc2c025-d369-45ed-8c9e-eb4a0ac412b7
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '309'
ht-degree: 1%

---

# Visualización de tabla de asociación{#association-table-visualization}

{{eol}}

La visualización Tabla de asociación permite asociar métricas con métricas, dimensiones y elementos de dimensión mediante el algoritmo V de Cramer.

La tabla de asociación compara valores con el cálculo de V de Cramer en lugar de usar el coeficiente de correlación de Pearson como se usa en la variable [Matriz de correlación](https://experienceleague.adobe.com/docs/data-workbench/using/client/analysis-visualizations/correlation-analysis/c-correlation-analysis.html) y [Correlación](https://experienceleague.adobe.com/docs/data-workbench/using/client/analysis-visualizations/c-chord-visualization.html) visualizaciones (solo pueden comparar métricas, mientras que la Tabla de asociación y [Consejo de asociación](../../../home/c-get-started/c-analysis-vis/associations-chord.md#concept-51d0bda998474dd5946cc2a9b8393445) puede comparar métricas, dimensiones y elementos).

## Crear una tabla de asociación {#section-87ed12ccc1af4196a1b6534e621c4cbb}

La tabla de asociación compara las métricas con respecto a una dimensión contable o no contable. La tabla se puede modificar para resaltar asociaciones dentro de la visualización mediante la selección de colores o para representarla como un mapa de texto, un mapa de calor o ambas opciones.

1. Abra una tabla de asociación.

   Clic con el botón derecho [!DNL Visualization] > [!DNL Predictive Analytics] > [!DNL Association Table].

   ![](assets/association_table.png)

1. Seleccione una dimensión extendida: una dimensión de clics, visitas individuales, productos, visitas o visitantes. Se abrirá una tabla de asociación con la dimensión ampliada identificada en la esquina y su métrica asociada colocada en la fila y la columna.

   ![](assets/association_table1.png)

   La tabla Asociaciones utiliza la V de Cramer como correlación simétrica, lo que da como resultado valores de métricas, dimensiones y elementos seleccionados que se reflejan en las columnas y filas de una tabla de asociación. Por ejemplo, si selecciona la variable **Product** la dimensión extendida utiliza la variable **[!UICONTROL Visits]** como métrica asociada tanto en la fila como en la columna de la tabla, lo que resulta en una comparación perfecta pero sin utilidad (1,00) porque los valores comparados son idénticos.

1. Agregue más valores a la tabla de asociación.

   Haga clic con el botón derecho en una columna o fila y seleccione **Agregar métrica** o **Agregar Dimension**. También puede arrastrar métricas y dimensiones desde un **Buscador** panel. Los elementos Dimension también se pueden arrastrar y soltar de una tabla abierta a la visualización de tabla.

   ![](assets/association_table2.png)

   >[!NOTE]
   >
   >Hay un límite de diez filas y columnas permitidas en la tabla de asociación.
