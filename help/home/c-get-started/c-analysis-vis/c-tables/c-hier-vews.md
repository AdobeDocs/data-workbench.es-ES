---
description: Las vistas de jerarquía solo están disponibles cuando se utiliza la aplicación Site o HBX.
solution: Analytics
title: Aplicar vistas de jerarquía
topic: Data workbench
uuid: 859a92af-4f7e-4bb5-9a98-917006894301
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Aplicar vistas de jerarquía{#apply-hierarchy-views}

Las vistas de jerarquía solo están disponibles cuando se utiliza la aplicación Site o HBX.

La vista de jerarquía muestra las páginas de un sitio web organizadas jerárquicamente por nombre de archivo y ordenadas alfabéticamente. Aunque resulta útil para el propio análisis, la vista de jerarquía también se puede utilizar para configurar visualizaciones avanzadas como los mapas de proceso. Para obtener más información sobre los mapas de procesos, consulte Mapas [de procesos](../../../../home/c-get-started/c-analysis-vis/c-proc-maps/c-proc-maps.md#concept-880aee224404429785b733a4e80d275e).

>[!NOTE]
>
>Si el conjunto de datos se ha configurado para ejecutarse en varios servidores de un clúster, para que esta función funcione correctamente, el administrador del sistema debe designar qué máquina funciona como servidor de normalización central. Para ver los pasos a seguir, consulte el capítulo Archivo de configuración de procesamiento de registros de la Guía *de configuración de* Dataset.

![](assets/vis_Table_CompareHierarchy.png)

**Para habilitar o deshabilitar la vista de jerarquía**

* Desde cualquier visualización de página o URI, haga clic con el botón derecho en un elemento o en la etiqueta de la dimensión de página y haga clic en **[!UICONTROL Hierarchy View]**.

   ![](assets/mnu_Table_HierarchyView.png)

   Se muestra una X junto a la opción cuando el [!DNL hierarchy view] está activo.

   La jerarquía se organiza en secciones y páginas del sitio web con una estructura de árbol. Las secciones (nodos) se pueden expandir o condensar usando el símbolo + o - junto al nombre de la sección. Las páginas individuales no tienen un símbolo + o - junto a ellas.

   ![](assets/vis_Table_HierarchyView_Expanded.png)

## Enmascaramiento de elementos de dimensión en una vista de jerarquía {#section-e477c469934846da8d807f92fc2f3ed1}

El enmascaramiento se refiere a seleccionar un subconjunto de los datos o un subconjunto de los elementos de una dimensión. Puede enmascarar u ocultar los elementos que no desee incluir en el análisis. Con las opciones de [!DNL Mask] menú para las vistas de jerarquía, se selecciona el porcentaje mínimo de una métrica que un elemento debe mostrar en la visualización.

**Para enmascarar datos con la opción de[!DNL Mask]menú**

1. Haga clic con el botón derecho en un elemento o en la etiqueta de la dimensión y haga clic en **[!UICONTROL Mask]**.

   ![](assets/mnu_Table_HierarchyView_Masking.png)

1. En Más que, haga clic en el porcentaje correspondiente y, a continuación, haga clic en la métrica que desee enmascarar.

Por ejemplo: si hace clic en 0,1% y luego en Vistas de página, oculta cualquier elemento que tenga menos del 0,1% del número total de vistas de páginas y muestra cualquier elemento que tenga más del 0,1% del número total de vistas de páginas. Si hace clic en 0%, ocultará todos los elementos con un valor de 0 (cero) para la métrica seleccionada.
