---
description: Información conceptual sobre espacios de trabajo y visualizaciones.
title: Espacios de trabajo y visualizaciones
uuid: dc7fab6c-d8b4-4ed7-bad6-b3df14b9ebbf
exl-id: a70748dd-8190-4d1b-9ee1-1011b73a1a86
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '163'
ht-degree: 3%

---

# Espacios de trabajo y visualizaciones{#workspaces-and-visualizations}

Información conceptual sobre espacios de trabajo y visualizaciones.

La siguiente figura muestra un mapa de dependencias cuyos nodos representan los espacios de trabajo, informes, opciones de menú y capas de globo terráqueo definidos en el perfil. Esta opción solo funciona si la opción de visualización [!DNL Query Model] está activada.

>[!NOTE]
>
>Si la opción de visualización [!DNL Query Model] no está activada al elegir la opción de visualización [!DNL Workspaces and Visualizations], aparece un mensaje de error.

![](assets/vis_DependencyMap_QueryModelandWorkspaces.png)

* Un nodo gris representa un espacio de trabajo o un informe.
* Un nodo amarillo-verde representa una opción de menú.
* Un nodo rojo representa un espacio de trabajo, informe, opción de menú o capa de globo con una dependencia rota o circular u otro error.

>[!NOTE]
>
>Debido a que el mapa de dependencias está diseñado para admitir dependencias acíclicas, es posible que los nodos involucrados en dependencias circulares no se muestren correctamente en el mapa. Puede buscar dependencias circulares escribiendo &quot;dependencia circular&quot; en el cuadro de texto [!DNL Search]. Para obtener más información sobre la función [!DNL Search], consulte [Búsqueda en un mapa](../../../../../home/c-get-started/c-admin-intrf/c-dataset-mgrs/c-dep-maps/t-srch-map.md#task-a1e7065a538d46c78a7d28676d880dfb).

Para obtener descripciones de otros nodos del mapa, consulte [Componentes del modelo de consulta](../../../../../home/c-get-started/c-admin-intrf/c-dataset-mgrs/c-dep-maps/c-qry-mod-comp.md#concept-32c6dadd32f74179b026c7e96d47710f).
