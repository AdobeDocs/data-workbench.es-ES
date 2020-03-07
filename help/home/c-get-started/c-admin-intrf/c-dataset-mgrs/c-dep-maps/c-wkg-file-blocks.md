---
description: Cuando se muestran componentes de conjuntos de datos en un mapa de dependencias, tiene la opción de habilitar la opción de visualización Incluir bloques de archivos.
solution: Analytics
title: Bloques de archivos
topic: Data workbench
uuid: 079dccba-ef19-4895-90bb-6c56f26e8beb
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Bloques de archivos{#file-blocks}

Cuando se muestran componentes de conjuntos de datos en un mapa de dependencias, tiene la opción de habilitar la opción de visualización Incluir bloques de archivos.

Cuando esta opción está habilitada, el mapa muestra un solo nodo azul para todas las transformaciones definidas en un archivo de configuración de conjunto de datos y un solo nodo verde para todas las dimensiones extendidas definidas en un archivo de configuración de conjunto de datos. Por ejemplo, si un [!DNL log processing dataset include] archivo incluye las definiciones de tres transformaciones, el mapa muestra un nodo azul que representa las tres transformaciones. Del mismo modo, si un [!DNL transformation dataset include] archivo incluye las definiciones de dos dimensiones extendidas, el mapa muestra un nodo verde que representa las dos dimensiones extendidas.

## Bloques de transformación {#section-c442730394264a0b850792a32eaaa2da}

Cada nodo azul es un bloque de transformación y tiene las siguientes opciones:

* Para ver los campos de entrada del bloque de transformación, haga clic con el botón derecho en el nodo del bloque y haga clic en **[!UICONTROL Inputs]**.
* Para ver los campos de salida del bloque de transformación, haga clic con el botón derecho en el nodo del bloque y haga clic en **[!UICONTROL Outputs]**.
* Para editar cualquiera de las transformaciones del bloque, haga clic con el botón derecho en el nodo del bloque y haga clic en **[!UICONTROL Edit Configuration]**. La llamada que se muestra contiene todo el archivo de configuración en el que se definen todas las transformaciones. A continuación, puede editar los parámetros como desee. Para obtener más información sobre estos parámetros, consulte la Guía *de configuración de* Dataset.

* Para ver todas las transformaciones en el bloque, haga clic con el botón secundario en el nodo del bloque de transformación y haga clic en **[!UICONTROL Show Details]**. La llamada que se muestra contiene otro mapa de dependencia que muestra los nodos de todas las transformaciones del bloque.

## Bloques de dimensión {#section-0dd581ac6dfc4153bee5300b3cfae2a0}

Cada nodo verde es un bloque de dimensión y tiene las siguientes opciones:

* Para ver los campos de entrada o la dimensión principal del bloque de dimensión, haga clic con el botón derecho en el nodo del bloque y haga clic en **[!UICONTROL Inputs]**.
* Para ver las dimensiones de salida del bloque de dimensiones, haga clic con el botón derecho en el nodo del bloque y haga clic en **[!UICONTROL Outputs]**.

