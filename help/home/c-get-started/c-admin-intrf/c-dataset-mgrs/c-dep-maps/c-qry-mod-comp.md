---
description: Información conceptual sobre los componentes del modelo de consulta.
title: Componentes del modelo de consulta
uuid: 708fab0b-dc10-4306-b410-49268069ac3b
exl-id: 1f5d0a3a-6647-4762-ab20-9d80e467d48f
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '160'
ht-degree: 3%

---

# Componentes del modelo de consulta{#query-model-components}

{{eol}}

Información conceptual sobre los componentes del modelo de consulta.

La siguiente ilustración muestra un mapa de dependencias cuyos nodos representan las métricas, dimensiones derivadas y filtros de un modelo de consulta definidos en las carpetas Dimension, Métricas y Filtros dentro del perfil, así como las dimensiones extendidas definidas en el conjunto de datos que se relacionan con ellos de alguna manera.

![](assets/vis_DependencyMap_QueryModel.png)

* Un nodo amarillo-verde representa un filtro.
* Un nodo morado representa una métrica.
* Un nodo azul-verde representa una dimensión derivada.
* Un nodo verde representa una dimensión extendida (definida en el conjunto de datos).
* Un nodo rojo representa una métrica, una dimensión derivada o un filtro con una dependencia rota o circular u otro error.

>[!NOTE]
>
>Debido a que el mapa de dependencias está diseñado para admitir dependencias acíclicas, es posible que los nodos involucrados en dependencias circulares no se muestren correctamente en el mapa. Puede buscar dependencias circulares escribiendo &quot;dependencia circular&quot; en la sección [!DNL Search] cuadro de texto. Para obtener más información sobre la variable [!DNL Search] función, consulte [Búsqueda dentro de un mapa](../../../../../home/c-get-started/c-admin-intrf/c-dataset-mgrs/c-dep-maps/t-srch-map.md#task-a1e7065a538d46c78a7d28676d880dfb).
