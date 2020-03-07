---
description: Pasos para registrar y ejecutar el servidor de informes.
solution: Analytics
title: Registro del servidor de informes como servicio de Windows
topic: Data workbench
uuid: 01fc0bbf-9f4a-487e-b1cb-16bf6974a541
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Registro del servidor de informes como servicio de Windows{#registering-report-server-as-a-windows-service}

Pasos para registrar y ejecutar el servidor de informes.

Antes de realizar este procedimiento, identifique la cuenta de Windows en la que se ejecutará el [!DNL Report Server] servicio. Asegúrese de que esta cuenta tenga los permisos adecuados para acceder a la ubicación en la que se almacenan los informes generados (es decir, no utilice el [!DNL Local System Account]).

Utilice el procedimiento siguiente para iniciar [!DNL Report Server]. Cuando se inicia [!DNL Report Server] por primera vez, automáticamente se registra como un servicio de Windows.

Cuando se inicia [!DNL Report Server] por primera vez, se conecta automáticamente al servidor de licencias de Adobe para registrar el certificado digital. Para completar el proceso de registro correctamente, el equipo debe estar conectado a Internet cuando ejecute los siguientes pasos.

1. En Windows, desplácese al directorio donde instaló [!DNL Report Server].

   Ejemplo: D:\Adobe\Report

1. Double-click **[!UICONTROL ReportServer.exe]**.
1. Para confirmar que [!DNL Report Server] se está ejecutando correctamente, haga clic en **[!UICONTROL Start]** > **[!UICONTROL Control Panel]** > **[!UICONTROL Administrative Tools]** > **[!UICONTROL Services]**. Esta secuencia de comandos puede variar en función de la versión de Windows que utilice.
1. En la lista de servicios, busque la entrada para [!DNL Report Server] y confirme que su estado es Iniciado y que su tipo de inicio es Automático.
1. Realice lo siguiente para especificar la cuenta de usuario en la que [!DNL Report Server] se ejecutará:

   1. Haga doble clic **[!UICONTROL Report Server]** para abrir la [!DNL Properties] ventana.

   1. Seleccione la **[!UICONTROL Log On]** ficha.
   1. Seleccione el botón de **[!UICONTROL This account]** radio.
   1. Escriba o busque el nombre de la cuenta. Esta cuenta debe tener permiso para acceder a la ubicación donde se almacenan los informes generados.

      >[!NOTE]
      >
      >Si [!DNL Report Server] distribuye informes como archivos de Microsoft Excel ( [!DNL .xls] o [!DNL .xlsx]), asegúrese de que la cuenta también tenga permiso para ejecutar Microsoft Excel.

   1. Introduzca y confirme la contraseña de la cuenta.
   1. Haga clic en **[!UICONTROL OK]**.

1. Haga clic con el botón secundario en el [!DNL Report Server] servicio y seleccione **[!UICONTROL Restart]** reiniciar el servicio en la cuenta especificada.
1. Para comprobar si [!DNL Report Server] se han producido errores durante el inicio, haga clic en **[!UICONTROL Start]** > **[!UICONTROL Control Panel]** > **[!UICONTROL Administrative Tools]** > **[!UICONTROL Event Viewer]**. Esta secuencia de comandos puede variar en función de la versión de Windows que utilice.

   1. En el panel izquierdo de la [!DNL Event Viewer] ventana, seleccione el registro Aplicaciones.
   1. En el panel derecho, busque eventos con Adobe en la [!DNL Source] columna.
   1. Si encuentra un error de Adobe, haga doble clic en el error para mostrar la [!DNL Event Properties] ventana. Esta ventana proporciona información detallada sobre el error.

      >[!NOTE]
      >
      >Una vez que se inicia el [!DNL Report Server] servicio, el archivo [!DNL ReportServer.log] se crea en el [!DNL Trace] directorio del servidor de informes. Este archivo también es útil para solucionar problemas con [!DNL Report Server].

Ha completado la instalación de [!DNL Report Server]. [!DNL Report Server] está diseñado para ejecutarse de forma continua. Si reinicia el equipo, [!DNL Report Server] se reinicia automáticamente. Si necesita iniciar y detener [!DNL Report Server] manualmente, puede hacerlo mediante el panel de [!DNL Services] control de Windows.
