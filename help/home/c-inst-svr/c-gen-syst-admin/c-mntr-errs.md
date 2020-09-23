---
description: Para detectar los errores del sistema y de la aplicación lo antes posible y solucionarlos antes de que causen problemas o interrupciones importantes, debe supervisar regularmente los registros de eventos.
solution: Analytics
title: Supervisión de eventos para detectar errores
uuid: 09bb34db-e24d-4bc5-84d2-7fc37df60681
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '148'
ht-degree: 6%

---


# Supervisión de eventos para detectar errores{#monitoring-events-for-errors}

Para detectar los errores del sistema y de la aplicación lo antes posible y solucionarlos antes de que causen problemas o interrupciones importantes, debe supervisar regularmente los registros de eventos.

**Frecuencia recomendada:** Cada 5-10 minutos

Para monitorear los productos de software del servidor Adobe, se puede configurar la herramienta de administración automatizada para que supervise el registro de eventos en busca de errores con el &quot;Adobe&quot; de origen y, a continuación, avise al personal adecuado de los problemas que puedan requerir intervención.

En Windows, los mensajes de error de la aplicación se envían al registro de Evento de la aplicación en Windows, al que se puede acceder mediante el visor de Evento de Windows. En Unix, los mensajes de error de la aplicación se envían al syslog Unix mediante la función LOG_DAEMON.

**Para abrir el visor de Evento de Windows**

* Haga clic **[!UICONTROL Start]** > **[!UICONTROL Control Panel]** > **[!UICONTROL Administrative Tools]** > **[!UICONTROL Event Viewer]**.

