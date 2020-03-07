---
description: Información conceptual sobre los componentes de conjuntos de datos.
solution: Analytics
title: Componentes de conjunto de datos
topic: Data workbench
uuid: a5dde039-3b79-4543-9953-995eefc73b5f
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Componentes de conjunto de datos{#dataset-components}

Información conceptual sobre los componentes de conjuntos de datos.

La siguiente figura muestra un mapa de dependencia cuyos nodos representan las fuentes de registro, los campos, las transformaciones y las dimensiones extendidas de un conjunto de datos.

![](assets/vis_DependencyMap.png)

* Un nodo amarillo-verde representa uno o más orígenes de registro o un filtro (como una condición de entrada de registro) definido en el conjunto de datos.

   * Un nodo para un origen de registro siempre aparece más a la izquierda en el mapa. Si el conjunto de datos tiene un único origen de registro, el mapa muestra el origen de registro: nombre *de origen del* registro. Si el conjunto de datos tiene varias fuentes de registro, el mapa muestra el *número* de fuentes de registro, donde el número es el número de fuentes de registro. Por ejemplo: si tiene tres orígenes de registro en el conjunto de datos, el mapa muestra 3 orígenes de registro.

   * El mapa muestra un nodo Condición de entrada de registro para cada [!DNL log processing dataset include] archivo, pero solo un nodo Condición de entrada de registro para la transformación (si se define en el [!DNL Transformation.cfg] archivo). Si la condición de entrada de registro está vacía, no se muestra en el mapa.

* Un nodo gris representa un campo que aparece en el parámetro Fields de un [!DNL Log Processing.cfg] archivo o [!DNL Log Processing include] archivo.

* Un nodo azul representa una transformación.
* Un nodo verde representa una dimensión extendida.

>[!NOTE]
>
>Si la carpeta Dataset del perfil contiene el archivo [!DNL Insight Transform.cfg], el mapa de dependencias muestra los orígenes de registro, las transformaciones y los exportadores definidos para su uso con Transform. Para obtener más información sobre Transformar, consulte la Guía *de configuración de* Dataset.

Cuando se activa la opción de visualización Incluir [!DNL File Blocks] , el mapa muestra un solo nodo azul para todas las transformaciones definidas en un archivo de configuración de conjunto de datos y un único nodo verde para todas las dimensiones extendidas definidas en un archivo de configuración de conjunto de datos. Para obtener más información sobre esta opción de visualización, consulte [Uso de bloques](../../../../../home/c-get-started/c-admin-intrf/c-dataset-mgrs/c-dep-maps/c-wkg-file-blocks.md#concept-3652bbabfbd34449a5f842d8aa598efc)de archivos.
