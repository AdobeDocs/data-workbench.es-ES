---
description: Para detectar los errores del sistema y de la aplicación lo antes posible y solucionarlos antes de que causen problemas o interrupciones importantes, debe supervisar regularmente los registros de eventos.
title: Supervisión de eventos para detectar errores
uuid: 09bb34db-e24d-4bc5-84d2-7fc37df60681
exl-id: 88f48594-5c73-4ae3-8014-b8543e689426
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '148'
ht-degree: 6%

---

# Supervisión de eventos para detectar errores{#monitoring-events-for-errors}

{{eol}}

Para detectar los errores del sistema y de la aplicación lo antes posible y solucionarlos antes de que causen problemas o interrupciones importantes, debe supervisar regularmente los registros de eventos.

**Frecuencia recomendada:** Cada 5-10 minutos

Para monitorizar los productos de software del servidor de Adobe, se puede configurar la herramienta de administración automatizada para que supervise el registro de eventos en busca de errores con el &quot;Adobe&quot; de origen y, a continuación, avise al personal adecuado de los problemas que puedan requerir intervención.

En Windows, los mensajes de error de la aplicación se envían al Registro de sucesos de la aplicación en Windows, al que se puede acceder mediante el Visor de sucesos de Windows. En Unix, los mensajes de error de la aplicación se envían al syslog de Unix utilizando la función LOG_DAEMON.

**Para abrir el Visor de eventos de Windows**

* Haga clic **[!UICONTROL Start]** > **[!UICONTROL Control Panel]** > **[!UICONTROL Administrative Tools]** > **[!UICONTROL Event Viewer]**.
