---
description: Las vistas de jerarquía solo están disponibles cuando se usa el Sitio o HBX aplicación.
title: Aplicación de vistas de jerarquía
uuid: 859a92af-4f7e-4bb5-9a98-917006894301
exl-id: 27a69404-40d3-44ab-bf5c-b2a5d8d836c2
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '363'
ht-degree: 1%

---

# Aplicación de vistas de jerarquía{#apply-hierarchy-views}

Las vistas de jerarquía solo están disponibles cuando se usa el Sitio o HBX aplicación.

La vista de jerarquía muestra las páginas de un sitio web organizado jerárquicamente por nombre de archivo y ordenado alfabéticamente. Aunque resulta útil para el propio análisis, la vista de jerarquía también se puede utilizar para configurar visualizaciones avanzadas como mapas de proceso. Para obtener más información sobre los mapas de procesos, consulte [Mapas de procesos](../../../../home/c-get-started/c-analysis-vis/c-proc-maps/c-proc-maps.md#concept-880aee224404429785b733a4e80d275e).

>[!NOTE]
>
>Si el conjunto de datos se ha configurado para ejecutarse en varios servidores de un clúster, para que esta característica funcione correctamente, el administrador del sistema debe designar qué equipo funciona como Servidor de Normalización Central. Para ver los pasos a seguir, consulte el capítulo Archivo de configuración de procesamiento de registros de la *Guía de configuración de conjuntos de datos*.

![](assets/vis_Table_CompareHierarchy.png)

**Para habilitar o deshabilitar la vista de jerarquía**

* Desde cualquier visualización de página o URI, haga clic con el botón derecho en un elemento o en la etiqueta de la dimensión de página y haga clic en **[!UICONTROL Hierarchy View]**.

   ![](assets/mnu_Table_HierarchyView.png)

   Se muestra una X junto a la opción cuando la [!DNL hierarchy view] está activa.

   La jerarquía se organiza en secciones y páginas del sitio web con una estructura de árbol. Las secciones (nodos) se pueden expandir o condensar utilizando el símbolo + o - situado junto al nombre de la sección. Las páginas individuales no tienen un símbolo + o - junto a ellas.

   ![](assets/vis_Table_HierarchyView_Expanded.png)

## Enmascaramiento de elementos Dimension en una vista de jerarquía {#section-e477c469934846da8d807f92fc2f3ed1}

Enmascaramiento hace referencia a la selección de un subconjunto de los datos o un subconjunto de los elementos de una dimensión. Los elementos que no desea incluir en el análisis se enmascaran u ocultan. Con las opciones de menú [!DNL Mask] para las vistas de jerarquía, se selecciona el porcentaje mínimo de una métrica que un elemento debe mostrarse en la visualización.

**Enmascarar datos con la opción de  [!DNL Mask] menú**

1. Haga clic con el botón derecho en un elemento o en la etiqueta de la dimensión y haga clic en **[!UICONTROL Mask]**.

   ![](assets/mnu_Table_HierarchyView_Masking.png)

1. En Más que, haga clic en el porcentaje correspondiente y, a continuación, haga clic en la métrica que desee enmascarar.

Por ejemplo, si hace clic en 0,1% y luego en Vistas de página, está ocultando cualquier elemento que tenga menos del 0,1% del número total de vistas de página y mostrando cualquier elemento que tenga más del 0,1% del número total de vistas de página. Si hace clic en 0%, ocultará todos los elementos con un valor de 0 (cero) para la métrica seleccionada.
