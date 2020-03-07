---
description: Información sobre el estado del servidor de informes y el estado del conjunto de informes.
solution: Analytics
title: Revisión del estado del informe
topic: Data workbench
uuid: 0f78a9fd-83d5-4e05-b7d1-d841033a5616
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Revisión del estado del informe{#reviewing-report-status}

Información sobre el estado del servidor de informes y el estado del conjunto de informes.

* [Estado del servidor de informes](../../../home/c-rpt-oview/c-admin-rpt/c-rev-rpt-st.md#section-1a84f22439ee4a4ba2b3434e51e82ce0)
* [Estado del conjunto de informes](../../../home/c-rpt-oview/c-admin-rpt/c-rev-rpt-st.md#section-8569b94266b74a1f85d2a85106a2aaef)

## Estado del servidor de informes {#section-1a84f22439ee4a4ba2b3434e51e82ce0}

**Frecuencia recomendada:** Sólo cuando sea necesario

[!DNL Report] envía información de estado al servidor del área de trabajo de datos cada dos minutos con respecto al estado del [!DNL Report] servidor. Esta información se puede ver en el [!DNL Report Server Status] nodo de la [!DNL Detailed Status] interfaz.

**Para abrir la[!DNL Detailed Status]visualización**

1. En el área de trabajo de datos, haga clic con el botón derecho en un área de trabajo y haga clic en **[!UICONTROL Admin]** > **[!UICONTROL Servers]**.

1. En la [!DNL Servers] interfaz, haga clic con el botón derecho en el icono del servidor del área de trabajo de datos al que se conecta el [!DNL Report] equipo y haga clic **[!UICONTROL Detailed Status.]**

1. Haga clic en **[!UICONTROL Report Server Status]**.

Si hay más de uno [!DNL Report] conectado al servidor del área de trabajo de datos, aparecerá una entrada para cada uno [!DNL Report Server] en el vector Estado. El intervalo de dos minutos se puede anular especificando un valor en el parámetro Intervalo de estado (segundos) en el [!DNL Reporting] nodo del [!DNL ReportServer.cfg] archivo.

Para obtener información sobre el [!DNL ReportServer.cfg] archivo, consulte [Configuración del conjunto](../../../home/c-rpt-oview/c-work-rpt-sets/t-create-rpt-set/t-config-rpt-set/t-config-rpt-set.md#task-cfb2fd0c28bc48c2acdd582fe0d670d0)de informes. Para obtener información sobre la configuración [!DNL Report], consulte [Instalación de informes](../../../home/c-rpt-oview/c-inst-rpt/c-inst-rpt.md#concept-3b8696a5b7f04ebfaafec7ff55890d91).

Para obtener más información sobre [!DNL Detailed Status], consulte el capítulo Interfaces administrativas de la Guía *del usuario de Área de trabajo de* datos.

## Estado del conjunto de informes {#section-8569b94266b74a1f85d2a85106a2aaef}

**Frecuencia recomendada:** Sólo cuando sea necesario

[!DNL Report] transmite la información de estado de cada conjunto de informes al servidor de Área de trabajo de datos. La información básica, como cuando se genera un conjunto de informes y se distribuye, se muestra en el área de trabajo de datos encima del conjunto de informes en texto verde. Al ejecutar informes, [!DNL Report] el servidor envía un mensaje cada dos minutos indicando el porcentaje de finalización de las consultas actuales. Este intervalo de dos minutos se puede anular especificando un valor en el parámetro Intervalo de mensaje de finalización (segundos) en el [!DNL Reporting] nodo del [!DNL ReportServer.cfg] archivo.

![](assets/report_status.png)

>[!NOTE]
>
>Si se produjo un error al ejecutar un informe, el error se indica en texto rojo debajo de la miniatura de ese informe. Puede hacer clic con el botón secundario en el espacio de trabajo para mostrar el mensaje de error completo.

