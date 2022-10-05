---
description: Información sobre el estado del servidor de informes y el estado del conjunto de informes.
title: Revisión del estado del informe
uuid: 0f78a9fd-83d5-4e05-b7d1-d841033a5616
exl-id: a986f148-f019-457c-ade8-a4eaecbb1de7
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '293'
ht-degree: 2%

---

# Revisión del estado del informe{#reviewing-report-status}

{{eol}}

Información sobre el estado del servidor de informes y el estado del conjunto de informes.

* [Estado del servidor de informes](../../../home/c-rpt-oview/c-admin-rpt/c-rev-rpt-st.md#section-1a84f22439ee4a4ba2b3434e51e82ce0)
* [Estado del conjunto de informes](../../../home/c-rpt-oview/c-admin-rpt/c-rev-rpt-st.md#section-8569b94266b74a1f85d2a85106a2aaef)

## Estado del servidor de informes {#section-1a84f22439ee4a4ba2b3434e51e82ce0}

**Frecuencia recomendada:** Solo cuando sea necesario

[!DNL Report] envía información de estado al servidor de Data Workbench cada dos minutos con respecto al estado del [!DNL Report] Servidor. Esta información se puede ver en la sección [!DNL Report Server Status] en el [!DNL Detailed Status] interfaz.

**Para abrir el [!DNL Detailed Status] visualización**

1. En Data Workbench, haga clic con el botón derecho en un espacio de trabajo y haga clic en **[!UICONTROL Admin]** > **[!UICONTROL Servers]**.

1. En el [!DNL Servers] , haga clic con el botón derecho en el icono del servidor de Data Workbench que [!DNL Report] la máquina se conecta a y haga clic en **[!UICONTROL Detailed Status.]**

1. Haga clic en **[!UICONTROL Report Server Status]**.

Si hay más de uno [!DNL Report] está conectado al servidor de Data Workbench, aparece una entrada para cada [!DNL Report Server] en el vector Status . El intervalo de dos minutos se puede anular especificando un valor en el parámetro Intervalo de estado (segundos) en la variable [!DNL Reporting] nodo de la variable [!DNL ReportServer.cfg] archivo.

Para obtener información sobre la variable [!DNL ReportServer.cfg] archivo, consulte [Configuración del conjunto de informes](../../../home/c-rpt-oview/c-work-rpt-sets/t-create-rpt-set/t-config-rpt-set/t-config-rpt-set.md#task-cfb2fd0c28bc48c2acdd582fe0d670d0). Para obtener información sobre cómo configurar [!DNL Report], consulte [Instalación del informe](../../../home/c-rpt-oview/c-inst-rpt/c-inst-rpt.md#concept-3b8696a5b7f04ebfaafec7ff55890d91).

Para obtener más información, consulte [!DNL Detailed Status], consulte el capítulo Interfaces administrativas del *Guía del usuario de Data Workbench*.

## Estado del conjunto de informes {#section-8569b94266b74a1f85d2a85106a2aaef}

**Frecuencia recomendada:** Solo cuando sea necesario

[!DNL Report] transmite la información de estado de cada conjunto de informes al servidor de Data Workbench. La información básica, como cuando se genera un conjunto de informes y se distribuye, se muestra en el área de trabajo de datos encima del conjunto de informes en verde. Mientras se ejecutan los informes, [!DNL Report] El servidor envía un mensaje cada dos minutos indicando el porcentaje de finalización de las consultas actuales. Este intervalo de dos minutos se puede anular especificando un valor en el parámetro Intervalo de mensaje de finalización (segundos) en la variable [!DNL Reporting] nodo de la variable [!DNL ReportServer.cfg] archivo.

![](assets/report_status.png)

>[!NOTE]
>
>Si se ha producido un error al ejecutar un informe, el error se indica en un texto rojo debajo de la miniatura de ese informe. Puede hacer clic con el botón derecho en el espacio de trabajo para mostrar el mensaje de error completo.
