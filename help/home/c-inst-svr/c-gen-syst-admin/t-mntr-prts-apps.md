---
description: Para monitorear más a fondo su implementación, puede monitorear todos los puertos de sus equipos de servidor, así como los productos de software que se ejecutan en cada uno de esos puertos.
solution: Analytics
title: Monitorización de puertos y aplicaciones
uuid: 63d92718-81df-49eb-adda-8b49bde57a9d
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '208'
ht-degree: 4%

---


# Monitorización de puertos y aplicaciones{#monitoring-ports-and-applications}

Para monitorear más a fondo su implementación, puede monitorear todos los puertos de sus equipos de servidor, así como los productos de software que se ejecutan en cada uno de esos puertos.

**Frecuencia recomendada:** Cada 5-10 minutos

Mediante una aplicación o una secuencia de comandos, puede supervisar el puerto TCP en el que se ejecuta cada aplicación (normalmente el puerto 80 o 443) para asegurarse de que la aplicación está enlazada a ese puerto. Para ello, solicita una página de estado de la aplicación desde el equipo que desea supervisar.

**Para solicitar la página de estado de la aplicación**

1. En el equipo que desea supervisar, modifique los Controles de acceso para permitir que la aplicación de supervisión o la secuencia de comandos accedan al equipo. Para obtener instrucciones, consulte [Configuración de Control de acceso](../../../home/c-inst-svr/c-admin-inst-svr/c-config-acs-ctrl/c-config-acs-ctrl.md#concept-ac385e870dbe4b57a72bf7266b60f93d).
1. Conéctese a [!DNL https://IP Address/Status/], donde Dirección IP es la dirección IP del equipo para el que desea recibir el estado.

   Ejemplo: [!DNL https://127.0.0.1/Status/]

   El equipo debe responder con una descripción del estado del servidor. Si no responde, compruebe los registros de eventos y póngase en contacto con el Servicio de atención al cliente de Adobe.

   Para obtener más información sobre este tipo de supervisión avanzada, póngase en contacto con los servicios de consultoría de Adobe.

