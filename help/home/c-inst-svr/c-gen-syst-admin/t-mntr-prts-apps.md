---
description: Para monitorizar su implementación de forma más exhaustiva, puede monitorizar todos los puertos de sus equipos de servidor, así como los productos de software que se ejecutan en cada uno de esos puertos.
title: Monitorización de puertos y aplicaciones
uuid: 63d92718-81df-49eb-adda-8b49bde57a9d
exl-id: 418b2e5c-42ec-40f0-9cae-375194288143
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '208'
ht-degree: 4%

---

# Monitorización de puertos y aplicaciones{#monitoring-ports-and-applications}

{{eol}}

Para monitorizar su implementación de forma más exhaustiva, puede monitorizar todos los puertos de sus equipos de servidor, así como los productos de software que se ejecutan en cada uno de esos puertos.

**Frecuencia recomendada:** Cada 5-10 minutos

Con una aplicación o secuencia de comandos, se puede controlar el puerto TCP en el que se ejecuta cada aplicación (normalmente el puerto 80 o 443) para asegurarse de que la aplicación está enlazada a ese puerto. Para ello, solicita una página de estado de la aplicación desde el equipo que desea monitorizar.

**Para solicitar la página de estado de la aplicación**

1. En el equipo que desee monitorizar, modifique los controles de acceso para permitir que la aplicación de monitorización o la secuencia de comandos accedan al equipo. Para obtener instrucciones, consulte [Configuración del control de acceso](../../../home/c-inst-svr/c-admin-inst-svr/c-config-acs-ctrl/c-config-acs-ctrl.md#concept-ac385e870dbe4b57a72bf7266b60f93d).
1. Conectar a [!DNL https://IP Address/Status/], donde Dirección IP es la dirección IP del equipo para el que desea recibir el estado.

   Ejemplo: [!DNL https://127.0.0.1/Status/]

   El equipo debe responder con una descripción del estado del servidor. Si no responde, compruebe sus registros de eventos y póngase en contacto con el servicio de atención al cliente de Adobe.

   Para obtener más información sobre este tipo de supervisión avanzada, póngase en contacto con los servicios de consultoría de Adobe.
