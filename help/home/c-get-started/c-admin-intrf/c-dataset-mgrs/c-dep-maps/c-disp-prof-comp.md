---
description: Puede elegir mostrar los componentes del conjunto de datos del perfil, los componentes del modelo de consulta o los espacios de trabajo, los informes, las opciones de menú y las capas de globo en el mapa de dependencia.
solution: Analytics
title: Mostrar componentes de perfil
topic: Data workbench
uuid: c904dcb7-6bb9-445c-be55-0573f88928ad
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Mostrar componentes de perfil{#display-profile-components}

Puede elegir mostrar los componentes del conjunto de datos del perfil, los componentes del modelo de consulta o los espacios de trabajo, los informes, las opciones de menú y las capas de globo en el mapa de dependencia.

**Seleccionar los componentes que se van a mostrar**

1. Haga clic con el botón derecho en el mapa de dependencia y haga clic en **[!UICONTROL Display]**.
1. Elija una o varias de las siguientes opciones para mostrar en el mapa. Aparece una X a la izquierda de cada opción de visualización que active.

   * **Conjunto de datos** para mostrar los componentes del conjunto de datos. Consulte Componentes [de conjuntos de datos](../../../../../home/c-get-started/c-admin-intrf/c-dataset-mgrs/c-dep-maps/c-dataset-comp.md#concept-4afe28ad29d14eca8a5000847254c293). Si elige mostrar los componentes del conjunto de datos, tiene la opción de [!DNL Include File Blocks] en el mapa. Consulte [Uso de bloques](../../../../../home/c-get-started/c-admin-intrf/c-dataset-mgrs/c-dep-maps/c-wkg-file-blocks.md#concept-3652bbabfbd34449a5f842d8aa598efc)de archivos.

   * **Modelo** de consulta para mostrar los componentes del modelo de consulta. Consulte Componentes [del modelo de consulta](../../../../../home/c-get-started/c-admin-intrf/c-dataset-mgrs/c-dep-maps/c-qry-mod-comp.md#concept-32c6dadd32f74179b026c7e96d47710f).

   * **Espacios de trabajo y visualizaciones** para mostrar espacios de trabajo, informes, opciones de menú y capas de globo terráqueo. Consulte [Espacios de trabajo y Visualizaciones](../../../../../home/c-get-started/c-admin-intrf/c-dataset-mgrs/c-dep-maps/c-wksps-vis.md#concept-abbd4fb115ff47f49f879466ce274921). Esta opción solo funciona si la opción de [!DNL Query Model] visualización está activada.

>[!NOTE]
>
>Si la opción de [!DNL Query Model] visualización no está activada al elegir la opción de [!DNL Workspaces and Visualizations] visualización, aparece un mensaje de error.

Si no puede ver todos los nodos del mapa, puede mover el mapa, acercarlo o alejarlo para mostrar todo el mapa o para centrarse en una sección en particular. Para obtener más información sobre el zoom, consulte [Zoom en Visualizaciones](../../../../../home/c-get-started/c-vis/c-zoom-vis.md#concept-7e33670bb5344f78a316f1a84cc20530).

Al hacer clic en un nodo, todos los nodos que dependen de él y todos los nodos de los que depende se resaltan y se muestran sus nombres.

![](assets/vis_DependencyMap_HighlightedPath.png)

>[!NOTE]
>
>Una ruta resaltada en un mapa de dependencia no constituye una selección.

Al hacer clic con el botón derecho en un nodo, se puede ver la información de identificación de cada componente que se muestra en el mapa y elegir las opciones de menú que le permiten ver más detalles sobre el componente o editarlo. Además, puede realizar búsquedas de texto y mostrar información de rendimiento para transformaciones y dimensiones extendidas.
