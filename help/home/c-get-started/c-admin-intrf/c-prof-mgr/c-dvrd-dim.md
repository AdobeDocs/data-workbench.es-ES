---
description: Las nuevas dimensiones que se crean con el Área de trabajo de datos (denominadas dimensiones derivadas) son dimensiones del lado del cliente.
solution: Analytics
title: Trabajar con dimensiones derivadas
topic: Data workbench
uuid: 3a955fdc-6666-40ab-aee0-bd23c260c009
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Trabajar con dimensiones derivadas{#work-with-derived-dimensions}

Las nuevas dimensiones que se crean con el Área de trabajo de datos (denominadas dimensiones derivadas) son dimensiones del lado del cliente.

En lugar de definir estas dimensiones durante el proceso de construcción y actualización del conjunto de datos (en el [!DNL Transformation.cfg] archivo) en los equipos del servidor del Área de trabajo de datos, las dimensiones derivadas se crean y almacenan individualmente como [!DNL .dim] archivos en un perfil. Como resultado, puede cambiar las dimensiones existentes y crear nuevas dimensiones derivadas sin reprocesar el conjunto de datos.

>[!NOTE]
>
>Para obtener más información sobre las dimensiones que la que se proporciona en esta sección, consulte la guía de la aplicación correspondiente del área de trabajo de datos.

Para obtener más información sobre el proceso de configuración y actualización del conjunto de datos, consulte la Guía *de configuración del* conjunto de datos.

## Crear dimensiones derivadas {#section-fd9b6ca13a8f4aa9bbc2fff3ef15cb76}

Para crear una dimensión derivada, puede copiar y modificar una dimensión existente o guardar una dimensión de una visualización.

## Crear dimensiones derivadas a partir de una dimensión existente {#section-f46c2d3ab0a5416c98d6e79d18d99fa1}

Los usuarios generalmente desean crear nuevas dimensiones de tiempo a partir de las existentes. Por ejemplo, puede crear una nueva dimensión &quot;Últimos 5 días&quot; a partir de la dimensión &quot;Últimos 7 días&quot; existente.

1. En la [!DNL Profile Manager], en la columna Nombre *del* perfil, haga clic con el botón secundario en la marca de verificación de una dimensión similar a la dimensión que desee crear y haga clic en **[!UICONTROL Copy]**.

   Por ejemplo, para copiar el archivo [!DNL Last 7 Days.dim] de la carpeta Informes del [!DNL Traffic] perfil, haga clic con el botón secundario en la marca de verificación del nombre del archivo en la [!DNL Traffic] columna y haga clic en **[!UICONTROL Copy]**.

   ![](assets/vis_ProfMgr_CopyDimension.png)

1. Haga clic con el botón secundario en la columna de la carpeta en la que desea almacenar la dimensión copiada y haga clic en [!DNL User] **[!UICONTROL Paste]**.

   La dimensión aparece en la carpeta Dimensiones seleccionada con una marca de verificación en la [!DNL User] columna.

1. Para cambiar el nombre de la nueva dimensión, haga clic con el botón derecho en su marca de verificación en la [!DNL User] columna y escriba el nuevo nombre en el [!DNL File] campo.
1. En el menú que aparece al hacer clic con el botón derecho, haga clic en **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**. Aparecerán los parámetros de definición de la dimensión.
1. Modifique los parámetros según sea necesario para definir la nueva dimensión.

   Para las dimensiones de tiempo, lo más probable es que tenga que modificar solo los parámetros Count y Range.

1. Para guardar el archivo, haga clic con el botón derecho del ratón **[!UICONTROL (modified)]** en la parte superior de la ventana y haga clic en **[!UICONTROL Save]**.

   Si desea que todos los usuarios de un perfil utilicen la dimensión que ha creado, debe cargarla en el perfil mediante el [!DNL Profile Manager]. Para obtener más información, consulte [Publicación de archivos en el perfil](../../../../home/c-get-started/c-admin-intrf/c-prof-mgr/t-pub-files-wkg-prof.md#task-a0106e010c834d16bd60eef4721b6af9)de trabajo.

Ahora puede utilizar la nueva dimensión en todo el perfil actual seleccionándola como lo haría con cualquier dimensión integrada.

## Guardar una dimensión desde una visualización {#section-84cfe5e9ccb640afa2ee4e2da2682757}

Puede guardar dimensiones extendidas de mapas de proceso y segmentos. Para ver los pasos para guardar una dimensión desde un mapa de proceso, consulte [Guardar dimensiones desde mapas](../../../../home/c-get-started/c-analysis-vis/c-proc-maps/t-dim-proc-maps.md#task-44d9e555d4a944e6aa81993eef703051)de proceso. Para ver los pasos para guardar una dimensión de segmento, consulte [Creación de dimensiones](../../../../home/c-get-started/c-analysis-vis/c-seg/c-create-seg-dim.md#concept-70b363edcad14185ba8051646ad3d44e) de segmento en la página 82.

## Guardar un segmento como dimensión {#section-7c443cf1ac5a44659623cabb9e0c1ab8}

También puede guardar los segmentos definidos como una dimensión. Para obtener más información, consulte [Reutilización de una visualización](../../../../home/c-get-started/c-analysis-vis/c-seg/c-reuse-seg-vis.md#concept-a8a607bd415d404a83c32a26b804cbdc)de segmentos.

## Editar una dimensión derivada existente {#section-3a82c604bf1c4d369770556d268808b2}

1. I

   En la [!DNL Profile Manager], en la columna *del nombre* del perfil, haga clic con el botón secundario en la marca de verificación del archivo de dimensión que desee editar y haga clic en **[!UICONTROL Make Local]**.
1. Haga clic con el botón secundario en la marca de verificación del archivo de dimensión en la [!DNL User] columna y haga clic en **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**.
1. Complete los parámetros según sea necesario. Para obtener más información, póngase en contacto con los servicios de consultoría de Adobe.
1. Para guardar el archivo, haga clic con el botón derecho del ratón **[!UICONTROL (modified)]** en la parte superior de la ventana y haga clic en **[!UICONTROL Save]**.

   Si desea que todos los usuarios de un perfil utilicen la dimensión modificada, debe cargarla en el perfil mediante el [!DNL Profile Manager]. Para obtener más información, consulte [Publicación de archivos en el perfil](../../../../home/c-get-started/c-admin-intrf/c-prof-mgr/t-pub-files-wkg-prof.md#task-a0106e010c834d16bd60eef4721b6af9)de trabajo.

