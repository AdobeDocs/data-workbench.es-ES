---
description: Pasos para registrar y ejecutar el servidor de informes.
title: Registro del servidor de informes como servicio de Windows
uuid: 01fc0bbf-9f4a-487e-b1cb-16bf6974a541
exl-id: 46ea5dd4-7041-451e-91e5-f927873fc7d7
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '398'
ht-degree: 3%

---

# Registro del servidor de informes como servicio de Windows{#registering-report-server-as-a-windows-service}

Pasos para registrar y ejecutar el servidor de informes.

Antes de realizar este procedimiento, identifique la cuenta de Windows en la que se ejecutará el servicio [!DNL Report Server]. Asegúrese de que esta cuenta tenga los permisos adecuados para acceder a la ubicación en la que se almacenan los informes generados (es decir, no utilice [!DNL Local System Account]).

Utilice el procedimiento siguiente para iniciar [!DNL Report Server]. Cuando inicia [!DNL Report Server] por primera vez, se registra automáticamente como un servicio de Windows.

Cuando inicia [!DNL Report Server] por primera vez, se conecta automáticamente al servidor de licencias de Adobe para registrar el certificado digital. Para completar el proceso de registro correctamente, el equipo debe estar conectado a Internet cuando ejecute los siguientes pasos.

1. En Windows, vaya al directorio donde instaló [!DNL Report Server].

   Ejemplo: D:\Adobe\Report

1. Haga doble clic en **[!UICONTROL ReportServer.exe]**.
1. Para confirmar que [!DNL Report Server] se está ejecutando correctamente, haga clic en **[!UICONTROL Start]** > **[!UICONTROL Control Panel]** > **[!UICONTROL Administrative Tools]** > **[!UICONTROL Services]**. Esta secuencia de comandos puede variar en función de la versión de Windows que utilice.
1. En la lista de servicios, busque la entrada para [!DNL Report Server] y confirme que su estado es Started y que su tipo de inicio es Automatic.
1. Haga lo siguiente para especificar la cuenta de usuario en la que se ejecutará [!DNL Report Server]:

   1. Haga doble clic en **[!UICONTROL Report Server]** para abrir la ventana [!DNL Properties].

   1. Seleccione la pestaña **[!UICONTROL Log On]**.
   1. Seleccione el botón de opción **[!UICONTROL This account]**.
   1. Escriba o busque el nombre de la cuenta. Esta cuenta debe tener permiso para acceder a la ubicación donde se almacenan los informes generados.

      >[!NOTE]
      >
      >Si [!DNL Report Server] distribuye los informes como archivos de Microsoft Excel ( [!DNL .xls] o [!DNL .xlsx]), asegúrese de que la cuenta también tenga permiso para ejecutar Microsoft Excel.

   1. Introduzca y confirme la contraseña de la cuenta.
   1. Haga clic en **[!UICONTROL OK]**.

1. Haga clic con el botón derecho en el servicio [!DNL Report Server] y seleccione **[!UICONTROL Restart]** para reiniciar el servicio en la cuenta especificada.
1. Para comprobar si [!DNL Report Server] experimentó algún error durante el inicio, haga clic en **[!UICONTROL Start]** > **[!UICONTROL Control Panel]** > **[!UICONTROL Administrative Tools]** > **[!UICONTROL Event Viewer]**. Esta secuencia de comandos puede variar en función de la versión de Windows que utilice.

   1. En el panel izquierdo de la ventana [!DNL Event Viewer] , seleccione el registro Aplicaciones .
   1. En el panel derecho, busque eventos con Adobe en la columna [!DNL Source] .
   1. Si encuentra un error de Adobe, haga doble clic en el error para mostrar la ventana [!DNL Event Properties]. Esta ventana proporciona información detallada sobre el error.

      >[!NOTE]
      >
      >Una vez que se inicie el servicio [!DNL Report Server], el archivo [!DNL ReportServer.log] se creará en el directorio [!DNL Trace] del servidor de informes. Este archivo también es útil para solucionar problemas con [!DNL Report Server].

Ha completado la instalación de [!DNL Report Server]. [!DNL Report Server] está diseñado para ejecutarse de forma continua. Si reinicia el equipo, [!DNL Report Server] se reinicia automáticamente. Si necesita iniciar y detener [!DNL Report Server] manualmente, puede hacerlo usando el panel de control [!DNL Services] en Windows.
