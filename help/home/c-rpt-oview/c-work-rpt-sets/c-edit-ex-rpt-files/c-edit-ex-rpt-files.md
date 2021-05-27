---
description: Pasos para editar los archivos existentes de Report.cfg mediante el escritorio o un editor de texto.
title: Edición de archivos de Report.cfg existentes
uuid: 494b9eef-42f3-4ed9-8b43-f5c09af33f2e
exl-id: 69038c0c-bb01-4e61-aad6-1be0bdec8a6d
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '388'
ht-degree: 2%

---

# Edición de archivos de Report.cfg existentes{#editing-existing-report-cfg-files}

Pasos para editar los archivos existentes de Report.cfg mediante el escritorio o un editor de texto.

>[!NOTE]
>
>* Debe estar trabajando en línea para editar archivos [!DNL Report.cfg]. Para trabajar en línea, en [!DNL Worktop], haga clic con el botón derecho en la barra de título y haga clic en **[!UICONTROL Work Online]**.
   >
   >
* Si el parámetro **[!UICONTROL Allow Report Regeneration]** del archivo [!DNL Report.cfg] está establecido en [!DNL True], cuando realice cambios en ese archivo y lo guarde de nuevo en el servidor, [!DNL Report] vuelve a generar automáticamente los informes de ese conjunto. Aunque regenera los informes, no los vuelve a enviar por correo electrónico. Para ver los pasos a seguir, consulte [Reenvío de informes por correo electrónico](../../../../home/c-rpt-oview/c-work-rpt-sets/c-edit-ex-rpt-files/t-res-rpts-email.md#task-b0a21f1c925f4e5d82560581ae4cf607).

>



Puede editar un [!DNL Report.cfg] existente desde [!DNL Worktop] o utilizando un editor de texto.

La edición de un archivo [!DNL Report.cfg] mediante la pestaña [!DNL Reports] de [!DNL Worktop] permite editar solo los parámetros, vectores y elementos vectoriales que ya existen en el archivo. Si necesita añadir un parámetro o un vector al archivo, debe editarlo mediante un editor de texto, como el Bloc de notas.

* [Para editar un Report.cfg existente mediante el escritorio de trabajo](../../../../home/c-rpt-oview/c-work-rpt-sets/c-edit-ex-rpt-files/c-edit-ex-rpt-files.md#section-7bce3bca006149c79be7678430f21945)
* [Para editar un Report.cfg existente con un editor de texto](../../../../home/c-rpt-oview/c-work-rpt-sets/c-edit-ex-rpt-files/c-edit-ex-rpt-files.md#section-06f3d2a8d7f34bc2841180caf10a1eb7)

## Para editar un Report.cfg existente mediante el escritorio {#section-7bce3bca006149c79be7678430f21945}

>[!NOTE]
>
>Debe estar trabajando en línea para editar el [!DNL Report.cfg] desde el [!DNL Worktop].

1. En Data Workbench, en la ficha [!DNL Reports], seleccione la subcarpeta (pestaña o subdirectorio desplegable) del conjunto de informes que desea configurar.
1. Haga clic en **[!UICONTROL Report.cfg]**. Se muestran los parámetros de [!DNL Report.cfg] para este conjunto de informes.

1. Edite los parámetros de configuración como desee. Para obtener información sobre estos parámetros, consulte [Parámetros de Report.cfg](../../../../home/c-rpt-oview/c-rpt-param-ref/c-rpt-param.md#concept-838e59d72d3f4cb29ee15f5c7eb0ceff).
1. Guarde el archivo haciendo clic con el botón derecho en **[!UICONTROL Report.cfg (modified)]** en la parte superior de los parámetros y haciendo clic en **[!UICONTROL Save to]***&lt; **[!UICONTROL server location]**>*.

## Para editar un Report.cfg existente con un editor de texto {#section-06f3d2a8d7f34bc2841180caf10a1eb7}

1. Abra [!DNL Reports Manager] haciendo clic con el botón derecho en un espacio de trabajo y haciendo clic en **[!UICONTROL Admin]** > **[!UICONTROL Profile]** > **[!UICONTROL Reports Manager]**.

1. Haga clic en la carpeta del conjunto de informes.
1. Haga clic con el botón derecho en la marca de verificación situada junto a [!DNL Report.cfg] para este conjunto de informes y haga clic en **[!UICONTROL Make Local]**.

1. En la columna [!DNL User], haga clic con el botón derecho en la marca de verificación situada junto a [!DNL Report.cfg] para este conjunto de informes y haga clic en **[!UICONTROL Open]** > **[!UICONTROL in Notepad]**. Se abre el archivo [!DNL Report.cfg].

   El ejemplo [!DNL Report.cfg] mostrado en [Configurar el conjunto de informes](../../../../home/c-rpt-oview/c-work-rpt-sets/t-create-rpt-set/t-config-rpt-set/t-config-rpt-set.md#task-cfb2fd0c28bc48c2acdd582fe0d670d0) contiene únicamente los parámetros incluidos en el archivo [!DNL Report.cfg] de forma predeterminada. El siguiente ejemplo incluye todos los parámetros disponibles para el archivo [!DNL Report.cfg] que puede utilizar como modelos para sus entradas de parámetro:

   ```
   Attachments = vector: 1 items
     0 = Attachment:
       FileName = string: c:\\myimage.jpg
       Content Type = string: image/jpeg
   Alert Threshold = int: 0
   Allow Report Regeneration = bool: true
   Color Set = int: 1
   Command To Execute = string: 
   Default Excel Template = string: 
   Dimension Name = string: 
   Email Only If Perfect = bool: false
   End Date = string: 
   Every = string: month
   Excel Watchdog Timeout (seconds) = double: 300.0
   Filter Formula = string: 
   Gamma Correction = double: 1
   Hide Logos = bool: false
   Lookup File = string: 
   Mail Report = MailReport: 
     Body XSL Template = string: 
     Recipients = vector: 0 items
     SMTP Server = SmtpServerInfo: 
       Address = string: 
       Password = string: 
       User = string: 
     Sender Address = string: 
     Sender Name = string: 
     Subject = string: 
   Notification Only = bool: false
   Output Root = string: 
   Report Types = vector: 3 items
     0 = string: thumbnail
     1 = string: png
     2 = string: excel
   Start Date = string: 7/1/06 19:16 EDT
   Thumbnail X = int: 240
   Thumbnail Y = int: 180
   Top N Metric = string: 
   Top N Value = int: 0
   Use Local Sample Only = bool: false
   Workspace Path = string: 
   ```

1. Edite los parámetros de configuración como desee. Para obtener información sobre estos parámetros, consulte [Parámetros de Report.cfg](../../../../home/c-rpt-oview/c-rpt-param-ref/c-rpt-param.md#concept-838e59d72d3f4cb29ee15f5c7eb0ceff).
1. Guarde y cierre el archivo.
1. En [!DNL Reports Manager], haga clic con el botón derecho en la marca de verificación de la columna [!DNL User] del archivo [!DNL Report.cfg] y seleccione **[!UICONTROL Save to]***&lt; **[!UICONTROL profile name]**>*.
