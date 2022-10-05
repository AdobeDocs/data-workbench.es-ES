---
description: Información conceptual sobre los componentes del conjunto de datos.
title: Componentes de conjunto de datos
uuid: a5dde039-3b79-4543-9953-995eefc73b5f
exl-id: 6be625c5-1a2e-4b0d-9c34-5f3baec4ba81
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '278'
ht-degree: 1%

---

# Componentes de conjunto de datos{#dataset-components}

{{eol}}

Información conceptual sobre los componentes del conjunto de datos.

La siguiente figura muestra un mapa de dependencias cuyos nodos representan las fuentes de registro, los campos, las transformaciones y las dimensiones extendidas de un conjunto de datos.

![](assets/vis_DependencyMap.png)

* Un nodo amarillo-verde representa una o más fuentes de registro o un filtro (como una condición de entrada de registro) definidos en el conjunto de datos.

   * Un nodo para un origen de registro siempre aparece más a la izquierda en el mapa. Si el conjunto de datos tiene un único origen de registro, el mapa muestra el origen de registro: *nombre de origen de registro*. Si el conjunto de datos tiene varias fuentes de registro, se muestra el mapa *number* Fuentes de registro, donde número es el recuento de fuentes de registro. Por ejemplo, si tiene tres fuentes de registro en el conjunto de datos, el mapa muestra 3 fuentes de registro.

   * El mapa muestra un nodo de condición de entrada de registro para cada [!DNL log processing dataset include] pero solo un nodo de condición de entrada de registro para la transformación (si se define en la variable [!DNL Transformation.cfg] ). Si la condición de entrada de registro está vacía, no se muestra en el mapa.

* Un nodo gris representa un campo que aparece en la lista del parámetro Fields de una [!DNL Log Processing.cfg] o [!DNL Log Processing include] archivo.

* Un nodo azul representa una transformación.
* Un nodo verde representa una dimensión extendida.

>[!NOTE]
>
>Si la carpeta del conjunto de datos de su perfil contiene el archivo [!DNL Insight Transform.cfg], el mapa de dependencias muestra las fuentes de registro, las transformaciones y los exportadores definidos para su uso con Transform. Para obtener información sobre Transformar, consulte la *Guía de configuración de conjuntos de datos*.

Al habilitar la opción Incluir [!DNL File Blocks] opción de visualización, el mapa muestra un nodo azul único para todas las transformaciones definidas en un archivo de configuración de conjunto de datos y un nodo verde único para todas las dimensiones extendidas definidas en un archivo de configuración de conjunto de datos. Para obtener más información sobre esta opción de visualización, consulte [Uso de bloques de archivos](../../../../../home/c-get-started/c-admin-intrf/c-dataset-mgrs/c-dep-maps/c-wkg-file-blocks.md#concept-3652bbabfbd34449a5f842d8aa598efc).
