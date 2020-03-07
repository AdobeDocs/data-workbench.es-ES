---
description: Pasos para editar los archivos Report.cfg existentes mediante Word o un editor de texto.
solution: Analytics
title: Edición de archivos de Report.cfg existentes
topic: Data workbench
uuid: 494b9eef-42f3-4ed9-8b43-f5c09af33f2e
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Edición de archivos de Report.cfg existentes{#editing-existing-report-cfg-files}

Pasos para editar los archivos Report.cfg existentes mediante Word o un editor de texto.

>[!NOTE]
>
>* Debe estar trabajando en línea para editar [!DNL Report.cfg] archivos. Para trabajar en línea, en la barra de título, haga clic con el botón derecho [!DNL Worktop]y haga clic en **[!UICONTROL Work Online]**.
   >
   >
* Si el **[!UICONTROL Allow Report Regeneration]** parámetro del [!DNL Report.cfg] archivo está establecido en [!DNL True], al realizar cambios en ese archivo y guardarlo de nuevo en el servidor, [!DNL Report] se vuelven a generar automáticamente los informes de ese conjunto. Aunque vuelve a generar los informes, no los vuelve a enviar por correo electrónico. Para ver los pasos a seguir, consulte [Reenvío de informes por correo electrónico](../../../../home/c-rpt-oview/c-work-rpt-sets/c-edit-ex-rpt-files/t-res-rpts-email.md#task-b0a21f1c925f4e5d82560581ae4cf607).
>



Puede editar una existente [!DNL Report.cfg] desde el [!DNL Worktop] o mediante un editor de texto.

La edición de un [!DNL Report.cfg] archivo mediante la [!DNL Reports] ficha de la [!DNL Worktop] permite editar solo los parámetros, vectores y elementos vectoriales que ya existen en el archivo. Si necesita agregar un parámetro o vector al archivo, debe editarlo con un editor de texto, como Bloc de notas.

* [Para editar un archivo Report.cfg existente mediante el escritorio](../../../../home/c-rpt-oview/c-work-rpt-sets/c-edit-ex-rpt-files/c-edit-ex-rpt-files.md#section-7bce3bca006149c79be7678430f21945)
* [Para editar un Report.cfg existente mediante un editor de texto](../../../../home/c-rpt-oview/c-work-rpt-sets/c-edit-ex-rpt-files/c-edit-ex-rpt-files.md#section-06f3d2a8d7f34bc2841180caf10a1eb7)

## Para editar un archivo Report.cfg existente mediante el escritorio {#section-7bce3bca006149c79be7678430f21945}

>[!NOTE]
>
>Debe estar trabajando en línea para editar el [!DNL Report.cfg] desde el [!DNL Worktop].

1. En el área de trabajo de datos, en la [!DNL Reports] ficha, seleccione la subcarpeta (ficha o subdirectorio desplegable) del conjunto de informes que desee configurar.
1. Haga clic en **[!UICONTROL Report.cfg]**. Se muestran los parámetros del [!DNL Report.cfg] conjunto de informes.

1. Edite los parámetros de configuración como desee. Para obtener información sobre estos parámetros, consulte Parámetros [de Report.cfg](../../../../home/c-rpt-oview/c-rpt-param-ref/c-rpt-param.md#concept-838e59d72d3f4cb29ee15f5c7eb0ceff).
1. Para guardar el archivo, haga clic con el botón derecho **[!UICONTROL Report.cfg (modified)]** en la parte superior de los parámetros y haga clic en **[!UICONTROL Save to]***&lt; **[!UICONTROL server location]**>*.

## Para editar un Report.cfg existente mediante un editor de texto {#section-06f3d2a8d7f34bc2841180caf10a1eb7}

1. Abra el [!DNL Reports Manager] haciendo clic con el botón secundario en un espacio de trabajo y haciendo clic en **[!UICONTROL Admin]** > **[!UICONTROL Profile]** > **[!UICONTROL Reports Manager]**.

1. Haga clic en la carpeta del conjunto de informes.
1. Haga clic con el botón secundario en la marca de verificación situada junto al [!DNL Report.cfg] para este conjunto de informes y haga clic en **[!UICONTROL Make Local]**.

1. En la [!DNL User] columna, haga clic con el botón secundario en la marca de verificación situada junto a [!DNL Report.cfg] para este conjunto de informes y haga clic en **[!UICONTROL Open]** > **[!UICONTROL in Notepad]**. Se abre el [!DNL Report.cfg] archivo.

   El ejemplo [!DNL Report.cfg] mostrado en [Configurar el conjunto](../../../../home/c-rpt-oview/c-work-rpt-sets/t-create-rpt-set/t-config-rpt-set/t-config-rpt-set.md#task-cfb2fd0c28bc48c2acdd582fe0d670d0) de informes contiene únicamente los parámetros incluidos en el [!DNL Report.cfg] archivo de forma predeterminada. El siguiente ejemplo incluye todos los parámetros disponibles para el [!DNL Report.cfg] archivo que puede utilizar como modelos para las entradas de parámetro:

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

1. Edite los parámetros de configuración como desee. Para obtener información sobre estos parámetros, consulte Parámetros [de Report.cfg](../../../../home/c-rpt-oview/c-rpt-param-ref/c-rpt-param.md#concept-838e59d72d3f4cb29ee15f5c7eb0ceff).
1. Guarde y cierre el archivo.
1. En la [!DNL Reports Manager], haga clic con el botón derecho en la marca de verificación de la [!DNL User] columna del [!DNL Report.cfg] archivo y seleccione **[!UICONTROL Save to]***&lt; **[!UICONTROL profile name]**>*.

