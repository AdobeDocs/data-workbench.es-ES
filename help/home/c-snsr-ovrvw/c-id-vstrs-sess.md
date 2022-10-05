---
description: Al recopilar datos de eventos de un servidor web, Sensor establece automáticamente una cookie persistente para cada visitante que contiene un pequeño identificador aleatorio, sin capturar ninguna información de identificación personal.
title: ¿Cómo identifica el sensor los visitantes y las sesiones?
uuid: 3735ed2d-67c4-469b-8b3e-0fac90cc4c09
exl-id: f5781ed6-ac83-4a8e-b412-8966f8c39c41
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '232'
ht-degree: 6%

---

# ¿Cómo identifica el sensor los visitantes y las sesiones?{#how-does-sensor-identify-visitors-and-sessions}

{{eol}}

Al recopilar datos de eventos de un servidor web, Sensor establece automáticamente una cookie persistente para cada visitante que contiene un pequeño identificador aleatorio, sin capturar ninguna información de identificación personal.

Esta cookie de Adobe se utiliza para identificar al visitante único y todas sus sesiones relacionadas.

De forma predeterminada, [!DNL Sensor] captura todos los campos de formato de archivo de registro ampliado W3C de cada encabezado HTTP, pero puede configurar [!DNL Sensor] para capturar cualquier encabezado que se transmita entre el cliente y el servidor. Para obtener información sobre los campos de datos de evento recopilados por [!DNL Sensor] en [!DNL .vsl] archivos, consulte [Campos de registro de datos de evento](../../home/c-snsr-ovrvw/c-evnt-data-rcd-flds/c-evnt-data-rcd-flds.md#concept-ed2a8797cb5b4995b55ffd50a9f12a44).

Los exploradores de algunos visitantes no almacenan cookies de forma persistente y un número muy pequeño de exploradores de los visitantes no aceptan cookies (incluso las cookies de sesión). Aunque solo representan una fracción del tráfico total de un sitio, pueden resultar en un recuento erróneo significativo si cada vista de página por parte de un visitante se cuenta incorrectamente como una sesión completa, como lo hace algún software de análisis de archivos de registro. Adobe soluciona este problema permitiéndole analizar los visitantes con y sin usar cookies.

Para obtener más información sobre el filtro de sesiones interrumpidas, consulte la *Guía del sensor de Data Workbench*.
