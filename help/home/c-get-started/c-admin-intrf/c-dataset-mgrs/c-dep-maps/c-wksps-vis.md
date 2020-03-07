---
description: Información conceptual sobre espacios de trabajo y visualizaciones.
solution: Analytics
title: Espacios de trabajo y visualizaciones
topic: Data workbench
uuid: dc7fab6c-d8b4-4ed7-bad6-b3df14b9ebbf
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Espacios de trabajo y visualizaciones{#workspaces-and-visualizations}

Información conceptual sobre espacios de trabajo y visualizaciones.

La siguiente figura muestra un mapa de dependencia cuyos nodos representan los espacios de trabajo, los informes, las opciones de menú y las capas de globo definidas en el perfil. Esta opción solo funciona si la opción de [!DNL Query Model] visualización está activada.

>[!NOTE]
>
>Si la opción de [!DNL Query Model] visualización no está activada al elegir la opción de [!DNL Workspaces and Visualizations] visualización, aparece un mensaje de error.

![](assets/vis_DependencyMap_QueryModelandWorkspaces.png)

* Un nodo gris representa un espacio de trabajo o un informe.
* Un nodo amarillo-verde representa una opción de menú.
* Un nodo rojo representa un espacio de trabajo, un informe, una opción de menú o una capa de globo con una dependencia rota o circular u otro error.

>[!NOTE]
>
>Debido a que el mapa de dependencias está diseñado para alojar dependencias acíclicas, es posible que los nodos involucrados en dependencias circulares no se muestren correctamente en el mapa. Puede buscar dependencias circulares escribiendo &quot;dependencia circular&quot; en el cuadro de texto [!DNL Search] . Para obtener más información sobre la [!DNL Search] función, consulte [Búsqueda dentro de un mapa](../../../../../home/c-get-started/c-admin-intrf/c-dataset-mgrs/c-dep-maps/t-srch-map.md#task-a1e7065a538d46c78a7d28676d880dfb).

Para obtener descripciones de otros nodos del mapa, consulte Componentes [del modelo](../../../../../home/c-get-started/c-admin-intrf/c-dataset-mgrs/c-dep-maps/c-qry-mod-comp.md#concept-32c6dadd32f74179b026c7e96d47710f)de consulta.
