---
description: Puede realizar selecciones dentro de mapas de procesos para crear filtros que incluyan o excluyan datos asociados a un nodo en particular.
title: Realización de una selección desde un mapa del proceso
uuid: 7fd00090-c9ab-4bb6-8584-7de7b6f4b68c
exl-id: 8ede395f-906a-49e0-8ff8-b43a326275e5
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '393'
ht-degree: 3%

---

# Realización de una selección desde un mapa del proceso{#make-a-selection-from-a-process-map}

{{eol}}

Puede realizar selecciones dentro de mapas de procesos para crear filtros que incluyan o excluyan datos asociados a un nodo en particular.

La realización de una selección dentro de un mapa de proceso implica la dimensión de grupo del mapa, que determina cómo se agrupan los elementos de la dimensión base (es decir, los nodos del mapa) para formar las conexiones entre nodos.

>[!NOTE]
>
>Puede cambiar la dimensión de grupo predeterminada para un mapa de proceso. Consulte [Configuración de mapas de procesos](../../../../home/c-get-started/c-intf-anlys-ftrs/t-config-proc-maps.md#task-4a95730b18a14bc790a77c013832b2d6).

Al realizar una selección basada en un nodo dentro de un mapa de procesos, se seleccionan todos los elementos de la dimensión de grupo que involucraron ese nodo. Para comprender mejor la función de la dimensión de grupo, tenga en cuenta los siguientes ejemplos:

* Las películas se pueden agrupar por los espectadores que las clasificaron. Cada visor es un elemento de la dimensión Usuario , por lo que la dimensión Usuario sería la dimensión de grupo para el mapa de proceso. Cuando realiza una selección desde un nodo para una película en particular, crea un filtro que muestra datos para los usuarios que clasificaron o no esa película.
* Las páginas del sitio web se pueden agrupar por las sesiones en las que se vieron. Cada sesión es un elemento de la dimensión Sesión , por lo que la dimensión Sesión sería la dimensión de grupo para el mapa de proceso. Cuando realiza una selección desde un nodo para una página en particular, crea un filtro que muestra los datos de las sesiones durante las cuales se vio o no la página.

**Para realizar una selección**

1. Haga clic con el botón derecho en cualquier nodo de un mapa de proceso.
1. Haga clic en una de las siguientes opciones para realizar una selección basada en el nodo :

   * **[!UICONTROL Select]*** **[!UICONTROL group dimension name +s]*** **[!UICONTROL through node name]**: Filtra los datos para incluir todos los elementos de la dimensión de grupo que pasaron por el nodo filtrando todas las sesiones que no pasaron por el nodo.

   * **[!UICONTROL Select]*** **[!UICONTROL group dimension name +s]*** **[!UICONTROL NOT through node name]**: Filtra los datos para incluir todos los elementos de la dimensión de grupo que no hayan pasado por el nodo filtrando todas las sesiones que pasaron por el nodo .

![](assets/vis_2DProcessMap_Selections_Movie.png)

![](assets/vis_2DProcessMap_Selections_Page.png)

Cuando realiza una selección en un mapa de proceso 3D, el nodo para el que se realiza la selección aparece en círculo. Los puntos de referencia aparecen alrededor de cada barra para ayudarle a comparar los valores de las métricas con o sin la selección. Consulte [Explicación de los puntos de referencia](../../../../home/c-get-started/c-vis/c-ustd-benchmks.md#concept-c7b0f4102e92458096f8c4765cbe2914).

![](assets/vis_3DProcessMap_Selection.png)
