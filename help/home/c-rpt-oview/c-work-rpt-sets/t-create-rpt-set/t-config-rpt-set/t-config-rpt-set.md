---
description: Después de crear y guardar los espacios de trabajo dentro de la carpeta del conjunto de informes, debe crear un nuevo archivo Report.cfg.
title: Configuración del conjunto de informes
uuid: 21f8dcde-8fe1-4ba0-9eb7-39ff812dcf14
exl-id: 780e6bb1-b332-4984-b132-df11d95b592a
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '223'
ht-degree: 4%

---

# Configuración del conjunto de informes{#configure-the-report-set}

Después de crear y guardar los espacios de trabajo dentro de la carpeta del conjunto de informes, debe crear un nuevo archivo Report.cfg.

Debe especificar en el archivo [!DNL Report.cfg] del conjunto de informes cuándo y cómo se generarán y distribuirán los informes.

**Para crear un nuevo Report.cfg**

1. En Data Workbench, abra [!DNL Profile Manager] haciendo clic con el botón derecho en un espacio de trabajo y haciendo clic en **[!UICONTROL Admin]** > **[!UICONTROL Profile]** > **[!UICONTROL Profile Manager]**.
1. Haga clic en **[!UICONTROL Reports]** para abrir la carpeta [!DNL Reports].
1. Haga clic en la carpeta del conjunto de informes.
1. En la columna [!DNL User] de la carpeta del conjunto de informes, haga clic con el botón derecho y seleccione **[!UICONTROL Create]** > **[!UICONTROL Report]**. Aparece un nuevo archivo [!DNL Report.cfg] en la columna [!DNL File].
1. En la columna [!DNL User] del nuevo archivo [!DNL Report.cfg], haga clic con el botón derecho en la marca de verificación del archivo [!DNL Report.cfg] y, a continuación, haga clic en **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**.

   ![Información sobre los pasos](assets/cfg_reportcfg.png)

1. Edite los parámetros de configuración como desee. Para obtener información sobre estos parámetros, consulte [Parámetros de Report.cfg](../../../../../home/c-rpt-oview/c-rpt-param-ref/c-rpt-param.md#concept-838e59d72d3f4cb29ee15f5c7eb0ceff).

   >[!NOTE]
   >
   >El ejemplo [!DNL Report.cfg] mostrado en este ejemplo contiene solo los parámetros incluidos en el archivo [!DNL Report.cfg] de forma predeterminada. Si necesita agregar parámetros adicionales a un archivo [!DNL Report.cfg], debe hacerlo usando un editor de texto. Para ver los pasos a seguir, consulte [Edición de archivos existentes de Report.cfg](../../../../../home/c-rpt-oview/c-work-rpt-sets/c-edit-ex-rpt-files/c-edit-ex-rpt-files.md#concept-96fd57159f454defa09bd18655a12887).

1. Guarde el archivo haciendo clic con el botón derecho **[!UICONTROL Report.cfg (modified)]** en la parte superior del archivo y haciendo clic en **[!UICONTROL Save as Reports\]***&lt; **[!UICONTROL ReportSetName]**>***[!UICONTROL \Report.cfg]**.
1. Cierre el archivo.
1. En [!DNL Profile Manager], haga clic con el botón derecho en la marca de verificación de la columna [!DNL User] del nuevo archivo [!DNL Report.cfg] y seleccione **[!UICONTROL Save to]***&lt; **[!UICONTROL profile name]**>*.
