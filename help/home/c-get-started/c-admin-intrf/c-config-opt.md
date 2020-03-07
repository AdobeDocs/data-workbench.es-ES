---
description: La opción Configuración abre el archivo Insight.cfg, que controla las conexiones a varios servidores.
solution: Analytics
title: Opción Configuración
topic: Data workbench
uuid: 1edfcf03-b278-4d81-942c-c9024378e13c
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Opción Configuración{#configuration-option}

La opción Configuración abre el archivo Insight.cfg, que controla las conexiones a varios servidores.

![](assets/cfg_Workstation.png)

**Para editar el archivo Insight.cfg**

1. En la [!DNL Insight.cfg] ventana, modifique los parámetros como desee. Para obtener descripciones detalladas de los parámetros del [!DNL Insight.cfg] archivo, consulte Parámetros [de configuración de](../../../home/c-get-started/c-insght-config-param.md#concept-14da97d0756348e885c08ca9e866074b)Insight.
1. Para guardar los ajustes de configuración, haga clic con el botón derecho del ratón **[!UICONTROL Insight.cfg (modified)]** en la parte superior de la ventana y haga clic en **[!UICONTROL Save as Insight.cfg]**.

**Para agregar nuevos servidores**

1. En la [!DNL Insight.cfg] ventana, haga clic con el botón derecho **[!UICONTROL Servers]** y haga clic en **[!UICONTROL Add new child]** > **[!UICONTROL Server]**.

   ![](assets/cfg_Workstation_AddServer.png)

1. Complete o modifique los parámetros del servidor para proporcionar acceso al área de trabajo de datos al servidor deseado. Para obtener descripciones detalladas de los parámetros del [!DNL Insight.cfg] archivo, consulte Parámetros [de configuración de](../../../home/c-get-started/c-insght-config-param.md#concept-14da97d0756348e885c08ca9e866074b)Insight.
1. Repita los pasos 1 y 2 para cada servidor en el que desee configurar una conexión.
1. Para guardar los ajustes de configuración, haga clic con el botón derecho del ratón **[!UICONTROL Insight.cfg (modified)]** en la parte superior de la ventana y haga clic en **[!UICONTROL Save as Insight.cfg]**.

El Área de trabajo de datos intenta conectarse a los servidores mediante la configuración especificada. Si se establece una conexión, aparecerá un nodo verde en la [!DNL Servers Manager] lista como se muestra a continuación. Si el Área de trabajo de datos no se puede conectar al servidor, aparece un nodo rojo.

![](assets/vis_SysStat_RedGreenDots.png)

