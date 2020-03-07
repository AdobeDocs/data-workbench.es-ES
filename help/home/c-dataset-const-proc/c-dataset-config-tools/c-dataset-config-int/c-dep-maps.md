---
description: Los mapas de dependencia permiten visualizar y administrar la configuración de los componentes de su perfil.
solution: Analytics
title: Mapas de dependencia
topic: Data workbench
uuid: c869267c-5fa9-43b8-b4d4-06c7a36bfa8e
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Mapas de dependencia{#dependency-maps}

Los mapas de dependencia permiten visualizar y administrar la configuración de los componentes de su perfil.

* **Componentes de conjunto de datos:** Orígenes de registro, filtros, campos, transformaciones y dimensiones extendidas definidos en los archivos [!DNL Log Processing.cfg], [!DNL Transformation.cfg]y [!DNL dataset include] del conjunto de datos.

* **Componentes del modelo de consulta:** Métricas, dimensiones y filtros definidos en las carpetas Dimensiones, Métricas y Filtros.
* **Espacios de trabajo y visualizaciones:** Espacios de trabajo, informes, opciones de menú y capas de globo terráqueo.

Para obtener más información sobre el trabajo con componentes, espacios de trabajo y visualizaciones del modelo de consulta en mapas de dependencia, consulte la Guía *del usuario de Área de trabajo de* datos.

Los componentes de perfil se representan mediante puntos de color (nodos) en el mapa. Las líneas que conectan los nodos representan dependencias, es decir, cómo se relacionan los componentes entre sí. Una línea entre dos nodos significa que una salida del nodo de la izquierda es una entrada del nodo de la derecha, es decir, el nodo derecho depende del nodo izquierdo.

## Visualización de los componentes del conjunto de datos {#section-3e51c09c23cc40aeade2e6ad0fa7c8d2}

1. Haga clic con el botón derecho en el mapa de dependencia y haga clic en **[!UICONTROL Display]**.
1. Elegir **[!UICONTROL Dataset]**. Aparece una X a la izquierda de [!DNL Dataset].

Para obtener más información sobre las demás opciones de visualización, consulte la Guía del usuario *del área de trabajo de datos*.

La siguiente figura muestra un mapa de dependencia cuyos nodos representan las fuentes de registro, los campos, las transformaciones y las dimensiones extendidas de un conjunto de datos.

![](assets/vis_DependencyMap.png)

* Un nodo amarillo-verde representa uno o más orígenes de registro o un filtro definido en el conjunto de datos. Un nodo para un origen de registro siempre aparece más a la izquierda en el mapa.
* Un nodo gris representa un campo que aparece en el parámetro Fields de un [!DNL Log Processing.cfg] archivo o [!DNL Log Processing Include]archivo.

* Un nodo azul representa una transformación.
* Un nodo verde representa una dimensión extendida.

>[!NOTE]
>
>Si el conjunto de datos tiene un único origen de registro, el mapa muestra el origen de registro: nombre *de origen del* registro. Si el conjunto de datos tiene varias fuentes de registro, el mapa muestra el *número* de fuentes de registro, donde el número es el número de fuentes de registro. Por ejemplo: si tiene tres orígenes de registro en el conjunto de datos, el mapa muestra 3 orígenes de registro.

Si no puede ver todos los nodos del mapa, puede mover el mapa, acercarlo o alejarlo para mostrar todo el mapa o para centrarse en una sección en particular. Para obtener más información sobre el zoom, consulte el capítulo Trabajo con visualizaciones de la Guía del usuario de *Área de trabajo de datos*.

Al hacer clic en un nodo, todos los nodos que dependen de él y todos los nodos de los que depende se resaltan y se muestran sus nombres.

![](assets/vis_DependencyMap_HighlightedPath.png)

>[!NOTE]
>
>Una ruta resaltada en un mapa de dependencia no constituye una selección.

Al hacer clic con el botón derecho en un nodo, se puede ver la información de identificación de cada componente que se muestra en el mapa y elegir las opciones de menú que le permiten ver más detalles sobre el componente o editarlo. Además, puede realizar búsquedas de texto y mostrar información de rendimiento para transformaciones y dimensiones extendidas.

Para obtener más información sobre estas funciones para los mapas de dependencia, consulte el capítulo Interfaces administrativas de la Guía *del usuario de Área de trabajo de* datos.
