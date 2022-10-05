---
description: Los mapas de procesos permiten analizar el flujo de actividad entre elementos de una dimensión.
title: Mapa del proceso
uuid: f1db41a9-400e-467a-ba59-39831fb166af
exl-id: 019cee7b-a704-4b47-84c6-d3ddc277c43e
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '737'
ht-degree: 0%

---

# Mapa del proceso{#process-map}

{{eol}}

Los mapas de procesos permiten analizar el flujo de actividad entre elementos de una dimensión.

Los mapas de proceso se crean arrastrando y soltando los elementos de una dimensión en un mapa bidimensional (2D) o tridimensional (3D) en blanco. Los elementos se convierten en nodos en el mapa. Los nodos son círculos en mapas de proceso 2D y barras en mapas de proceso 3D.

![](assets/vis_2DProcessMap.png)

![](assets/vis_3DProcessMap.png)

>[!NOTE]
>
>Un mapa de procesos obtiene su nombre de su uso en el análisis del flujo de actividad entre los pasos de un proceso. En este tipo de análisis, cada elemento del mapa representa un paso en el proceso.

A diferencia de los exploradores de rutas, los mapas de procesos pueden mostrar tan pocos o tantos elementos como sea necesario para el análisis. Elija los elementos de interés y arrástrelos y suéltelos en el mapa. A diferencia de los exploradores de rutas, los mapas de procesos representan el flujo de actividad en ambas direcciones entre un elemento y uno o más elementos.

>[!NOTE]
>
>Para que estos mapas funcionen de forma más eficaz, debe abrir una leyenda de color en el espacio de trabajo. Para obtener información sobre el uso de leyendas de colores con mapas de procesos, consulte [Activación de vínculos de color](../../../../home/c-get-started/c-analysis-vis/c-proc-maps/c-act-color-lnks.md#concept-2c9b9f67f2bd4cd7a5431fa21c094edc). Para obtener más información sobre las leyendas de color, consulte [Leyendas de color](../../../../home/c-get-started/c-analysis-vis/c-legends/c-color-leg.md#concept-f84d51dc0d6547f981d0642fc2d01358).

Cada mapa de proceso tiene asociada una dimensión base, una dimensión de grupo, una dimensión de nivel y una métrica, que proporcionan claves para interpretar los datos que se muestran en el mapa de proceso.

La configuración predeterminada para las dimensiones y métricas de un mapa de proceso depende de la aplicación de Data Workbench que utilice. Para obtener información sobre las dimensiones y métricas disponibles para los mapas de procesos, consulte la guía de aplicación para la aplicación de Data Workbench.

* **Dimensión base:** Cuando arrastra y suelta un elemento en un mapa de procesos, arrastra y suelta un elemento de la dimensión base.
* **Dimensión de nivel:** Cada dimensión del conjunto de datos tiene una dimensión de nivel asociada (también denominada dimensión principal). La dimensión de nivel para el mapa de proceso debe ser la misma que la dimensión de nivel (o principal) para la dimensión base del mapa de proceso. Por ejemplo, si arrastra una página (un elemento de la dimensión Página) al mapa, la dimensión de nivel correspondiente sería Vista de página.
* **Dimensión de grupo:** La dimensión de grupo determina cómo se agrupan los elementos de la dimensión de nivel para formar las conexiones entre nodos. Para los mapas de procesos, la dimensión de grupo es importante por tres motivos principales:

   * Una conexión entre dos nodos no puede abarcar más de un elemento de una dimensión de grupo. Para entender esto, considere un ejemplo de uso de datos web. Supongamos que las dimensiones base, nivel y grupo de su mapa de proceso son Página, Vista de página y Sesión, respectivamente. Una conexión de la página A a la página B le indica que, durante cualquier sesión única, se produjo una vista de página de la página A antes de una vista de página de la página B sin ninguna vista de página de intervención de otras páginas (nodos) en el mapa. Tenga en cuenta que es posible que se hayan visualizado otras páginas del sitio entre las vistas de página de las páginas A y B durante la misma sesión, pero estas páginas no se muestran en este mapa.
   * Una conexión entre dos nodos puede representar varios elementos de la dimensión de grupo. Por ejemplo, puede haber varias sesiones en las que se produjo una vista de página de la página A antes de una vista de página de la página B. Por lo tanto, la conexión entre la página A y la página B representa todas las sesiones individuales en las que se produjo una vista de página de la página A antes de una vista de página de la página B sin ninguna vista de página de intervención de otras páginas (nodos) en el mapa.
   * Al realizar una selección basada en un nodo dentro de un mapa de procesos, se seleccionan todos los elementos de la dimensión de grupo que involucraron ese nodo. Consulte [Realización de selecciones en visualizaciones](../../../../home/c-get-started/c-vis/c-sel-vis/c-sel-vis.md#concept-012870ec22c7476e9afbf3b8b2515746). Para obtener información sobre las selecciones, consulte [Realización de selecciones en visualizaciones](../../../../home/c-get-started/c-vis/c-sel-vis/c-sel-vis.md#concept-012870ec22c7476e9afbf3b8b2515746).

* **Métrica:** El tamaño del nodo de un elemento determinado es proporcional al valor de la métrica para ese elemento. Los nodos más grandes indican valores de métricas buenos que los nodos más pequeños.

Por ejemplo, si está utilizando la variable [!DNL Site] Para HBX aplicación, puede arrastrar, de forma predeterminada, elementos de la dimensión Página al mapa de proceso. El tamaño de cada nodo está relacionado con la cantidad de sesiones (definida por la métrica Sesiones) en la que se vio la página.

>[!NOTE]
>
>Puede cambiar las dimensiones o métricas predeterminadas de un mapa de proceso. Para ver los pasos para configurar un mapa de procesos, consulte [Configuración de mapas de procesos](../../../../home/c-get-started/c-intf-anlys-ftrs/t-config-proc-maps.md#task-4a95730b18a14bc790a77c013832b2d6).
