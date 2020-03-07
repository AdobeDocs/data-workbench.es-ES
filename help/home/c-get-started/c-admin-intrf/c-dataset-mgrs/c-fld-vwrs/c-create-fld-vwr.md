---
description: Puede abrir un visor de campos como una llamada desde un mapa de dependencias o como una visualización independiente desde el menú Administración.
solution: Analytics
title: Creación de un visor de campos
topic: Data workbench
uuid: df48e728-96f9-4432-82c8-f8047840ffb9
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Creación de un visor de campos{#create-a-field-viewer}

Puede abrir un visor de campos como una llamada desde un mapa de dependencias o como una visualización independiente desde el menú Administración.

## Creación de un visor de campos a partir de un mapa de dependencias {#section-040cb83c902b49c48b841d35abc127e5}

Cuando se abre un visor de campos desde un mapa de dependencias (como se muestra en [Abrir visores](../../../../../home/c-get-started/c-admin-intrf/c-dataset-mgrs/c-dep-maps/c-opn-field-vwrs.md#concept-0f0738ac50804a33818487222c337c27)de campos), el visor se rellena automáticamente en función del origen de registro, la transformación o la dimensión en la que se hace clic con el botón derecho. Para un origen de registro o una transformación, los campos del visor son entradas o salidas del origen de registro o transformación. Para una dimensión, los campos son entradas de la dimensión. Puede agregar y quitar campos como desee.

## Creación de visores de campo como visualización independiente {#section-11d10e46631d4fdca45d7534336e1e80}

Al abrir un visor de campos como visualización independiente, puede crear una [!DNL Log Processing Field Viewer] o una [!DNL Transformation Field Viewer]. El visor está en blanco y debe agregar los campos deseados al visor. Para un [!DNL Log Processing Field Viewer], puede agregar campos del [!DNL Log Processing.cfg] archivo o de cualquier [!DNL Log Processing dataset include] archivo. Para un [!DNL Transformation Field Viewer], puede agregar campos del [!DNL Transformation.cfg] archivo o de cualquier [!DNL Transformation dataset include] archivo.

Para obtener más información sobre la configuración y los archivos de inclusión, consulte la Guía *de configuración de* Dataset.

## Agregar y quitar un campo {#section-9c0d4f5735a044a8b21dc7a99c63a59a}

**Adición de un campo a un visor de campos**

* Haga clic con el botón derecho en el visor del campo y haga clic en **[!UICONTROL Fields]** > *&lt;**[!UICONTROL field name]**>* > *&lt;**[!UICONTROL instance]**>*.

   -O bien-

* Haga clic con el botón secundario en una columna existente en el visor de campos y haga clic en **[!UICONTROL Fields]** > *&lt;**[!UICONTROL field name]**>* > *&lt;**[!UICONTROL instance]**>*.

El nombre del campo hace referencia al nombre del campo y la instancia hace referencia a dónde se utiliza el campo en la configuración del conjunto de datos, como una etapa de procesamiento del conjunto de datos o una transformación. Algunos campos se utilizan en varios lugares dentro de la configuración del conjunto de datos (por ejemplo, un campo puede modificarse mediante varias transformaciones), por lo que debe seleccionar qué instancia del campo desea agregar al visor del campo.

En la lista de campos disponibles, aparece una X a la izquierda de cualquier campo ya mostrado en el visor.

**Quitar un campo de un visor de campos**

* Haga clic con el botón secundario en la columna del campo que desee eliminar y haga clic en **[!UICONTROL Remove Field]**.

