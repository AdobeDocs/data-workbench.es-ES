---
description: El archivo de configuración de Comunicaciones, Communications.cfg, contiene la configuración de red de Insight Server y la ruta al archivo Access Control.cfg.
title: Configuración de comunicaciones
uuid: 04d08206-17b1-4348-a945-0c907c9a494c
exl-id: af5e788e-8904-4c68-b02a-c95b523b076d
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '189'
ht-degree: 3%

---

# Configuración de comunicaciones{#configuring-communications}

El archivo de configuración de Comunicaciones, Communications.cfg, contiene la configuración de red de Insight Server y la ruta al archivo Access Control.cfg.

Esta configuración le ayuda a conectarse a [!DNL Insight Server].

**Frecuencia recomendada:** solo cuando sea necesario

**Para ver y modificar la configuración de comunicaciones en[!DNL Insight]**

1. En [!DNL Insight], en la pestaña [!DNL Admin] > [!DNL Dataset and Profile], haga clic en la miniatura **[!UICONTROL Servers Manager]** para abrir el espacio de trabajo del Administrador de servidores.
1. Haga clic con el botón derecho en el icono del [!DNL Insight Server] que desee configurar y haga clic en **[!UICONTROL Server Files]**.
1. En [!DNL Server Files Manager], haga clic en **[!UICONTROL Components]** para ver su contenido. El archivo [!DNL Communications.cfg] se encuentra dentro de este directorio.
1. Haga clic con el botón derecho en la marca de verificación de la columna *server name* para [!DNL Communications.cfg] y haga clic en **[!UICONTROL Make Local]**. Aparece una marca de verificación en la columna [!DNL Temp] de [!DNL Communications.cfg].
1. Haga clic con el botón derecho en la marca de verificación recién creada en la columna [!DNL Temp] y haga clic en **[!UICONTROL Open]** > **[!UICONTROL in Insight]**.
1. En la ventana [!DNL Communications.cfg], haga clic en **[!UICONTROL component]** para ver su contenido.
1. Cambie la configuración según sea necesario. Para obtener información sobre los parámetros disponibles en este archivo, consulte [Configuración de comunicaciones](../../../home/c-inst-svr/c-cfg-stgs-ref/c-comm-cfg-stgs.md#concept-aed00587c7a1432fb487bd154aaea6b1).

   ![Información sobre los pasos](assets/cfg_communications_examplevalues.png)

1. Guarde los cambios en el servidor haciendo lo siguiente:

   1. Haga clic con el botón derecho **[!UICONTROL (modified)]** en la parte superior de la ventana y haga clic en **[!UICONTROL Save]**.

   1. En [!DNL Server Files Manager], haga clic con el botón derecho en la marca de verificación del archivo en la columna [!DNL Temp] y seleccione **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>*.
