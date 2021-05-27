---
description: Las nuevas dimensiones que se crean mediante la Data Workbench (denominadas dimensiones derivadas) son dimensiones del lado del cliente.
title: Trabajo con dimensiones derivadas
uuid: 3a955fdc-6666-40ab-aee0-bd23c260c009
exl-id: 5b7e3a2a-ac61-4186-ad6c-234edf68af3e
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '562'
ht-degree: 1%

---

# Trabajo con dimensiones derivadas{#work-with-derived-dimensions}

Las nuevas dimensiones que se crean mediante la Data Workbench (denominadas dimensiones derivadas) son dimensiones del lado del cliente.

En lugar de definir estas dimensiones durante el proceso de construcción y actualización del conjunto de datos (en el archivo [!DNL Transformation.cfg]) en los equipos de servidor de Data Workbench, las dimensiones derivadas se crean y almacenan individualmente como [!DNL .dim] archivos en un perfil. Como resultado, puede cambiar las dimensiones existentes y crear nuevas dimensiones derivadas sin necesidad de reprocesar el conjunto de datos.

>[!NOTE]
>
>Para obtener más información sobre las dimensiones que la que se proporciona en esta sección, consulte la guía de aplicación de Data Workbench correspondiente.

Para obtener más información sobre el proceso de configuración y actualización del conjunto de datos, consulte la *Guía de configuración del conjunto de datos*.

## Crear dimensiones derivadas {#section-fd9b6ca13a8f4aa9bbc2fff3ef15cb76}

Para crear una dimensión derivada, puede copiar y modificar una dimensión existente o guardar una dimensión de una visualización.

## Crear dimensiones derivadas de una dimensión existente {#section-f46c2d3ab0a5416c98d6e79d18d99fa1}

Los usuarios suelen querer crear nuevas dimensiones temporales a partir de las existentes. Por ejemplo, puede crear una nueva dimensión &quot;Últimos 5 días&quot; a partir de la dimensión &quot;Últimos 7 días&quot; existente.

1. En [!DNL Profile Manager], en la columna *nombre del perfil*, haga clic con el botón derecho en la marca de verificación de una dimensión similar a la que desea crear y haga clic en **[!UICONTROL Copy]**.

   Por ejemplo, para copiar el [!DNL Last 7 Days.dim] de la carpeta Informes del perfil [!DNL Traffic], haga clic con el botón derecho en la marca de verificación del nombre del archivo en la columna [!DNL Traffic] y haga clic en **[!UICONTROL Copy]**.

   ![](assets/vis_ProfMgr_CopyDimension.png)

1. Haga clic con el botón derecho en la columna [!DNL User] de la carpeta en la que desea almacenar la dimensión copiada y haga clic en **[!UICONTROL Paste]**.

   La dimensión aparece en la carpeta de Dimension seleccionada con una marca de verificación en la columna [!DNL User].

1. Para cambiar el nombre de la nueva dimensión, haga clic con el botón derecho en su marca de verificación en la columna [!DNL User] y escriba el nuevo nombre en el campo [!DNL File].
1. En el menú que aparece al hacer clic con el botón derecho, haga clic en **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**. Se muestran los parámetros de definición de la dimensión.
1. Modifique los parámetros según sea necesario para definir la nueva dimensión.

   Para las dimensiones temporales, lo más probable es que necesite modificar solo los parámetros Count y Range .

1. Para guardar el archivo, haga clic con el botón derecho en **[!UICONTROL (modified)]** en la parte superior de la ventana y haga clic en **[!UICONTROL Save]**.

   Si desea que todos los usuarios de un perfil utilicen la dimensión que ha creado, debe cargarla en el perfil mediante [!DNL Profile Manager]. Para obtener más información, consulte [Publicación de archivos en su perfil de trabajo](../../../../home/c-get-started/c-admin-intrf/c-prof-mgr/t-pub-files-wkg-prof.md#task-a0106e010c834d16bd60eef4721b6af9).

Ahora puede utilizar la nueva dimensión en todo el perfil actual seleccionándola como lo haría con cualquier dimensión integrada.

## Guardar una dimensión desde una visualización {#section-84cfe5e9ccb640afa2ee4e2da2682757}

Puede guardar dimensiones extendidas de mapas de procesos y segmentos. Para ver los pasos para guardar una dimensión de un mapa de procesos, consulte [Guardar Dimension de mapas de procesos](../../../../home/c-get-started/c-analysis-vis/c-proc-maps/t-dim-proc-maps.md#task-44d9e555d4a944e6aa81993eef703051). Para ver los pasos para guardar una dimensión de segmento, consulte [Creación de Dimension de segmento](../../../../home/c-get-started/c-analysis-vis/c-seg/c-create-seg-dim.md#concept-70b363edcad14185ba8051646ad3d44e) en la página 82.

## Guardar un segmento como dimensión {#section-7c443cf1ac5a44659623cabb9e0c1ab8}

También puede guardar segmentos definidos como dimensiones. Para ver los pasos, consulte [Reutilización de una visualización de segmentos](../../../../home/c-get-started/c-analysis-vis/c-seg/c-reuse-seg-vis.md#concept-a8a607bd415d404a83c32a26b804cbdc).

## Editar una dimensión derivada existente {#section-3a82c604bf1c4d369770556d268808b2}

1. I

   En [!DNL Profile Manager], en la columna *nombre del perfil*, haga clic con el botón derecho en la marca de verificación del archivo de dimensión que desee editar y haga clic en **[!UICONTROL Make Local]**.
1. Haga clic con el botón derecho en la marca de verificación del archivo de dimensión en la columna [!DNL User] y haga clic en **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**.
1. Complete los parámetros según sea necesario. Para obtener más información, póngase en contacto con los servicios de consultoría de Adobe.
1. Para guardar el archivo, haga clic con el botón derecho en **[!UICONTROL (modified)]** en la parte superior de la ventana y haga clic en **[!UICONTROL Save]**.

   Si desea que todos los usuarios de un perfil utilicen la dimensión modificada, debe cargarla en el perfil mediante [!DNL Profile Manager]. Para obtener más información, consulte [Publicación de archivos en su perfil de trabajo](../../../../home/c-get-started/c-admin-intrf/c-prof-mgr/t-pub-files-wkg-prof.md#task-a0106e010c834d16bd60eef4721b6af9).
