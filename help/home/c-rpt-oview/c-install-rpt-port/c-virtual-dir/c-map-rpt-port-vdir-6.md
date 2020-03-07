---
description: Pasos para asignar el portal de informes a un directorio virtual (IIS 6.0).
solution: Analytics
title: Asignación del portal de informes a un directorio virtual (IIS 6.0)
topic: Data workbench
uuid: e09d23d7-09de-4180-8260-60527f47aa98
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Asignación del portal de informes a un directorio virtual (IIS 6.0){#mapping-report-portal-to-a-virtual-directory-iis}

Pasos para asignar el portal de informes a un directorio virtual (IIS 6.0).

La asignación de [!DNL Report Portal] un directorio virtual en IIS 6.0 implica tres tareas independientes:

1. [Editar el archivo de configuración](../../../../home/c-rpt-oview/c-install-rpt-port/c-virtual-dir/c-map-rpt-port-vdir-6.md#section-eaf1c58935074cfa840dac33e1286520)
1. [Importar el archivo de configuración en IIS](../../../../home/c-rpt-oview/c-install-rpt-port/c-virtual-dir/c-map-rpt-port-vdir-6.md#section-9d61f6bfa93846dcb96973fec5573b19)
1. [Habilitar páginas Active Server (ASP) en IIS](../../../../home/c-rpt-oview/c-install-rpt-port/c-virtual-dir/c-map-rpt-port-vdir-6.md#section-a7725ec2afc64ffc854c5bd8c5c31802)

Debe completar las tres tareas.

## To Edit the Configuration File {#section-eaf1c58935074cfa840dac33e1286520}

1. En el equipo donde [!DNL Report Portal] está instalado, abra \*PortalName*\ReportPortalSetup.xml en un editor de texto como Notepad.

1. Utilice la función de buscar y reemplazar del editor para reemplazar globalmente (Reemplazar todo) la cadena &quot;VirtualPortalName&quot; por el nombre de su portal. Por ejemplo: si desea utilizar &quot;VisualReportPortal&quot; como nombre del [!DNL Report Portal], buscaría &quot;VisualReportPortalName&quot; y lo reemplazaría por &quot;VisualReportPortal&quot;.
1. Busque el siguiente elemento en este archivo:

   ```
   <IIsWebVirtualDir Location= "/LM/W3SVC/1/Root/PortalName/Output" AccessFlags="AccessRead | AccessScript” AppFriendlyName="Output" . . . >
   ```

1. Establezca el atributo de este elemento en la ubicación física del directorio en el que [!DNL Path] [!DNL Report Server] se guarda el resultado de los conjuntos de informes.

   La carpeta de salida se puede ubicar en cualquier lugar, se le puede dar un nombre y contiene una subcarpeta para cada conjunto de informes.

   >[!NOTE]
   >
   >Debe ser el mismo directorio que especifique en el parámetro Raíz de salida del [!DNL Report.cfg] archivo para un conjunto de informes. Para obtener más información, consulte [Configuración de archivos](../../../../home/c-rpt-oview/c-admin-rpt/c-config-rpt-files.md#concept-cf4b95344fcb4c8c877db91e5f1d345d)Report.cfg.

   El siguiente ejemplo de código muestra cómo se configuraría el [!DNL Path] atributo si los informes se guardasen en [!DNL E:\VSReport\ReportOutput]:

   ```
   < . . . 
   AppIsolated="2" 
       AppRoot="/LM/W3SVC/1/Root/PortalName/OutputFolder" 
       DirBrowseFlags="DirBrowseShowDate | DirBrowseShowTime |...  
       Path="E:\VSReport\ReportOutput"
   ```

   >[!NOTE]
   >
   >Es fundamental que el [!DNL Path] atributo esté configurado correctamente.

1. Si ha cambiado el valor predeterminado [!DNL Path] del [!DNL Output] elemento, mueva el [!DNL profiles.xml] archivo de la carpeta *\PortalName*\PortalFiles\Output folder to the output directory that you specified in Step 4. En el ejemplo anterior, se movería [!DNL profiles.xml] a [!DNL E:\VSReport\ReportOutput].

1. Compruebe que los [!DNL Path] atributos de todos los demás [!DNL IIsWebVirtualDir] elementos están asignados a la ubicación correcta buscando todas las instancias de [!DNL C:\Inetpub\wwwroot] y reemplazando cada una por la ruta correcta.

1. Guarde el archivo. Si desea conservar el archivo original, puede guardar el archivo de configuración con un nombre nuevo.

## Importar el archivo de configuración en IIS {#section-9d61f6bfa93846dcb96973fec5573b19}

1. En el equipo en el que [!DNL Report Portal] está instalado, inicie el Administrador de IIS con **[!UICONTROL Start]** > **[!UICONTROL Administrative Tools]** > **[!UICONTROL Internet Information Systems (IIS) Manager]**.

1. Select **[!UICONTROL (local computer)]** > **[!UICONTROL Web Sites]** > **[!UICONTROL Default Web Site]**.

1. Haga clic con el botón derecho **[!UICONTROL Default Web Site]** y seleccione **[!UICONTROL New]** > **[!UICONTROL Virtual Directory]** (del archivo).

1. Seleccione el **[!UICONTROL ReportPortalSetup.xml]** archivo y haga clic en **[!UICONTROL Read File]**.

1. Verifique que se incluyan seis directorios virtuales para su empresa [!DNL Report Portal] , como se muestra en el siguiente ejemplo.

   ![](assets/rptPort_dia_VirDirs.png)

   Si no ve seis directorios virtuales o si recibe un mensaje de error, haga clic en **[!UICONTROL Cancel]** y examine el archivo de configuración para ver si hay errores.

1. Seleccione el primer directorio virtual de la lista (el directorio principal de los otros cinco) y haga clic en **[!UICONTROL OK]**. IIS importa las asignaciones y agrega los directorios virtuales al sitio Web predeterminado.

   Asegúrese de que la estructura de directorio resultante tiene una carpeta principal (con el mismo nombre que el portal) y cinco subdirectorios, como se muestra en el siguiente ejemplo.

   ![](assets/rptPort_scrn_VirDirs_Installed.png)

1. Haga clic en cada directorio virtual para asegurarse de que IIS puede localizar el directorio físico que representa. Si IIS muestra un error, haga clic con el botón secundario en el nombre del directorio virtual y compruebe que el [!DNL Local Path] campo apunta al directorio físico correcto.

## Para habilitar las páginas Active Server (ASP) en IIS {#section-a7725ec2afc64ffc854c5bd8c5c31802}

Para usar [!DNL Report Portal], los ASP deben estar activados en IIS. (De forma predeterminada, los ASP están desactivados cuando se instala IIS 6.0). Utilice el siguiente procedimiento para comprobar que los ASP están activados en su IIS.

1. En la ventana Administrador de IIS, seleccione **[!UICONTROL (local computer)]** > **[!UICONTROL Web Service Extensions]**.
1. Compruebe que la [!DNL Active Server Pages] extensión está configurada en [!DNL Allowed].

   ![](assets/report_aspenable.png)

1. Si su estado está prohibido, seleccione **[!UICONTROL Active Server Pages]** y haga clic en **[!UICONTROL Allow]**.
1. Cierre el Administrador de IIS.

