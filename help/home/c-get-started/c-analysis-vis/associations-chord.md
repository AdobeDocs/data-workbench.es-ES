---
description: La visualización del acorde de asociación permite mostrar tanto la proporción como la asociación entre métricas, dimensiones y elementos, mostrando coros más grandes como una indicación de una asociación más fuerte.
title: Visualización de Association Chord
uuid: c656ffc8-e45a-44c0-a29b-cdc10dcbd1f2
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Visualización de Association Chord{#association-chord-visualization}

La visualización del acorde de asociación permite mostrar tanto la proporción como la asociación entre métricas, dimensiones y elementos, mostrando coros más grandes como una indicación de una asociación más fuerte.

La tabla Asociaciones compara valores con el cálculo de V de Cramer en lugar de usar el coeficiente de correlación de Pearson como se emplea en las visualizaciones de la matriz [de](/help/home/c-get-started/c-analysis-vis/c-correlation-analysis/c-correlation-analysis.md) correlación y del acorde de [correlación](/help/home/c-get-started/c-analysis-vis/associations-visualization.md) (solo pueden comparar métricas, mientras que la tabla de asociación y el acorde pueden comparar métricas, dimensiones y elementos). El acorde de asociaciones también proporciona otra vista en una tabla de [asociaciones](../../../home/c-get-started/c-analysis-vis/associations-visualization.md#concept-9d937dda38174875b32095c6eaf22f2f)creada anteriormente.

**Para crear un acorde de asociación**

1. En un espacio de trabajo, haga clic con el botón secundario en **Visualización > Análisis predictivos > Acorde de asociación**.

   Se abrirá un menú que permite seleccionar una dimensión extendida de la lista.

   ![](assets/association_chord1.png)

   Una vez seleccionada, la tabla de asociación en blanco se abrirá con la dimensión seleccionada identificada en el título. ![](assets/association_chord2.png)

1. **Seleccione una métrica, dimensión o elemento** de dimensión.

   Haga clic con el botón derecho en la visualización de acordes y seleccione **Agregar métrica** o **Agregar dimensión**. Seleccione los elementos del menú que desee agregar al acorde.

   También puede arrastrar métricas y dimensiones desde el **[!UICONTROL Finder]** gráfico haciendo clic **[!UICONTROL Ctrl-Alt]** y arrastrando métricas y dimensiones al mismo. O bien, arrastre los elementos de dimensión directamente desde una tabla abierta a la visualización de acordes.

1. **Elija métricas, dimensiones y elementos adicionales para asociar**.

   Después de seleccionar dos o más valores, el gráfico se actualizará automáticamente y comenzará a mostrar los datos de asociación. Continúe agregando métricas según sea necesario para asociar puntos de datos.

   ![](assets/association_chord.png)

   La visualización de acordes muestra la proporción del total representado por el área de cada segmento. Continúe agregando métricas, dimensiones o elementos según sea necesario para identificar e investigar las relaciones significativas.

1. **Vea la visualización** de acordes.

   Pase el ratón sobre cada valor de la visualización para ver las relaciones.

1. **Cambiar configuración.** Haga clic con el botón derecho en la visualización de acordes para abrir un menú para cambiar la métrica, dimensión o elementos y mostrar las dimensiones como números absolutos o como porcentajes, eliminar la métrica seleccionada o todas las métricas, editar colores y detalles y exportar valores a una tabla de asociaciones.

**Para crear un acorde de asociación a partir de una tabla de asociación:**

1. Abra una visualización **de tabla** de asociación.
1. Haga clic con el botón derecho y seleccione **Exportar visualización** de acordes. Se abrirá un diagrama de acordes de asociación con los valores seleccionados en la tabla de asociación. ![](assets/association_table_to_chord.png)

>[!IMPORTANT]
>
>Si se exporta una tabla de asociación desde un diagrama de acordes de asociación que contenga al menos una métrica, se duplicarán los elementos en las filas y columnas de la tabla de asociación. Para evitar la duplicación de elementos, cree una nueva tabla de asociación y agregue los elementos deseados en lugar de exportar los elementos desde un diagrama de acordes de asociación.

