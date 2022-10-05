---
description: Después de crear y guardar los espacios de trabajo dentro de la carpeta del conjunto de informes, debe crear un nuevo archivo Report.cfg.
title: Configuración del conjunto de informes
uuid: 21f8dcde-8fe1-4ba0-9eb7-39ff812dcf14
exl-id: 780e6bb1-b332-4984-b132-df11d95b592a
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '223'
ht-degree: 4%

---

# Configuración del conjunto de informes{#configure-the-report-set}

{{eol}}

Después de crear y guardar los espacios de trabajo dentro de la carpeta del conjunto de informes, debe crear un nuevo archivo Report.cfg.

Debe especificar en la variable [!DNL Report.cfg] para el conjunto de informes cuándo y cómo se generarán y distribuirán los informes.

**Para crear un nuevo Report.cfg**

1. En Data Workbench, abra la variable [!DNL Profile Manager] haciendo clic con el botón derecho en un espacio de trabajo y haciendo clic en **[!UICONTROL Admin]** > **[!UICONTROL Profile]** > **[!UICONTROL Profile Manager]**.
1. Haga clic en **[!UICONTROL Reports]** para abrir el [!DNL Reports] carpeta.
1. Haga clic en la carpeta del conjunto de informes.
1. En el [!DNL User] para la carpeta del conjunto de informes, haga clic con el botón derecho y seleccione **[!UICONTROL Create]** > **[!UICONTROL Report]**. Un nuevo [!DNL Report.cfg] El archivo aparece en la sección [!DNL File]para abrir el Navegador.
1. En el [!DNL User] para la nueva columna [!DNL Report.cfg] , haga clic con el botón derecho en la marca de verificación de [!DNL Report.cfg] y, a continuación, haga clic en **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**.

   ![Información sobre los pasos](assets/cfg_reportcfg.png)

1. Edite los parámetros de configuración como desee. Para obtener información sobre estos parámetros, consulte [Parámetros de Report.cfg](../../../../../home/c-rpt-oview/c-rpt-param-ref/c-rpt-param.md#concept-838e59d72d3f4cb29ee15f5c7eb0ceff).

   >[!NOTE]
   >
   >El ejemplo [!DNL Report.cfg] que se muestra en este ejemplo contiene solo los parámetros incluidos en la variable [!DNL Report.cfg] de forma predeterminada. Si necesita agregar parámetros adicionales a una [!DNL Report.cfg] , debe hacerlo con un editor de texto. Para ver los pasos necesarios para ello, consulte [Edición de archivos de Report.cfg existentes](../../../../../home/c-rpt-oview/c-work-rpt-sets/c-edit-ex-rpt-files/c-edit-ex-rpt-files.md#concept-96fd57159f454defa09bd18655a12887).

1. Guarde el archivo haciendo clic con el botón derecho **[!UICONTROL Report.cfg (modified)]** en la parte superior del archivo y haga clic en **[!UICONTROL Save as Reports\]***&lt; **[!UICONTROL ReportSetName]**>***[!UICONTROL \Report.cfg]**.
1. Cierre el archivo.
1. En el [!DNL Profile Manager], haga clic con el botón derecho en la marca de verificación de la [!DNL User] para la nueva columna [!DNL Report.cfg] y seleccione **[!UICONTROL Save to]***&lt; **[!UICONTROL profile name]**>*.
