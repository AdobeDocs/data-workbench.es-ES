---
description: Información conceptual sobre los componentes del conjunto de datos.
title: Componentes de conjunto de datos
uuid: a5dde039-3b79-4543-9953-995eefc73b5f
exl-id: 6be625c5-1a2e-4b0d-9c34-5f3baec4ba81
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '278'
ht-degree: 1%

---

# Componentes de conjunto de datos{#dataset-components}

Información conceptual sobre los componentes del conjunto de datos.

La siguiente figura muestra un mapa de dependencias cuyos nodos representan las fuentes de registro, los campos, las transformaciones y las dimensiones extendidas de un conjunto de datos.

![](assets/vis_DependencyMap.png)

* Un nodo amarillo-verde representa una o más fuentes de registro o un filtro (como una condición de entrada de registro) definidos en el conjunto de datos.

   * Un nodo para un origen de registro siempre aparece más a la izquierda en el mapa. Si el conjunto de datos tiene un único origen de registro, el mapa muestra el origen de registro: *nombre del origen de registro*. Si el conjunto de datos tiene varias fuentes de registro, el mapa muestra *número* Fuentes de registro, donde número es el recuento de las fuentes de registro. Por ejemplo, si tiene tres fuentes de registro en el conjunto de datos, el mapa muestra 3 fuentes de registro.

   * El mapa muestra un nodo de condición de entrada de registro para cada archivo [!DNL log processing dataset include] pero solo un nodo de condición de entrada de registro para la transformación (si se define en el archivo [!DNL Transformation.cfg] ). Si la condición de entrada de registro está vacía, no se muestra en el mapa.

* Un nodo gris representa un campo que aparece en el parámetro Fields de un archivo [!DNL Log Processing.cfg] o [!DNL Log Processing include].

* Un nodo azul representa una transformación.
* Un nodo verde representa una dimensión extendida.

>[!NOTE]
>
>Si la carpeta Dataset de su perfil contiene el archivo [!DNL Insight Transform.cfg], el mapa de dependencias muestra los orígenes de registro, las transformaciones y los exportadores definidos para su uso con Transform. Para obtener más información sobre la Transformación, consulte la *Guía de configuración del conjunto de datos*.

Cuando se activa la opción Incluir [!DNL File Blocks] visualización, el mapa muestra un solo nodo azul para todas las transformaciones definidas en un archivo de configuración de conjunto de datos y un solo nodo verde para todas las dimensiones extendidas definidas en un archivo de configuración de conjunto de datos. Para obtener más información sobre esta opción de visualización, consulte [Trabajo con bloques de archivos](../../../../../home/c-get-started/c-admin-intrf/c-dataset-mgrs/c-dep-maps/c-wkg-file-blocks.md#concept-3652bbabfbd34449a5f842d8aa598efc).
