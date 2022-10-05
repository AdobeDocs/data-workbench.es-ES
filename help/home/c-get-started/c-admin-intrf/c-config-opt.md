---
description: La opción Configuración abre el archivo Insight.cfg, que controla las conexiones a varios servidores.
title: Opción de configuración
uuid: 1edfcf03-b278-4d81-942c-c9024378e13c
exl-id: bb694d3c-64f7-4a74-b774-4d5145250e6d
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '182'
ht-degree: 2%

---

# Opción de configuración{#configuration-option}

{{eol}}

La opción Configuración abre el archivo Insight.cfg, que controla las conexiones a varios servidores.

![](assets/cfg_Workstation.png)

**Para editar el archivo Insight.cfg**

1. En el [!DNL Insight.cfg] , modifique los parámetros como desee. Para obtener descripciones detalladas de los parámetros de la variable [!DNL Insight.cfg] archivo, consulte [Parámetros de configuración de Insight](../../../home/c-get-started/c-insght-config-param.md#concept-14da97d0756348e885c08ca9e866074b).
1. Para guardar los ajustes de configuración, haga clic con el botón derecho del ratón **[!UICONTROL Insight.cfg (modified)]** en la parte superior de la ventana y haga clic en **[!UICONTROL Save as Insight.cfg]**.

**Para agregar nuevos servidores**

1. En el [!DNL Insight.cfg] ventana, clic con el botón derecho **[!UICONTROL Servers]** y haga clic en **[!UICONTROL Add new child]** > **[!UICONTROL Server]**.

   ![](assets/cfg_Workstation_AddServer.png)

1. Complete o modifique los parámetros del servidor para proporcionar a la Data Workbench acceso al servidor deseado. Para obtener descripciones detalladas de los parámetros de la variable [!DNL Insight.cfg] archivo, consulte [Parámetros de configuración de Insight](../../../home/c-get-started/c-insght-config-param.md#concept-14da97d0756348e885c08ca9e866074b).
1. Repita los pasos 1 y 2 para cada servidor al que desee configurar una conexión.
1. Para guardar los ajustes de configuración, haga clic con el botón derecho del ratón **[!UICONTROL Insight.cfg (modified)]** en la parte superior de la ventana y haga clic en **[!UICONTROL Save as Insight.cfg]**.

La Data Workbench intenta conectarse a los servidores utilizando la configuración especificada. Si se establece una conexión, aparece un nodo verde en la variable [!DNL Servers Manager] como se muestra a continuación. Si la Data Workbench no se puede conectar al servidor, aparece un nodo rojo.

![](assets/vis_SysStat_RedGreenDots.png)
