---
description: Los mapas de dependencias permiten visualizar y administrar la configuración de los componentes de su perfil.
title: Mapas de dependencias
uuid: c869267c-5fa9-43b8-b4d4-06c7a36bfa8e
exl-id: 4618c735-f507-4abc-a4b4-d52a37c64c60,733407ca-3326-406a-a642-a3ea3d3f6b8b
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '488'
ht-degree: 1%

---

# Mapas de dependencias{#dependency-maps}

Los mapas de dependencias permiten visualizar y administrar la configuración de los componentes de su perfil.

* **Componentes de conjunto de datos:** fuentes de registro, filtros, campos, transformaciones y dimensiones ampliadas definidas en los  [!DNL Log Processing.cfg]archivos,  [!DNL Transformation.cfg]y  [!DNL dataset include] archivos de su conjunto de datos.

* **Componentes del modelo de consulta:** métricas, dimensiones y filtros definidos en las carpetas Dimension, Métricas y Filtros.
* **Espacios de trabajo y visualizaciones:** Espacios de trabajo, informes, opciones de menú y capas de globo terráqueo.

Para obtener más información sobre cómo trabajar con componentes, espacios de trabajo y visualizaciones del modelo de consulta en los mapas de dependencias, consulte la *Guía del usuario de Data Workbench*.

Los componentes de perfil se representan mediante puntos de color (nodos) en el mapa. Las líneas que conectan los nodos muestran dependencias, es decir, cómo se relacionan los componentes entre sí. Una línea entre dos nodos significa que una salida del nodo de la izquierda es una entrada del nodo de la derecha, es decir, el nodo derecho depende del nodo izquierdo.

## Visualización de los componentes del conjunto de datos {#section-3e51c09c23cc40aeade2e6ad0fa7c8d2}

1. Haga clic con el botón derecho en el mapa de dependencias y haga clic en **[!UICONTROL Display]**.
1. Elegir **[!UICONTROL Dataset]**. Aparece una X a la izquierda de [!DNL Dataset].

Para obtener más información sobre las otras opciones de visualización, consulte la *Guía del usuario de Data Workbench*.

La siguiente figura muestra un mapa de dependencias cuyos nodos representan las fuentes de registro, los campos, las transformaciones y las dimensiones extendidas de un conjunto de datos.

![](assets/vis_DependencyMap.png)

* Un nodo amarillo-verde representa una o más fuentes de registro o un filtro definido en el conjunto de datos. Un nodo para un origen de registro siempre aparece más a la izquierda en el mapa.
* Un nodo gris representa un campo que aparece en el parámetro Fields de un archivo [!DNL Log Processing.cfg] o [!DNL Log Processing Include].

* Un nodo azul representa una transformación.
* Un nodo verde representa una dimensión extendida.

>[!NOTE]
>
>Si el conjunto de datos tiene un único origen de registro, el mapa muestra el origen de registro: *nombre del origen de registro*. Si el conjunto de datos tiene varias fuentes de registro, el mapa muestra *número* Fuentes de registro, donde número es el recuento de las fuentes de registro. Por ejemplo, si tiene tres fuentes de registro en el conjunto de datos, el mapa muestra 3 fuentes de registro.

Si no puede ver todos los nodos del mapa, puede mover el mapa, acercar o alejar para mostrar todo el mapa o para centrarse en una sección en particular. Para obtener más información sobre el zoom, consulte el capítulo Trabajo con visualizaciones de la *Guía del usuario de Data Workbench*.

Al hacer clic en un nodo, todos los nodos que dependen de él y todos los nodos de los que depende se resaltan y se muestran sus nombres.

![](assets/vis_DependencyMap_HighlightedPath.png)

>[!NOTE]
>
>Una ruta resaltada en un mapa de dependencias no constituye una selección.

Al hacer clic con el botón derecho en un nodo, puede ver información de identificación sobre cada componente mostrado en el mapa y elegir las opciones de menú que le permiten ver más detalles sobre el componente o editar el componente. Además, puede realizar búsquedas de texto y mostrar información de rendimiento para transformaciones y dimensiones extendidas.

Para obtener información sobre estas funciones para los mapas de dependencias, consulte el capítulo Interfaces administrativas de la *Guía del usuario de Data Workbench*.
