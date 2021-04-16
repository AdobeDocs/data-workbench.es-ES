---
description: Compruebe si el transmisor se está ejecutando configurando alertas, comprobando el estado del sistema del sensor, etc.
title: Confirmación de la ejecución del transmisor de datos
uuid: 8dd6307c-e7d2-4800-88c7-f93385b33ca5
exl-id: 10ba704e-85be-425f-8a5d-9429100f367d
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '276'
ht-degree: 5%

---

# Confirmación de la ejecución del transmisor de datos{#confirming-that-the-data-transmitter-is-running}

Compruebe si el transmisor se está ejecutando configurando alertas, comprobando el estado del sistema del sensor, etc.

**Frecuencia recomendada:** cada 5-10 minutos

* [Compruebe que el proceso del transmisor se esté ejecutando.](../../../home/c-snsr-ovrvw/admin-sensor/c-data-trmtr-rng.md#section-79806fa3b7034a8eaf571a66e24874d7)
* [Configure alertas administrativas en Insight Server.](../../../home/c-snsr-ovrvw/admin-sensor/c-data-trmtr-rng.md#section-d98e0f18b8fb45a78419fe75610a3b1e)
* [Compruebe el estado del sistema del sensor.](../../../home/c-snsr-ovrvw/admin-sensor/c-data-trmtr-rng.md#section-de9d7e359242487a9fbead4ed65aebbc)

## Comprobación del proceso del transmisor {#section-79806fa3b7034a8eaf571a66e24874d7}

Una manera de verificar que el transmisor se está ejecutando es comprobar que el proceso del [!DNL Sensor] transmisor se está ejecutando en cada servidor web donde está instalada una instancia [!DNL Sensor]. El proceso del transmisor aparece como &quot;txlogd&quot; en la lista de procesos del servidor web. Puede realizar esta comprobación utilizando una herramienta de monitorización del sistema.

## Configuración de alertas administrativas en el servidor de Data Workbench {#section-d98e0f18b8fb45a78419fe75610a3b1e}

Otra forma de verificar que el transmisor se está ejecutando es configurar alertas administrativas automatizadas en [!DNL data workbench server]. Cuando se han configurado alertas administrativas, [!DNL data workbench server] genera una alerta de correo electrónico cuando no ha recibido datos de un [!DNL Sensor] configurado y conectado anteriormente dentro del lapso de tiempo especificado en el parámetro [!DNL Sensor] Tiempo de espera de alerta (min) del archivo [!DNL data workbench server’s] [!DNL Administrative Alerts.cfg] . Para obtener más información sobre la configuración de alertas administrativas, consulte la *Guía de instalación y administración de productos de servidor*.

## Comprobación del estado del sistema del sensor {#section-de9d7e359242487a9fbead4ed65aebbc}

Otra forma de comprobar que el transmisor se está ejecutando es comprobar manualmente la [!DNL Servers Manager] en la Data Workbench.

**Para ver el[!DNL Servers Manager]**

* En la Data Workbench, haga clic con el botón secundario en un espacio de trabajo, haga clic en **[!UICONTROL Admin]** y, a continuación, en [!DNL Manage], haga clic en **[!UICONTROL Servers]**.

Si el icono de un [!DNL Sensor] es verde, el transmisor se está ejecutando.

Para obtener más información sobre [!DNL Servers Manager], consulte el capítulo Interfaces administrativas de la *Guía [!DNL Sensor] de la Data Workbench*.
