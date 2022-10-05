---
description: Compruebe si el transmisor se está ejecutando configurando alertas, comprobando el estado del sistema del sensor, etc.
title: Confirmación de la ejecución del transmisor de datos
uuid: 8dd6307c-e7d2-4800-88c7-f93385b33ca5
exl-id: 10ba704e-85be-425f-8a5d-9429100f367d
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '276'
ht-degree: 5%

---

# Confirmación de la ejecución del transmisor de datos{#confirming-that-the-data-transmitter-is-running}

{{eol}}

Compruebe si el transmisor se está ejecutando configurando alertas, comprobando el estado del sistema del sensor, etc.

**Frecuencia recomendada:** Cada 5-10 minutos

* [Compruebe que el proceso del transmisor se esté ejecutando.](../../../home/c-snsr-ovrvw/admin-sensor/c-data-trmtr-rng.md#section-79806fa3b7034a8eaf571a66e24874d7)
* [Configure alertas administrativas en Insight Server.](../../../home/c-snsr-ovrvw/admin-sensor/c-data-trmtr-rng.md#section-d98e0f18b8fb45a78419fe75610a3b1e)
* [Compruebe el estado del sistema del sensor.](../../../home/c-snsr-ovrvw/admin-sensor/c-data-trmtr-rng.md#section-de9d7e359242487a9fbead4ed65aebbc)

## Comprobación del proceso del transmisor {#section-79806fa3b7034a8eaf571a66e24874d7}

Una forma de verificar que el transmisor está funcionando es comprobar que la variable [!DNL Sensor] el proceso de transmisor se está ejecutando en cada servidor web donde se [!DNL Sensor] está instalada. El proceso del transmisor aparece como &quot;txlogd&quot; en la lista de procesos del servidor web. Puede realizar esta comprobación utilizando una herramienta de monitorización del sistema.

## Configuración de alertas administrativas en el servidor de Data Workbench {#section-d98e0f18b8fb45a78419fe75610a3b1e}

Otra forma de verificar que el transmisor se está ejecutando es configurar alertas administrativas automatizadas en la variable [!DNL data workbench server]. Cuando se han configurado las alertas administrativas, la variable [!DNL data workbench server] genera una alerta de correo electrónico cuando no ha recibido datos de un [!DNL Sensor] dentro del lapso de tiempo especificado en la variable [!DNL Sensor] Tiempo de espera de alerta (min) en el parámetro [!DNL data workbench server’s] [!DNL Administrative Alerts.cfg] archivo. Para obtener más información sobre la configuración de alertas administrativas, consulte la *Guía de instalación y administración de productos para servidor*.

## Comprobación del estado del sistema del sensor {#section-de9d7e359242487a9fbead4ed65aebbc}

Otra forma de verificar que el transmisor está funcionando es comprobar manualmente la [!DNL Servers Manager] en Data Workbench.

**Para ver el[!DNL Servers Manager]**

* En Data Workbench, haga clic con el botón derecho en un espacio de trabajo y haga clic en **[!UICONTROL Admin]** y, a continuación, debajo de [!DNL Manage], haga clic en **[!UICONTROL Servers]**.

Si el icono de un [!DNL Sensor] es verde, el transmisor está funcionando.

Para obtener más información sobre la variable [!DNL Servers Manager], consulte el capítulo Interfaces administrativas del *Data Workbench [!DNL Sensor] Guía*.
