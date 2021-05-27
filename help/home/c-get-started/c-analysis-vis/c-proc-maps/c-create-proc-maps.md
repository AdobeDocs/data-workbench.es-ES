---
description: Puede crear mapas de procesos 2D y 3D arrastrando y soltando elementos de gráficos de barras, tablas y vistas de jerarquía en un mapa en blanco.
title: Creación de un mapa de proceso
uuid: dbcde637-0411-4296-99ca-5510e0285e4b
exl-id: 2e417a8e-5b1c-4dce-9e4e-ac7ed044564c
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '469'
ht-degree: 1%

---

# Creación de un mapa de proceso{#create-a-process-map}

Puede crear mapas de procesos 2D y 3D arrastrando y soltando elementos de gráficos de barras, tablas y vistas de jerarquía en un mapa en blanco.

Los elementos que se pueden añadir deben ser elementos de la dimensión base del mapa del proceso. También puede arrastrar y soltar nodos de un mapa de proceso a otro siempre que los mapas utilicen la misma dimensión base. Además, el mapa completo se puede ampliar o mover para centrarse en un nodo concreto, o puede cambiarse a otros tipos de visualización. Consulte [Ampliación en visualizaciones](../../../../home/c-get-started/c-vis/c-zoom-vis.md#concept-7e33670bb5344f78a316f1a84cc20530).

**Adición de elementos a un mapa de proceso mediante un gráfico de tablas o barras**

* Desde cualquier gráfico de tablas o barras con la misma dimensión base que el mapa de procesos, pulse Ctrl+Alt mientras hace clic y arrastra elementos individuales al mapa de procesos. El cursor del ratón muestra la palabra &quot;No&quot; hasta que el ratón llegue al mapa de procesos.

   >[!NOTE]
   >
   >Los elementos que se pueden añadir deben ser elementos de la dimensión base del mapa del proceso.

   ![](assets/vis_2DProcessMap_addPages.png)

**Adición de elementos a un mapa de proceso mediante una vista de jerarquía**

>[!NOTE]
>
>Adobe recomienda agregar nodos del nivel más alto de la jerarquía que está analizando.

1. Desde cualquier tabla o gráfico de barras con la misma dimensión base que el mapa de procesos, haga clic con el botón derecho en un elemento o en la etiqueta de la dimensión base y haga clic en **[!UICONTROL Hierarchy View]**.
1. Pulse Ctrl+Alt mientras hace clic y arrastra los elementos al mapa de procesos. El cursor del ratón muestra la palabra &quot;No&quot; hasta que el ratón llegue al mapa.

   >[!NOTE]
   >
   >Los elementos que se pueden añadir deben ser elementos de la dimensión base del mapa del proceso.

   Al arrastrar un solo elemento a un mapa de procesos, se crea un nodo de mapa solo para ese elemento, pero si selecciona varios elementos (un grupo) o una carpeta que contiene varios elementos, al arrastrar desde la jerarquía se crea un solo nodo para ese grupo o carpeta. Por ejemplo, si está trabajando con datos de sitios web, al arrastrar una carpeta denominada [!DNL site.com/cgi-bin] a un mapa, se crea un nodo llamado [!DNL site.com/cgi-bin/*], que representa todas las páginas y directorios que son secundarios de esa carpeta.

Para obtener más información sobre las vistas de jerarquía de página, consulte [Aplicación de vistas de jerarquía](../../../../home/c-get-started/c-analysis-vis/c-tables/c-hier-vews.md#concept-b461183424a841eb94f8143a0eaf9bff).

**Adición de nodos a un mapa de proceso desde otro mapa de proceso**

>[!NOTE]
>
>Los mapas de proceso deben tener la misma dimensión base.

* Copie un nodo del primer al segundo mapa de proceso mediante los siguientes métodos:

   * Para copiar nodos individuales, haga clic y arrastre cada nodo al segundo mapa de proceso.
   * Para copiar varios nodos, pulse Ctrl+clic y arrastre para crear un cuadro alrededor de los nodos que desee copiar y, a continuación, haga clic y arrastre los nodos resaltados al segundo mapa de proceso. Todos los nodos resaltados se copian en el segundo mapa de proceso.
