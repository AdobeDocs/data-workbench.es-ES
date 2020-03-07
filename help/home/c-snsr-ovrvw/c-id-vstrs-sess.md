---
description: Al recopilar datos de eventos de un servidor web, Sensor establece automáticamente una cookie persistente para cada visitante que contiene un pequeño identificador aleatorio, sin capturar ninguna información de identificación personal.
solution: Insight
title: ¿Cómo identifica el sensor a los visitantes y las sesiones?
uuid: 3735ed2d-67c4-469b-8b3e-0fac90cc4c09
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# ¿Cómo identifica el sensor a los visitantes y las sesiones?{#how-does-sensor-identify-visitors-and-sessions}

Al recopilar datos de eventos de un servidor web, Sensor establece automáticamente una cookie persistente para cada visitante que contiene un pequeño identificador aleatorio, sin capturar ninguna información de identificación personal.

Esta cookie de Adobe se utiliza para identificar al visitante único y todas sus sesiones relacionadas.

De forma predeterminada, [!DNL Sensor] captura todos los campos de Formato de archivo de registro ampliado W3C de cada encabezado HTTP, pero puede configurarlos [!DNL Sensor] para capturar cualquier encabezado que se transmita entre el cliente y el servidor. Para obtener información sobre los campos de datos de eventos recopilados por [!DNL Sensor] en [!DNL .vsl] archivos, consulte Campos [de registro de datos de](../../home/c-snsr-ovrvw/c-evnt-data-rcd-flds/c-evnt-data-rcd-flds.md#concept-ed2a8797cb5b4995b55ffd50a9f12a44)eventos.

Algunos exploradores de visitantes no almacenan las cookies de forma persistente y un número muy pequeño de exploradores de visitantes no aceptan las cookies (incluso las cookies de sesión). Aunque solo representan una fracción del tráfico total de un sitio, pueden resultar en un recuento erróneo significativo si cada vista de página por parte de un visitante se cuenta incorrectamente como una sesión completa, como lo hace algún software de análisis de archivos de registro. Adobe resuelve este problema permitiéndole analizar a los visitantes con y sin utilizar cookies.

Para obtener más información sobre el filtro de sesiones interrumpidas, consulte la Guía del sensor *del área de trabajo de datos*.
