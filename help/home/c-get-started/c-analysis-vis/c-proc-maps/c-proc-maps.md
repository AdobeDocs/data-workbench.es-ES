---
description: Los mapas de procesos permiten analizar el flujo de actividad entre los elementos de una dimensión.
solution: Analytics
title: Mapa de procesos
topic: Data workbench
uuid: f1db41a9-400e-467a-ba59-39831fb166af
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Mapa de procesos{#process-map}

Los mapas de procesos permiten analizar el flujo de actividad entre los elementos de una dimensión.

Para crear mapas de procesos, arrastre y suelte los elementos de una dimensión en un mapa bidimensional (2D) o tridimensional (3D) en blanco. Los elementos se convierten en nodos en el mapa. Los nodos son círculos en mapas de proceso 2D y barras en mapas de proceso 3D.

![](assets/vis_2DProcessMap.png)

![](assets/vis_3DProcessMap.png)

>[!NOTE]
>
>Un mapa de procesos obtiene su nombre de su uso en el análisis del flujo de actividad entre los pasos de un proceso. En este tipo de análisis, cada elemento del mapa representa un paso en el proceso.

A diferencia de los exploradores de rutas, los mapas de procesos pueden mostrar tantos o pocos elementos como sea necesario para el análisis. Puede elegir los elementos de interés y arrastrarlos y colocarlos en el mapa. Además, a diferencia de los exploradores de rutas, los mapas de procesos representan el flujo de actividad en ambas direcciones entre un elemento y uno o más elementos.

>[!NOTE]
>
>Para que estos mapas funcionen con mayor eficacia, debe abrir una leyenda de color en el espacio de trabajo. Para obtener información sobre el uso de leyendas de color con mapas de proceso, consulte [Activación de vínculos](../../../../home/c-get-started/c-analysis-vis/c-proc-maps/c-act-color-lnks.md#concept-2c9b9f67f2bd4cd7a5431fa21c094edc)de color. Para obtener más información sobre las leyendas de color, consulte Leyendas [de color](../../../../home/c-get-started/c-analysis-vis/c-legends/c-color-leg.md#concept-f84d51dc0d6547f981d0642fc2d01358).

Cada mapa de procesos tiene una dimensión base, una dimensión de grupo, una dimensión de nivel y una métrica asociadas, que proporcionan claves para interpretar los datos que se muestran en el mapa de procesos.

La configuración predeterminada de las dimensiones y métricas de un mapa de proceso depende de la aplicación Área de trabajo de datos que utilice. Para obtener información sobre las dimensiones y métricas disponibles para los mapas de proceso, consulte la guía de aplicaciones de la aplicación Área de trabajo de datos.

* **Dimensión base:** Cuando arrastra y suelta un elemento en un mapa de proceso, arrastra y suelta un elemento de la dimensión base.
* **Dimensión de nivel:** Cada dimensión del conjunto de datos tiene una dimensión de nivel asociada (también denominada principal). La dimensión de nivel de la asignación de procesos debe ser la misma que la dimensión de nivel (o principal) de la dimensión base de la asignación de procesos. Por ejemplo, si arrastra una página (un elemento de la dimensión Página) al mapa, la dimensión de nivel correspondiente sería Vista de página.
* **Dimensión de grupo:** La dimensión de grupo determina cómo se agrupan los elementos de la dimensión de nivel para formar las conexiones entre nodos. Para los mapas de proceso, la dimensión de grupo es importante por tres motivos principales:

   * Una conexión entre dos nodos no puede abarcar más de un elemento de una dimensión de grupo. Para entenderlo, considere un ejemplo de uso de datos web. Supongamos que las dimensiones base, de nivel y de grupo para el mapa de proceso son Página, Vista de página y Sesión, respectivamente. Una conexión de la página A a la página B le indica que, durante una sola sesión, se produjo una vista de página de la página A antes de una vista de página de la página B sin ninguna vista de página de otras páginas (nodos) en el mapa que interviene. Tenga en cuenta que las vistas de página de otras páginas del sitio pueden haber ocurrido entre las vistas de página de las páginas A y B durante la misma sesión, pero estas páginas no se muestran en este mapa.
   * Una conexión entre dos nodos puede representar varios elementos de la dimensión de grupo. Por ejemplo: puede haber varias sesiones en las que se produjo una vista de página de la página A antes de una vista de página de la página B. Por lo tanto, la conexión entre la página A y la página B representa todas las sesiones individuales en las que se produjo una vista de página de la página A antes de una vista de página de la página B sin ninguna vista de página de otras páginas (nodos) en el mapa.
   * Al realizar una selección basada en un nodo dentro de una asignación de proceso, se seleccionan todos los elementos de la dimensión de grupo que involucraron ese nodo. Consulte [Realizar selecciones en visualizaciones](../../../../home/c-get-started/c-vis/c-sel-vis/c-sel-vis.md#concept-012870ec22c7476e9afbf3b8b2515746). Para obtener información sobre las selecciones, consulte [Realizar selecciones en Visualizaciones](../../../../home/c-get-started/c-vis/c-sel-vis/c-sel-vis.md#concept-012870ec22c7476e9afbf3b8b2515746).

* **Métrica:** El tamaño del nodo de un elemento determinado es proporcional al valor de la métrica para ese elemento. Los nodos más grandes indican valores de métricas buenos que los nodos más pequeños.

Por ejemplo, si utiliza la aplicación [!DNL Site] o HBX, puede arrastrar, de forma predeterminada, elementos de la dimensión Página al mapa del proceso. El tamaño de cada nodo está relacionado con la cantidad de sesiones (definida por la métrica Sesiones) en las que se vio la página.

>[!NOTE]
>
>Puede cambiar las dimensiones o métricas predeterminadas de un mapa de proceso. Para ver los pasos para configurar un mapa de proceso, consulte [Configuración de mapas](../../../../home/c-get-started/c-intf-anlys-ftrs/t-config-proc-maps.md#task-4a95730b18a14bc790a77c013832b2d6)de proceso.

