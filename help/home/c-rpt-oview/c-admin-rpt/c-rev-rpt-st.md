---
description: Información sobre el estado del servidor de informes y el estado del conjunto de informes.
title: Revisión del estado del informe
uuid: 0f78a9fd-83d5-4e05-b7d1-d841033a5616
exl-id: a986f148-f019-457c-ade8-a4eaecbb1de7
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '293'
ht-degree: 2%

---

# Revisión del estado del informe{#reviewing-report-status}

Información sobre el estado del servidor de informes y el estado del conjunto de informes.

* [Estado del servidor de informes](../../../home/c-rpt-oview/c-admin-rpt/c-rev-rpt-st.md#section-1a84f22439ee4a4ba2b3434e51e82ce0)
* [Estado del conjunto de informes](../../../home/c-rpt-oview/c-admin-rpt/c-rev-rpt-st.md#section-8569b94266b74a1f85d2a85106a2aaef)

## Estado del servidor de informes {#section-1a84f22439ee4a4ba2b3434e51e82ce0}

**Frecuencia recomendada:** solo cuando sea necesario

[!DNL Report] envía información de estado al servidor de Data Workbench cada dos minutos con respecto al estado del  [!DNL Report] servidor. Esta información se puede ver en el nodo [!DNL Report Server Status] de la interfaz [!DNL Detailed Status].

**Para abrir la  [!DNL Detailed Status] visualización**

1. En Data Workbench, haga clic con el botón derecho en un espacio de trabajo y haga clic en **[!UICONTROL Admin]** > **[!UICONTROL Servers]**.

1. En la interfaz [!DNL Servers], haga clic con el botón derecho en el icono del servidor de Data Workbench al que se conecta el equipo [!DNL Report] y haga clic en **[!UICONTROL Detailed Status.]**

1. Haga clic en **[!UICONTROL Report Server Status]**.

Si hay más de un [!DNL Report] conectado al servidor de Data Workbench, aparece una entrada por cada [!DNL Report Server] en el vector Status. El intervalo de dos minutos se puede anular especificando un valor en el parámetro Intervalo de estado (segundos) en el nodo [!DNL Reporting] del archivo [!DNL ReportServer.cfg].

Para obtener información sobre el archivo [!DNL ReportServer.cfg], consulte [Configuración del conjunto de informes](../../../home/c-rpt-oview/c-work-rpt-sets/t-create-rpt-set/t-config-rpt-set/t-config-rpt-set.md#task-cfb2fd0c28bc48c2acdd582fe0d670d0). Para obtener información sobre cómo configurar [!DNL Report], consulte [Instalación del informe](../../../home/c-rpt-oview/c-inst-rpt/c-inst-rpt.md#concept-3b8696a5b7f04ebfaafec7ff55890d91).

Para obtener más información sobre [!DNL Detailed Status], consulte el capítulo Interfaces administrativas de la *Guía del usuario de la Data Workbench*.

## Estado del conjunto de informes {#section-8569b94266b74a1f85d2a85106a2aaef}

**Frecuencia recomendada:** solo cuando sea necesario

[!DNL Report] transmite la información de estado de cada conjunto de informes al servidor de Data Workbench. La información básica, como cuando se genera un conjunto de informes y se distribuye, se muestra en el área de trabajo de datos encima del conjunto de informes en verde. Al ejecutar informes, [!DNL Report] El servidor envía un mensaje cada dos minutos indicando el porcentaje de finalización de las consultas actuales. Este intervalo de dos minutos se puede anular especificando un valor en el parámetro Intervalo de mensaje de finalización (segundos) en el nodo [!DNL Reporting] del archivo [!DNL ReportServer.cfg].

![](assets/report_status.png)

>[!NOTE]
>
>Si se ha producido un error al ejecutar un informe, el error se indica en un texto rojo debajo de la miniatura de ese informe. Puede hacer clic con el botón derecho en el espacio de trabajo para mostrar el mensaje de error completo.
