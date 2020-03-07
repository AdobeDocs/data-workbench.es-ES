---
description: Información sobre la actualización y desinstalación del software del servidor de informes.
solution: Analytics
title: Actualización y desinstalación del servidor de informes
topic: Data workbench
uuid: 42f0d190-1a88-424d-be4b-90338144d287
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Actualización y desinstalación del servidor de informes{#upgrading-and-uninstalling-report-server}

Información sobre la actualización y desinstalación del software del servidor de informes.

* [Actualizando informe](../../../home/c-rpt-oview/c-inst-rpt/c-upgrade-uninstall-rpt.md#section-95fea4bddad74616a8aea450dcdb2282)
* [Desinstalando informe](../../../home/c-rpt-oview/c-inst-rpt/c-upgrade-uninstall-rpt.md#section-96eb3281c45a45c0a7065deaa6845c25)

## Actualización del servidor de informes {#section-95fea4bddad74616a8aea450dcdb2282}

Si está actualizando a [!DNL Report Server] 5.4, puede utilizar las instrucciones para actualizar su [!DNL Report Server] software. Si utiliza [!DNL Report Server] 3.6 o una versión anterior, póngase en contacto con Adobe para obtener ayuda con la actualización.

Para actualizar [!DNL Report Server] 5.4, utilice el área de trabajo de datos para copiar un archivo de actualización en el servidor del área de trabajo de datos al que se [!DNL Report Server] conecta. Después de hacerlo, [!DNL Report] las instancias del servidor se actualizan automáticamente cuando se conectan a ese servidor y cargan un perfil.

>[!NOTE]
>
>Antes de realizar la actualización [!DNL Report Server], asegúrese de haber actualizado correctamente el software del servidor del área de trabajo de datos, así como los perfiles que se ejecutan en el servidor del área de trabajo de datos. Para obtener más información, póngase en contacto con los servicios de consultoría de Adobe.

Para realizar el siguiente procedimiento, primero debe obtener el archivo de actualización para [!DNL Report Server].

**Para actualizar a la versión[!DNL Report Server]5.4 y versiones posteriores**

1. Realice una copia de seguridad de todos los archivos que se encuentran debajo [!DNL E:\Portal] y elimine todos los archivos y carpetas de este directorio.
1. Copy the contents of the new build into [!DNL E:\Portal].
1. Modifique [!DNL global.asa][!DNL email.asp]y [!DNL TopNavigation.xml] según las instrucciones de la sección anterior.

1. Copie el [!DNL users.mdb] de la copia de seguridad.

   >[!NOTE]
   >
   >Si anteriormente no generaba informes con una salida .png, debe ir a las carpetas de informes individuales y modificar el informe [!DNL reports.xml] para incluir un formato de informe de png. De lo contrario, puede que reciba un error 500. El original [!DNL reports.xml] tendría el siguiente aspecto:

   ```
      <?xml version="1.0" encoding="UTF-8" standalone="no" ?>
   <REPORTS>
    <REPORT format="xls">
     <NAME>Dashboard</NAME>
     <PATH>Dashboard.xls</PATH>
     <WEB_PATH>Dashboard.xls</WEB_PATH>
    </REPORT>
   </REPORTS>
   ```

   Habría que modificarlo para que dijera lo siguiente:

   ```
   <?xml version="1.0" encoding="UTF-8" standalone="no" ?>
   <REPORTS>
    <REPORT format="xls">
     <NAME>Dashboard</NAME>
     <PATH>Dashboard.xls</PATH>
     <WEB_PATH>Dashboard.xls</WEB_PATH>
    </REPORT>
    <REPORT format="png">
    <NAME>Dashboard</NAME>
     <PATH>Dashboard.png</PATH>
     <WEB_PATH>Dashboard.png</WEB_PATH>
    </REPORT>
   </REPORTS>
   ```

1. En el [!DNL report.cfg], incluya un formato de salida de png y guarde. A partir de ahora, debe generar informes en formato png.

**Para actualizar a[!DNL Report Server]4.0**

1. En el equipo del área de trabajo de datos, copie el archivo de actualización del servidor de informes en la [!DNL Temp\Software] carpeta del directorio donde está instalado el área de trabajo de datos.
1. Inicie el área de trabajo de datos y cargue el [!DNL Configuration] perfil.
1. Haga clic en la **[!UICONTROL Configure Connection to Servers]** miniatura.
1. En la ventana [!DNL Servers Manager], haga clic con el botón derecho en el icono del servidor del área de trabajo de datos y haga clic en **[!UICONTROL Server Files]**.

1. En la carpeta Software, abra la [!DNL Report Server] carpeta.
1. Haga clic con el botón derecho en la **[!UICONTROL Temp]** marca de verificación [!DNL ReportServer.exe] y seleccione **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>*.

## Desinstalación del servidor de informes {#section-96eb3281c45a45c0a7065deaa6845c25}

**Para desinstalar[!DNL Report Server]**

1. Anule el registro del [!DNL Report Windows] servicio.

   1. Abra un símbolo del sistema y vaya al subdirectorio bin en la carpeta donde instaló el servidor del área de trabajo de datos (InsightServer64.exe). Ejemplo: [!DNL D:\Adobe\Report\bin]
   1. En el símbolo del sistema, ejecute el siguiente comando para detenerlo y anular el registro como un servicio en Microsoft Windows: [!DNL visualreport /unregserver]

1. Elimine el directorio de instalación del servidor de informes.

