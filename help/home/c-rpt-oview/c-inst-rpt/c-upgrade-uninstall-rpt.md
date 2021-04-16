---
description: Información sobre la actualización y desinstalación del software de Report Server.
title: Actualización y desinstalación del servidor de informes
uuid: 42f0d190-1a88-424d-be4b-90338144d287
exl-id: 86d0d848-4e2a-45cb-a1b3-b8a856332d33
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '377'
ht-degree: 2%

---

# Actualización y desinstalación del servidor de informes{#upgrading-and-uninstalling-report-server}

Información sobre la actualización y desinstalación del software de Report Server.

* [Actualización del informe](../../../home/c-rpt-oview/c-inst-rpt/c-upgrade-uninstall-rpt.md#section-95fea4bddad74616a8aea450dcdb2282)
* [Desinstalación del informe](../../../home/c-rpt-oview/c-inst-rpt/c-upgrade-uninstall-rpt.md#section-96eb3281c45a45c0a7065deaa6845c25)

## Actualización del servidor de informes {#section-95fea4bddad74616a8aea450dcdb2282}

Si está actualizando a [!DNL Report Server] 5.4, puede utilizar las instrucciones para actualizar su software [!DNL Report Server]. Si utiliza [!DNL Report Server] 3.6 o una versión anterior, póngase en contacto con el Adobe para obtener ayuda con la actualización.

Para actualizar [!DNL Report Server] 5.4, utilice Data Workbench para copiar un archivo de actualización en el servidor de Data Workbench al que [!DNL Report Server] se conecta. Después de hacerlo, las instancias de [!DNL Report] Server se actualizan automáticamente cuando se conectan a ese servidor y cargan un perfil.

>[!NOTE]
>
>Antes de actualizar [!DNL Report Server], asegúrese de haber actualizado correctamente el software del servidor de Data Workbench, así como los perfiles que se ejecutan en el servidor de Data Workbench. Para obtener más información, póngase en contacto con los servicios de consultoría de Adobe.

Para realizar el siguiente procedimiento, primero debe obtener el archivo de actualización para [!DNL Report Server].

**Para actualizar a la versión  [!DNL Report Server] 5.4 y versiones posteriores**

1. Haga una copia de seguridad de todos los archivos de [!DNL E:\Portal] y elimine todos los archivos y carpetas de este directorio.
1. Copie el contenido de la nueva compilación en [!DNL E:\Portal].
1. Modifique [!DNL global.asa], [!DNL email.asp] y [!DNL TopNavigation.xml] según las instrucciones de la sección anterior.

1. Copie el [!DNL users.mdb] de la copia de seguridad.

   >[!NOTE]
   >
   >Si anteriormente no generaba informes con un resultado .png , debe ir a las carpetas de informes individuales y modificar el [!DNL reports.xml] para incluir un formato de informe de png. De lo contrario, puede obtener un error 500. Su [!DNL reports.xml] original tendría un aspecto similar al siguiente:

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

   Habría que modificarlo de la siguiente manera:

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

1. En [!DNL report.cfg], incluya un formato de salida png y guarde. En adelante, debería generar informes en formato png.

**Para actualizar a  [!DNL Report Server] 4.0**

1. En el equipo de Data Workbench, copie el archivo de actualización de Report Server a la carpeta [!DNL Temp\Software] del directorio en el que está instalado Data Workbench.
1. Inicie Data Workbench y cargue el perfil [!DNL Configuration].
1. Haga clic en la miniatura **[!UICONTROL Configure Connection to Servers]**.
1. En [!DNL Servers Manager], haga clic con el botón derecho en el icono del servidor de Data Workbench y haga clic en **[!UICONTROL Server Files]**.

1. En la carpeta Software, abra la carpeta [!DNL Report Server].
1. Haga clic con el botón derecho en la marca de verificación **[!UICONTROL Temp]** para [!DNL ReportServer.exe] y seleccione **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>*.

## Desinstalación del servidor de informes {#section-96eb3281c45a45c0a7065deaa6845c25}

**Para desinstalar[!DNL Report Server]**

1. Anule el registro del servicio [!DNL Report Windows].

   1. Abra un símbolo del sistema y vaya al subdirectorio bin en la carpeta donde instaló el servidor de Data Workbench (InsightServer64.exe). Ejemplo: [!DNL D:\Adobe\Report\bin]
   1. En el símbolo del sistema, ejecute el siguiente comando para detenerlo y anular el registro como un servicio en Microsoft Windows: [!DNL visualreport /unregserver]

1. Elimine el directorio de instalación de Report Server.
