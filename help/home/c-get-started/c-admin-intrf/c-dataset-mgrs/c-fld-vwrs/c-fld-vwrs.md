---
description: Un visor de campos es una tabla que contiene los valores de uno o varios campos de datos.
title: Visor de campos
uuid: 1227b0de-6ae8-4f97-ad3e-5c9ead818ba5
exl-id: 53ede4aa-4865-4e67-b3b1-e3e6287f29d7
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '279'
ht-degree: 1%

---

# Visor de campos{#field-viewer}

{{eol}}

Un visor de campos es una tabla que contiene los valores de uno o varios campos de datos.

Los campos cuyos valores se muestran son entradas o salidas de las fuentes de registro, transformaciones o dimensiones extendidas de un conjunto de datos. El nombre del campo se muestra en el encabezado de la columna y cada fila contiene el valor del campo para una sola fila de datos de origen. Dado que los visualizadores de campo permiten ver los valores de un campo, son útiles para escribir y probar [expresiones regulares](../../../../../home/c-dataset-const-proc/c-reg-exp.md#concept-070077baa419475094ef0469e92c5b9c).

Puede abrir un visualizador de campos como una llamada desde un [!DNL Transformation Dependency] mapa o como visualización independiente desde el [!DNL Admin] menú:

* Creación de un visor de campos a partir de un [!DNL Transformation Dependency] mapa. Al abrir un visor de campos desde un [!DNL Transformation Dependency] , el visor se rellena automáticamente en función del origen del registro, la transformación o la dimensión en la que se haga clic con el botón derecho. Para un origen de registro o una transformación, los campos del visor son entradas o salidas del origen de registro o transformación. Para una dimensión, los campos son entradas de la dimensión. Puede agregar y quitar campos como desee.

* Creación de un visor de campos como visualización independiente. Al abrir un visor de campos como visualización independiente, puede crear una [!DNL Log Processing Field Viewer] o [!DNL Transformation Field Viewer]. El visor está en blanco y debe añadir los campos deseados al visor. Para un [!DNL Log Processing Field Viewer], puede agregar campos desde la [!DNL Log Processing.cfg] archivo o [!DNL Log Processing Dataset Include] archivo. Para un [!DNL Transformation Field Viewer], puede agregar campos desde la [!DNL Transformation.cfg] archivo o [!DNL Transformation Dataset Include] archivo.

![](assets/vis_FieldViewer_OneField.png)

>[!NOTE]
>
>Los visualizadores de campo no son visualizaciones de tabla; por lo tanto, no tienen las propiedades asociadas a las tablas.

Para obtener información sobre cómo agregar y quitar campos y filtrar dentro de un visualizador de campos, consulte [Interfaces administrativas](../../../../../home/c-get-started/c-admin-intrf/c-admin-intrf.md#concept-855c1a91e1a948969fab592adca15f74).
