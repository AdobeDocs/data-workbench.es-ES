---
description: Después de crear y guardar las áreas de trabajo dentro de la carpeta del conjunto de informes, debe crear un nuevo archivo Report.cfg.
solution: Analytics
title: Configuración del conjunto de informes
topic: Data workbench
uuid: 21f8dcde-8fe1-4ba0-9eb7-39ff812dcf14
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Configuración del conjunto de informes{#configure-the-report-set}

Después de crear y guardar las áreas de trabajo dentro de la carpeta del conjunto de informes, debe crear un nuevo archivo Report.cfg.

Debe especificar en el [!DNL Report.cfg] archivo del conjunto de informes cuándo y cómo se generarán y distribuirán los informes.

**Para crear un nuevo informe.cfg**

1. En el área de trabajo de datos, abra la [!DNL Profile Manager] haciendo clic con el botón derecho en un área de trabajo y haciendo clic en **[!UICONTROL Admin]** > **[!UICONTROL Profile]** > **[!UICONTROL Profile Manager]**.
1. Haga clic en **[!UICONTROL Reports]** para abrir la [!DNL Reports] carpeta.
1. Haga clic en la carpeta del conjunto de informes.
1. En la [!DNL User] columna de la carpeta del conjunto de informes, haga clic con el botón derecho y seleccione **[!UICONTROL Create]** > **[!UICONTROL Report]**. Aparece un nuevo [!DNL Report.cfg] archivo en la [!DNL File]columna.
1. En la [!DNL User] columna del nuevo [!DNL Report.cfg] archivo, haga clic con el botón secundario en la marca de verificación del [!DNL Report.cfg] archivo y, a continuación, haga clic en **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**.

   ![Información sobre los pasos](assets/cfg_reportcfg.png)

1. Edite los parámetros de configuración como desee. Para obtener información sobre estos parámetros, consulte Parámetros [de Report.cfg](../../../../../home/c-rpt-oview/c-rpt-param-ref/c-rpt-param.md#concept-838e59d72d3f4cb29ee15f5c7eb0ceff).

   >[!NOTE]
   >
   >El ejemplo [!DNL Report.cfg] que se muestra en este ejemplo contiene únicamente los parámetros incluidos en el [!DNL Report.cfg] archivo de forma predeterminada. Si necesita agregar parámetros adicionales a un [!DNL Report.cfg] archivo, debe hacerlo con un editor de texto. Para ver los pasos a seguir, consulte [Edición de archivos](../../../../../home/c-rpt-oview/c-work-rpt-sets/c-edit-ex-rpt-files/c-edit-ex-rpt-files.md#concept-96fd57159f454defa09bd18655a12887)Report.cfg existentes.

1. Guarde el archivo haciendo clic con el botón derecho **[!UICONTROL Report.cfg (modified)]** en la parte superior del archivo y haciendo clic en **[!UICONTROL Guardar como informes\]***&lt;**[!UICONTROL ReportSetName]**>***[!UICONTROL \Report.cfg]**.
1. Cierre el archivo.
1. En la [!DNL Profile Manager], haga clic con el botón derecho en la marca de verificación de la [!DNL User] columna del nuevo [!DNL Report.cfg] archivo y seleccione **[!UICONTROL Save to]***&lt; **[!UICONTROL profile name]**>*.
