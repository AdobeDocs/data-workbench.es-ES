---
description: Antes de poder generar informes y alertas, debe configurar el servidor de informes para especificar la dirección del servidor de Insight e identificar los perfiles con los que desea que informe.
solution: Analytics
title: Configuración de la conexión con el servidor de Insight
topic: Data workbench
uuid: 2018b67e-90a6-41d7-b628-4b463869df6e
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Configuración de la conexión con el servidor de Insight{#configuring-the-connection-to-the-insight-server}

Antes de poder generar informes y alertas, debe configurar el servidor de informes para especificar la dirección del servidor de Insight e identificar los perfiles con los que desea que informe.

>[!NOTE]
>
>Hasta que configure el servidor de informes como se describe a continuación, no podrá ejecutar el servidor de informes correctamente. Si intenta ejecutar el servidor de informes con el archivo no configurado que está instalado con el programa, el servidor de informes genera un flujo de errores.

**Para configurar el servidor de informes**

1. Con el Explorador de Windows, navegue al directorio donde instaló el Servidor de informes.
1. Abra el [!DNL ReportServer.cfg] archivo en el Bloc de notas y modifíquelo como desee.

   El ejemplo siguiente [!DNL Report Server.cfg] contiene únicamente los parámetros incluidos en el [!DNL Report Server.cfg] archivo de forma predeterminada (y resalta la configuración de parámetro requerida). Si se pone en contacto con el servidor de licencias de Adobe a través de un servidor proxy, deberá agregar el vector de licencias y sus parámetros. Consulte Parámetros [de Report Server.cfg](../../../home/c-rpt-oview/c-rpt-param-ref/c-rpt-svr-param.md#concept-53359b328fd140d593c3f2fc0031be06) para obtener una descripción detallada.

   ```
   Fonts = vector: 0 items
   Gamma = float: 1.6
   Network Location = string: NetworkLocationName
   Servers = vector: 1 items
     0 = serverInfo:
       Address = string: ServerIPAddress
       Name = string: 
       Port = int: 443
       Proxy Address = string:
       Proxy Password = string:
       Proxy Port = int: 8080
       Proxy User Name = string:
       SSL Client Certificate = string: ReportCertFileName.pem
       SSL Server Common Name = string: ServerCommonName
       Use SSL = bool: true
   Result Memory Limit (KB) = double: 100000
   Maximum Slice Size = int: 30
   Use OpenGL Hardware Rendering = bool: true
   Reporting = :
     Profiles = vector: 1 items
       0 = ReportProfile:
         Server = string: ServerCommonName
         Profile = string: ProfileName
     Update Interval (minutes) = int: 10
     Completion Message Interval (seconds) = int: 600
     Status interval (seconds) = int: 600
     SMTP Server for Errors = string: SMTPServerHostName
     SMTP Server for Errors Username = string: SMTPServerUsername
     SMTP Server for Errors Password = string: SMTPServerPassword
     SMTP Server for Errors Send From = string: SenderAddress
     SMTP Server for Errors Send To = string: RecipientAddresses
   ```

1. Guarde y cierre el archivo.
