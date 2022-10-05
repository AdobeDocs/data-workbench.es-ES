---
description: Pasos para registrar y ejecutar el servidor de informes.
title: Registro del servidor de informes como servicio de Windows
uuid: 01fc0bbf-9f4a-487e-b1cb-16bf6974a541
exl-id: 46ea5dd4-7041-451e-91e5-f927873fc7d7
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '398'
ht-degree: 3%

---

# Registro del servidor de informes como servicio de Windows{#registering-report-server-as-a-windows-service}

{{eol}}

Pasos para registrar y ejecutar el servidor de informes.

Antes de realizar este procedimiento, identifique la cuenta de Windows en la que [!DNL Report Server] se ejecutará. Asegúrese de que esta cuenta tenga los permisos adecuados para acceder a la ubicación en la que se almacenan los informes generados (es decir, no use la variable [!DNL Local System Account]).

Utilice el procedimiento siguiente para empezar [!DNL Report Server]. Cuando se inicia [!DNL Report Server] por primera vez, se registra automáticamente como un servicio de Windows.

Cuando se inicia [!DNL Report Server] por primera vez, se conecta automáticamente al servidor de licencias de Adobe para registrar su certificado digital. Para completar el proceso de registro correctamente, el equipo debe estar conectado a Internet cuando ejecute los siguientes pasos.

1. En Windows, vaya al directorio donde instaló [!DNL Report Server].

   Ejemplo: D:\Adobe\Report

1. Hacer doble clic **[!UICONTROL ReportServer.exe]**.
1. Para confirmar que [!DNL Report Server] se está ejecutando correctamente, haga clic en **[!UICONTROL Start]** > **[!UICONTROL Control Panel]** > **[!UICONTROL Administrative Tools]** > **[!UICONTROL Services]**. Esta secuencia de comandos puede variar en función de la versión de Windows que utilice.
1. En la lista de servicios, busque la entrada para [!DNL Report Server] y confirme que su estado es Started y que su tipo de inicio es Automatic.
1. Haga lo siguiente para especificar la cuenta de usuario en la que [!DNL Report Server] se ejecutará:

   1. Hacer doble clic **[!UICONTROL Report Server]** para abrir el [!DNL Properties] ventana.

   1. Seleccione el **[!UICONTROL Log On]** pestaña .
   1. Seleccione el **[!UICONTROL This account]** botón de opción.
   1. Escriba o busque el nombre de la cuenta. Esta cuenta debe tener permiso para acceder a la ubicación donde se almacenan los informes generados.

      >[!NOTE]
      >
      >If [!DNL Report Server] distribuye informes como Microsoft Excel ( [!DNL .xls] o [!DNL .xlsx]), asegúrese de que la cuenta también tenga permiso para ejecutar Microsoft Excel.

   1. Introduzca y confirme la contraseña de la cuenta.
   1. Haga clic en **[!UICONTROL OK]**.

1. Haga clic con el botón derecho en el [!DNL Report Server] servicio y seleccione **[!UICONTROL Restart]** para reiniciar el servicio en la cuenta especificada.
1. Para comprobar si [!DNL Report Server] se han producido errores durante el inicio, haga clic en **[!UICONTROL Start]** > **[!UICONTROL Control Panel]** > **[!UICONTROL Administrative Tools]** > **[!UICONTROL Event Viewer]**. Esta secuencia de comandos puede variar en función de la versión de Windows que utilice.

   1. En el panel izquierdo del [!DNL Event Viewer] , seleccione el registro Aplicaciones .
   1. En el panel derecho, busque eventos con Adobe en el [!DNL Source] para abrir el Navegador.
   1. Si encuentra un error de Adobe, haga doble clic en el error para mostrar la variable [!DNL Event Properties] ventana. Esta ventana proporciona información detallada sobre el error.

      >[!NOTE]
      >
      >Después de la [!DNL Report Server] inicios del servicio, el archivo [!DNL ReportServer.log] se crea en el servidor de informes [!DNL Trace] directorio. Este archivo también es útil para solucionar problemas con [!DNL Report Server].

Ha completado la instalación de [!DNL Report Server]. [!DNL Report Server] está diseñado para ejecutarse de forma continua. Si reinicia el equipo, [!DNL Report Server] se reinicia automáticamente. Si necesita iniciar y detener [!DNL Report Server] manualmente, puede hacerlo usando la variable [!DNL Services] panel de control de Windows.
