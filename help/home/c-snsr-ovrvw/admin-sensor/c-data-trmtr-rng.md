---
description: Compruebe si el transmisor se está ejecutando configurando alertas, comprobando el estado del sistema del sensor y mucho más.
solution: Analytics
title: Confirmación de la ejecución del transmisor de datos
uuid: 8dd6307c-e7d2-4800-88c7-f93385b33ca5
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '276'
ht-degree: 5%

---


# Confirmación de la ejecución del transmisor de datos{#confirming-that-the-data-transmitter-is-running}

Compruebe si el transmisor se está ejecutando configurando alertas, comprobando el estado del sistema del sensor y mucho más.

**Frecuencia recomendada:** Cada 5-10 minutos

* [Compruebe que el proceso del transmisor se está ejecutando.](../../../home/c-snsr-ovrvw/admin-sensor/c-data-trmtr-rng.md#section-79806fa3b7034a8eaf571a66e24874d7)
* [Configure alertas administrativas en Insight Server.](../../../home/c-snsr-ovrvw/admin-sensor/c-data-trmtr-rng.md#section-d98e0f18b8fb45a78419fe75610a3b1e)
* [Compruebe el estado del sistema del sensor.](../../../home/c-snsr-ovrvw/admin-sensor/c-data-trmtr-rng.md#section-de9d7e359242487a9fbead4ed65aebbc)

## Comprobación del proceso del transmisor {#section-79806fa3b7034a8eaf571a66e24874d7}

Una manera de verificar que el transmisor se está ejecutando es comprobar que el proceso del [!DNL Sensor] transmisor se está ejecutando en cada servidor web en el que está instalada una [!DNL Sensor] instancia. El proceso del transmisor aparece como &quot;txlogd&quot; en la lista de procesos del servidor web. Puede realizar esta comprobación con una herramienta de supervisión del sistema.

## Configuración de alertas administrativas en el servidor de Data Workbench {#section-d98e0f18b8fb45a78419fe75610a3b1e}

Otra manera de verificar que el transmisor se está ejecutando es configurar alertas administrativas automatizadas en el [!DNL data workbench server]. Cuando se han configurado alertas administrativas, la alerta [!DNL data workbench server] genera una alerta de correo electrónico cuando no ha recibido datos de un parámetro configurado y previamente conectado [!DNL Sensor] dentro del intervalo de tiempo especificado en el parámetro [!DNL Sensor] Alert Timeout (min) en el [!DNL data workbench server’s] archivo [!DNL Administrative Alerts.cfg] . Para obtener más información sobre la configuración de alertas administrativas, consulte la Guía *de instalación y administración de productos* de servidor.

## Comprobación del estado del sistema del sensor {#section-de9d7e359242487a9fbead4ed65aebbc}

Otra forma de comprobar que el transmisor está funcionando es comprobar manualmente la Data Workbench [!DNL Servers Manager] en pantalla.

**Para la vista de la variable[!DNL Servers Manager]**

* En Data Workbench, haga clic con el botón secundario en un espacio de trabajo, haga clic en **[!UICONTROL Admin]**, luego en [!DNL Manage], haga clic en **[!UICONTROL Servers]**.

Si el icono de un [!DNL Sensor] es verde, el transmisor se está ejecutando.

Para obtener más información sobre el [!DNL Servers Manager], consulte el capítulo Interfaces administrativas de la *Guía[!DNL Sensor]de* Data Workbench.
