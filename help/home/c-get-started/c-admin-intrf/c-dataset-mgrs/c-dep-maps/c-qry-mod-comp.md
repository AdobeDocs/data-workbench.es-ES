---
description: Información conceptual sobre los componentes del modelo de consulta.
solution: Analytics
title: Componentes del modelo de consulta
topic: Data workbench
uuid: 708fab0b-dc10-4306-b410-49268069ac3b
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Componentes del modelo de consulta{#query-model-components}

Información conceptual sobre los componentes del modelo de consulta.

La siguiente figura muestra un mapa de dependencia cuyos nodos representan las métricas, las dimensiones derivadas y los filtros del modelo de consulta definidos en las carpetas Dimensiones, Métricas y Filtros dentro del perfil, así como las dimensiones extendidas definidas en el conjunto de datos que se relacionan con ellos de alguna manera.

![](assets/vis_DependencyMap_QueryModel.png)

* Un nodo amarillo-verde representa un filtro.
* Un nodo púrpura representa una métrica.
* Un nodo azul-verde representa una dimensión derivada.
* Un nodo verde representa una dimensión extendida (definida en el conjunto de datos).
* Un nodo rojo representa una métrica, una dimensión derivada o un filtro con una dependencia rota o circular u otro error.

>[!NOTE]
>
>Debido a que el mapa de dependencias está diseñado para alojar dependencias acíclicas, es posible que los nodos involucrados en dependencias circulares no se muestren correctamente en el mapa. Puede buscar dependencias circulares escribiendo &quot;dependencia circular&quot; en el cuadro de texto [!DNL Search] . Para obtener más información sobre la [!DNL Search] función, consulte [Búsqueda dentro de un mapa](../../../../../home/c-get-started/c-admin-intrf/c-dataset-mgrs/c-dep-maps/t-srch-map.md#task-a1e7065a538d46c78a7d28676d880dfb).

