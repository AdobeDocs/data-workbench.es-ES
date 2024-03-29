---
description: Pasos para asignar el portal de informes a un directorio virtual (IIS 6.0).
title: Asignación del portal de informes a un directorio virtual (IIS 6.0)
uuid: e09d23d7-09de-4180-8260-60527f47aa98
exl-id: 39335705-7391-49af-a63d-c0fe4ca3f8f0
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '546'
ht-degree: 3%

---

# Asignación del portal de informes a un directorio virtual (IIS 6.0){#mapping-report-portal-to-a-virtual-directory-iis}

{{eol}}

Pasos para asignar el portal de informes a un directorio virtual (IIS 6.0).

Asignación de [!DNL Report Portal] a un directorio virtual en IIS 6.0 implica tres tareas independientes:

1. [Editar el archivo de configuración](../../../../home/c-rpt-oview/c-install-rpt-port/c-virtual-dir/c-map-rpt-port-vdir-6.md#section-eaf1c58935074cfa840dac33e1286520)
1. [Importar el archivo de configuración en IIS](../../../../home/c-rpt-oview/c-install-rpt-port/c-virtual-dir/c-map-rpt-port-vdir-6.md#section-9d61f6bfa93846dcb96973fec5573b19)
1. [Habilitar páginas Active Server (ASP) en IIS](../../../../home/c-rpt-oview/c-install-rpt-port/c-virtual-dir/c-map-rpt-port-vdir-6.md#section-a7725ec2afc64ffc854c5bd8c5c31802)

Debe completar las tres tareas.

## Para editar el archivo de configuración {#section-eaf1c58935074cfa840dac33e1286520}

1. En la máquina donde [!DNL Report Portal] está instalado, abra \*PortalName*\ReportPortalSetup.xml en un editor de texto como Notepad.

1. Utilice la función de búsqueda y reemplazo del editor para reemplazar globalmente (Reemplazar todo) la cadena &quot;VSVirtualPortalName&quot; por el nombre de su portal. Por ejemplo, si desea usar &quot;VisualReportPortal&quot; como nombre de su [!DNL Report Portal], buscaría &quot;VSVirtualPortalName&quot; y lo reemplazaría por &quot;VisualReportPortal&quot;.
1. Busque el siguiente elemento en este archivo:

   ```
   <IIsWebVirtualDir Location= "/LM/W3SVC/1/Root/PortalName/Output" AccessFlags="AccessRead | AccessScript” AppFriendlyName="Output" . . . >
   ```

1. Establezca el [!DNL Path] a la ubicación física del directorio en el que [!DNL Report Server] guarda el resultado de los conjuntos de informes.

   La carpeta de salida se puede ubicar en cualquier lugar, se le puede dar un nombre y contiene una subcarpeta para cada conjunto de informes.

   >[!NOTE]
   >
   >Debe ser el mismo directorio que especifique en el parámetro Raíz de salida en la variable [!DNL Report.cfg] para un conjunto de informes. Para obtener más información, consulte [Configuración de los archivos de Report.cfg](../../../../home/c-rpt-oview/c-admin-rpt/c-config-rpt-files.md#concept-cf4b95344fcb4c8c877db91e5f1d345d).

   El siguiente ejemplo de código muestra cómo se configuraría la variable [!DNL Path] si los informes se han guardado en [!DNL E:\VSReport\ReportOutput]:

   ```
   < . . . 
   AppIsolated="2" 
       AppRoot="/LM/W3SVC/1/Root/PortalName/OutputFolder" 
       DirBrowseFlags="DirBrowseShowDate | DirBrowseShowTime |...  
       Path="E:\VSReport\ReportOutput"
   ```

   >[!NOTE]
   >
   >Es fundamental que [!DNL Path] se ha configurado correctamente.

1. Si ha cambiado el valor predeterminado [!DNL Path] del [!DNL Output] elemento, mueva el [!DNL profiles.xml] del *\PortalName*\PortalFiles\Output folder al directorio de salida especificado en el paso 4. En el ejemplo anterior, se movería [!DNL profiles.xml] a [!DNL E:\VSReport\ReportOutput].

1. Compruebe que la variable [!DNL Path] atributos para todos los demás [!DNL IIsWebVirtualDir] los elementos se asignan a la ubicación correcta buscando todas las instancias de [!DNL C:\Inetpub\wwwroot] y reemplazando cada uno por la ruta correcta.

1. Guarde el archivo. Si desea conservar el archivo original, puede guardar el archivo de configuración con un nombre nuevo.

## Para importar el archivo de configuración en IIS {#section-9d61f6bfa93846dcb96973fec5573b19}

1. En la máquina donde [!DNL Report Portal] está instalado, inicie el Administrador de IIS usando **[!UICONTROL Start]** > **[!UICONTROL Administrative Tools]** > **[!UICONTROL Internet Information Systems (IIS) Manager]**.

1. Seleccione **[!UICONTROL (local computer)]** > **[!UICONTROL Web Sites]** > **[!UICONTROL Default Web Site]**.

1. Clic con el botón derecho **[!UICONTROL Default Web Site]** y seleccione **[!UICONTROL New]** > **[!UICONTROL Virtual Directory]** (del archivo ).

1. Seleccione el **[!UICONTROL ReportPortalSetup.xml]** y haga clic en **[!UICONTROL Read File]**.

1. Compruebe que hay seis directorios virtuales enumerados para su [!DNL Report Portal] como se muestra en el siguiente ejemplo.

   ![](assets/rptPort_dia_VirDirs.png)

   Si no ve seis directorios virtuales o si recibe un mensaje de error, haga clic en **[!UICONTROL Cancel]** y examine el archivo de configuración en busca de errores.

1. Seleccione el primer directorio virtual de la lista (el que es el principal de los otros cinco) y haga clic en **[!UICONTROL OK]**. IIS importa las asignaciones y agrega los directorios virtuales al sitio web predeterminado.

   Asegúrese de que la estructura de directorio resultante tenga una carpeta principal (con el mismo nombre que su portal) y cinco subdirectorios como se muestra en el siguiente ejemplo.

   ![](assets/rptPort_scrn_VirDirs_Installed.png)

1. Haga clic en cada directorio virtual para asegurarse de que IIS pueda localizar el directorio físico que representa. Si IIS muestra un error, haga clic con el botón secundario en el nombre del directorio virtual y verifique que la variable [!DNL Local Path] El campo apunta al directorio físico correcto.

## Para habilitar páginas Active Server (ASP) en IIS {#section-a7725ec2afc64ffc854c5bd8c5c31802}

Para usar [!DNL Report Portal], los ASP deben estar habilitados en IIS. (De forma predeterminada, los ASP están deshabilitados cuando IIS 6.0 está instalado). Utilice el siguiente procedimiento para comprobar que los ASP están habilitados en su IIS.

1. En la ventana Administrador de IIS, seleccione **[!UICONTROL (local computer)]** > **[!UICONTROL Web Service Extensions]**.
1. Compruebe que la variable [!DNL Active Server Pages] la extensión está configurada en [!DNL Allowed].

   ![](assets/report_aspenable.png)

1. Si su estado está prohibido, seleccione **[!UICONTROL Active Server Pages]** y haga clic en **[!UICONTROL Allow]**.
1. Cierre el Administrador de IIS.
