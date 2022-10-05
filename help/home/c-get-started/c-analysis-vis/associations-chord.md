---
description: La visualización del acorde de asociación le permite mostrar la proporción y la asociación entre métricas, dimensiones y elementos, mostrando coros más grandes como indicación de una asociación más fuerte.
title: Visualización de acordes de asociación
uuid: c656ffc8-e45a-44c0-a29b-cdc10dcbd1f2
exl-id: e71394ef-4895-4a3e-912d-d6f56ca8f001
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '428'
ht-degree: 1%

---

# Visualización de acordes de asociación{#association-chord-visualization}

{{eol}}

La visualización del acorde de asociación le permite mostrar la proporción y la asociación entre métricas, dimensiones y elementos, mostrando coros más grandes como indicación de una asociación más fuerte.

La tabla Asociaciones compara valores con el cálculo de V de Cramer en lugar de usar el coeficiente de correlación de Pearson como se usa en la [Matriz de correlación](/help/home/c-get-started/c-analysis-vis/c-correlation-analysis/c-correlation-analysis.md) y [Correlación](/help/home/c-get-started/c-analysis-vis/associations-visualization.md) visualizaciones (solo pueden comparar métricas, mientras que la tabla de asociación y el acorde pueden comparar métricas, dimensiones y elementos). El acorde de asociaciones también proporciona otra vista en una [Tabla de asociaciones](../../../home/c-get-started/c-analysis-vis/associations-visualization.md#concept-9d937dda38174875b32095c6eaf22f2f).

**Para crear un acorde de asociación**

1. En un espacio de trabajo, haga clic con el botón derecho **Visualización > Análisis predictivo > acorde de asociación**.

   Se abrirá un menú que le permite seleccionar una dimensión ampliada de la lista.

   ![](assets/association_chord1.png)

   Una vez seleccionada, la tabla de asociación en blanco se abrirá con el Dimension seleccionado identificado en el título. ![](assets/association_chord2.png)

1. **Seleccionar una métrica, dimensión o elemento de dimensión**.

   Haga clic con el botón derecho en la visualización de acordes y seleccione **Agregar métrica** o **Agregar Dimension**. Seleccione elementos del menú para agregarlos al acorde.

   También puede arrastrar métricas y dimensiones desde el **[!UICONTROL Finder]** haciendo clic en **[!UICONTROL Ctrl-Alt]** y arrastrando métricas y dimensiones al acorde. O arrastre elementos de dimensión directamente desde una tabla abierta a la visualización de acordes.

1. **Elegir métricas, dimensiones y elementos adicionales para asociar**.

   Después de seleccionar dos o más valores, el gráfico se actualizará automáticamente y empezará a mostrar los datos de asociación. Siga agregando métricas según sea necesario para asociar puntos de datos.

   ![](assets/association_chord.png)

   La visualización del acorde muestra la proporción del total representado por el área de cada segmento. Siga agregando métricas, dimensiones/elementos según sea necesario para identificar e investigar las relaciones significativas.

1. **Visualización del acorde**.

   Pase el ratón sobre cada valor de la visualización para ver las relaciones.

1. **Cambiar configuración.** Haga clic con el botón derecho en la visualización de acordes para abrir un menú a fin de cambiar la métrica, la dimensión o los elementos para mostrar las dimensiones como números absolutos o como porcentajes, eliminar la métrica seleccionada o todas las métricas, editar los colores y detalles y exportar valores a una tabla de asociaciones.

**Para crear un acorde de asociación a partir de una tabla de asociación:**

1. Abra un **Tabla de asociación** visualización.
1. Haga clic con el botón derecho y seleccione **Exportación de visualización de acordes**. Se abrirá un diagrama del acorde de asociación con valores seleccionados en la tabla de asociación. ![](assets/association_table_to_chord.png)

>[!IMPORTANT]
>
>Exportar una tabla de asociación de un diagrama de acordes de asociación que contenga al menos una métrica dará como resultado elementos duplicados en las filas y columnas de la tabla de asociación. Para evitar elementos duplicados, cree una nueva tabla de asociación y añada los elementos deseados en lugar de exportarlos desde un diagrama de acordes de asociación.
