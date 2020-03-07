---
description: Para detectar los errores del sistema y de la aplicación lo antes posible y solucionarlos antes de que produzcan problemas o interrupciones importantes, debe supervisar regularmente los registros de eventos.
solution: Insight
title: Monitoreo de eventos para detectar errores
uuid: 09bb34db-e24d-4bc5-84d2-7fc37df60681
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Monitoreo de eventos para detectar errores{#monitoring-events-for-errors}

Para detectar los errores del sistema y de la aplicación lo antes posible y solucionarlos antes de que produzcan problemas o interrupciones importantes, debe supervisar regularmente los registros de eventos.

**Frecuencia recomendada:** Cada 5-10 minutos

Para supervisar los productos de software de servidor de Adobe, se puede configurar la herramienta de administración automatizada para que supervise el registro de eventos en busca de errores con la fuente &quot;Adobe&quot; y, a continuación, avise al personal adecuado de los problemas que puedan requerir intervención.

En Windows, los mensajes de error de la aplicación se envían al registro de eventos de la aplicación en Windows, al que se puede acceder mediante el visor de eventos de Windows. En Unix, los mensajes de error de la aplicación se envían al syslog Unix mediante la función LOG_DAEMON.

**Para abrir el Visor de eventos de Windows**

* Haga clic **[!UICONTROL Start]** > **[!UICONTROL Control Panel]** > **[!UICONTROL Administrative Tools]** > **[!UICONTROL Event Viewer]**.

