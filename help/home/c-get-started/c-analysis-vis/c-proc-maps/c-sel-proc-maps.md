---
description: Puede realizar selecciones en los mapas de proceso para crear filtros que incluyan o excluyan datos asociados a un nodo en particular.
solution: Analytics
title: Realizar una selección desde un mapa de procesos
topic: Data workbench
uuid: 7fd00090-c9ab-4bb6-8584-7de7b6f4b68c
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Realizar una selección desde un mapa de procesos{#make-a-selection-from-a-process-map}

Puede realizar selecciones en los mapas de proceso para crear filtros que incluyan o excluyan datos asociados a un nodo en particular.

Realizar una selección dentro de un mapa de proceso implica la dimensión de grupo del mapa, que determina cómo se agrupan los elementos de la dimensión base (es decir, los nodos del mapa) para formar las conexiones entre nodos.

>[!NOTE]
>
>Puede cambiar la dimensión de grupo predeterminada para una asignación de proceso. Consulte [Configuración de mapas](../../../../home/c-get-started/c-intf-anlys-ftrs/t-config-proc-maps.md#task-4a95730b18a14bc790a77c013832b2d6)de proceso.

Al realizar una selección basada en un nodo dentro de una asignación de proceso, se seleccionan todos los elementos de la dimensión de grupo que involucraron ese nodo. Para comprender mejor la función de la dimensión de grupo, tenga en cuenta los siguientes ejemplos:

* Las películas se pueden agrupar por los visores que las hayan clasificado. Cada visor es un elemento de la dimensión Usuario, por lo que la dimensión Usuario sería la dimensión de grupo para la asignación de procesos. Al realizar una selección desde un nodo para una película en particular, se crea un filtro que muestra los datos de los usuarios que clasificaron o no esa película.
* Las páginas del sitio web pueden agruparse según las sesiones en las que se vieron. Cada sesión es un elemento de la dimensión Sesión, por lo que la dimensión Sesión sería la dimensión de grupo para el mapa de procesos. Al realizar una selección desde un nodo para una página en particular, se crea un filtro que muestra los datos de las sesiones durante las cuales se vio o no esa página.

**Para realizar una selección**

1. Haga clic con el botón secundario en cualquier nodo de una asignación de proceso.
1. Haga clic en una de las siguientes opciones para realizar una selección basada en el nodo:

   * **[!UICONTROL Select]*** **[!UICONTROL group dimension name +s]*** **[!UICONTROL through node name]**: Filtra los datos para incluir todos los elementos de la dimensión de grupo que pasaron por el nodo filtrando todas las sesiones que no pasaron por el nodo.

   * **[!UICONTROL Select]*** **[!UICONTROL group dimension name +s]*** **[!UICONTROL NOT through node name]**: Filtra los datos para incluir todos los elementos de la dimensión de grupo que no pasaron por el nodo filtrando todas las sesiones que pasaron por el nodo.

![](assets/vis_2DProcessMap_Selections_Movie.png)

![](assets/vis_2DProcessMap_Selections_Page.png)

Cuando se realiza una selección en un mapa de proceso 3D, el nodo para el que se realiza la selección se rodea. Los puntos de referencia aparecen alrededor de cada barra para ayudarle a comparar los valores de las métricas con o sin la selección. Consulte [Explicación de los puntos de referencia](../../../../home/c-get-started/c-vis/c-ustd-benchmks.md#concept-c7b0f4102e92458096f8c4765cbe2914).

![](assets/vis_3DProcessMap_Selection.png)

