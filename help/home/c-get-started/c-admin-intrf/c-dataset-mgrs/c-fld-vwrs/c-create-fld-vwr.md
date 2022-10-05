---
description: Puede abrir un visualizador de campos como una llamada desde un mapa de dependencias o como una visualización independiente desde el menú Administración.
title: Creación de un visor de campos
uuid: df48e728-96f9-4432-82c8-f8047840ffb9
exl-id: a2563dbb-1d1f-4ed8-b73b-6ac7a2687405
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '346'
ht-degree: 2%

---

# Creación de un visor de campos{#create-a-field-viewer}

{{eol}}

Puede abrir un visualizador de campos como una llamada desde un mapa de dependencias o como una visualización independiente desde el menú Administración.

## Creación de un visor de campos a partir de un mapa de dependencias {#section-040cb83c902b49c48b841d35abc127e5}

Al abrir un visor de campos desde un mapa de dependencias (como se muestra en [Apertura de visualizadores de campo](../../../../../home/c-get-started/c-admin-intrf/c-dataset-mgrs/c-dep-maps/c-opn-field-vwrs.md#concept-0f0738ac50804a33818487222c337c27)), el visor se rellena automáticamente en función del origen del registro, la transformación o la dimensión en la que se haga clic con el botón derecho. Para un origen de registro o una transformación, los campos del visor son entradas o salidas del origen de registro o transformación. Para una dimensión, los campos son entradas de la dimensión. Puede agregar y quitar campos como desee.

## Creación de visualizadores de campo como visualización independiente {#section-11d10e46631d4fdca45d7534336e1e80}

Al abrir un visor de campos como visualización independiente, puede crear una [!DNL Log Processing Field Viewer] o [!DNL Transformation Field Viewer]. El visor está en blanco y debe añadir los campos deseados al visor. Para un [!DNL Log Processing Field Viewer], puede agregar campos desde la [!DNL Log Processing.cfg] archivo o [!DNL Log Processing dataset include] archivo. Para un [!DNL Transformation Field Viewer], puede agregar campos desde la [!DNL Transformation.cfg] archivo o [!DNL Transformation dataset include] archivo.

Para obtener más información sobre la configuración y los archivos de inclusión, consulte la *Guía de configuración de conjuntos de datos*.

## Adición y eliminación de un campo {#section-9c0d4f5735a044a8b21dc7a99c63a59a}

**Adición de un campo a un visor de campos**

* Haga clic con el botón derecho en el visor de campos y haga clic en **[!UICONTROL Fields]** > *&lt;**[!UICONTROL field name]**>* > *&lt;**[!UICONTROL instance]**>*.

   -o-

* Haga clic con el botón derecho en una columna existente en el visualizador de campos y haga clic en **[!UICONTROL Fields]** > *&lt;**[!UICONTROL field name]**>* > *&lt;**[!UICONTROL instance]**>*.

El nombre del campo hace referencia al nombre del campo y la instancia hace referencia a dónde en la configuración del conjunto de datos se utiliza el campo, como una etapa de procesamiento del conjunto de datos o una transformación. Algunos campos se utilizan en varios lugares dentro de la configuración del conjunto de datos (por ejemplo, un campo se puede modificar mediante varias transformaciones), por lo que debe seleccionar qué instancia del campo desea agregar al visor de campos.

En la lista de campos disponibles, aparece una X a la izquierda de cualquier campo ya mostrado en el visor.

**Eliminación de un campo de un visor de campos**

* Haga clic con el botón derecho en la columna del campo que desee eliminar y haga clic en **[!UICONTROL Remove Field]**.
