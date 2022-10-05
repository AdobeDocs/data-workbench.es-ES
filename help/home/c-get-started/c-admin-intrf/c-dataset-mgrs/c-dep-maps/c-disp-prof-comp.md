---
description: Puede elegir mostrar los componentes del conjunto de datos del perfil, los componentes del modelo de consulta o los espacios de trabajo, los informes, las opciones de menú y las capas de globo terráqueo en el mapa de dependencias.
title: Mostrar componentes de perfil
uuid: c904dcb7-6bb9-445c-be55-0573f88928ad
exl-id: 9d0aea02-cc24-43c2-afb8-e11ebd80e193
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '313'
ht-degree: 1%

---

# Mostrar componentes de perfil{#display-profile-components}

{{eol}}

Puede elegir mostrar los componentes del conjunto de datos del perfil, los componentes del modelo de consulta o los espacios de trabajo, los informes, las opciones de menú y las capas de globo terráqueo en el mapa de dependencias.

**Seleccionar los componentes que se van a mostrar**

1. Haga clic con el botón derecho en el mapa de dependencias y haga clic en **[!UICONTROL Display]**.
1. Elija una o más de las siguientes opciones para mostrar en el mapa. Aparece una X a la izquierda de cada opción de visualización que active.

   * **Conjunto de datos** para mostrar los componentes del conjunto de datos. Consulte [Componentes de conjunto de datos](../../../../../home/c-get-started/c-admin-intrf/c-dataset-mgrs/c-dep-maps/c-dataset-comp.md#concept-4afe28ad29d14eca8a5000847254c293). Si elige mostrar los componentes del conjunto de datos, tiene la opción de [!DNL Include File Blocks] en el mapa. Consulte [Uso de bloques de archivos](../../../../../home/c-get-started/c-admin-intrf/c-dataset-mgrs/c-dep-maps/c-wkg-file-blocks.md#concept-3652bbabfbd34449a5f842d8aa598efc).

   * **Modelo de consulta** para mostrar los componentes del modelo de consulta. Consulte [Componentes del modelo de consulta](../../../../../home/c-get-started/c-admin-intrf/c-dataset-mgrs/c-dep-maps/c-qry-mod-comp.md#concept-32c6dadd32f74179b026c7e96d47710f).

   * **Espacios de trabajo y visualizaciones** para mostrar espacios de trabajo, informes, opciones de menú y capas de globo terráqueo. Consulte [Espacios de trabajo y visualizaciones](../../../../../home/c-get-started/c-admin-intrf/c-dataset-mgrs/c-dep-maps/c-wksps-vis.md#concept-abbd4fb115ff47f49f879466ce274921). Esta opción solo funciona si la variable [!DNL Query Model] la opción de visualización está activada.

>[!NOTE]
>
>Si la variable [!DNL Query Model] la opción de visualización no está activada al elegir la opción [!DNL Workspaces and Visualizations] opción de visualización, aparece un mensaje de error.

Si no puede ver todos los nodos del mapa, puede mover el mapa, acercar o alejar para mostrar todo el mapa o para centrarse en una sección en particular. Para obtener más información sobre el zoom, consulte [Ampliación de las visualizaciones](../../../../../home/c-get-started/c-vis/c-zoom-vis.md#concept-7e33670bb5344f78a316f1a84cc20530).

Al hacer clic en un nodo, todos los nodos que dependen de él y todos los nodos de los que depende se resaltan y se muestran sus nombres.

![](assets/vis_DependencyMap_HighlightedPath.png)

>[!NOTE]
>
>Una ruta resaltada en un mapa de dependencias no constituye una selección.

Al hacer clic con el botón derecho en un nodo, puede ver información de identificación sobre cada componente mostrado en el mapa y elegir las opciones de menú que le permiten ver más detalles sobre el componente o editar el componente. Además, puede realizar búsquedas de texto y mostrar información de rendimiento para transformaciones y dimensiones extendidas.
