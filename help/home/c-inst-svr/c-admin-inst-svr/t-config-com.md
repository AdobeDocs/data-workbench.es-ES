---
description: El archivo de configuración Communications, Communications.cfg, contiene la configuración de red de Insight Server y la ruta del archivo Control de acceso.cfg.
solution: Analytics
title: Configuración de comunicaciones
uuid: 04d08206-17b1-4348-a945-0c907c9a494c
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '189'
ht-degree: 3%

---


# Configuración de comunicaciones{#configuring-communications}

El archivo de configuración Communications, Communications.cfg, contiene la configuración de red de Insight Server y la ruta del archivo Control de acceso.cfg.

Esta configuración le ayuda a conectarse a [!DNL Insight Server].

**Frecuencia recomendada:** Sólo cuando sea necesario

**Para vista y modificación de la configuración de comunicaciones en[!DNL Insight]**

1. En [!DNL Insight], en la ficha [!DNL Admin] > [!DNL Dataset and Profile] , haga clic en la **[!UICONTROL Servers Manager]** miniatura para abrir el espacio de trabajo del Administrador de servidores.
1. Haga clic con el botón secundario en el icono del [!DNL Insight Server] que desee configurar y haga clic en **[!UICONTROL Server Files]**.
1. En el [!DNL Server Files Manager], haga clic en **[!UICONTROL Components]** para vista de su contenido. El [!DNL Communications.cfg] archivo se encuentra dentro de este directorio.
1. Haga clic con el botón secundario en la marca de verificación de la columna del nombre *del* servidor [!DNL Communications.cfg] y haga clic en **[!UICONTROL Make Local]**. Aparece una marca de verificación en la [!DNL Temp] columna para [!DNL Communications.cfg].
1. Haga clic con el botón secundario en la marca de verificación recién creada en la [!DNL Temp] columna y haga clic en **[!UICONTROL Open]** > **[!UICONTROL in Insight]**.
1. En la [!DNL Communications.cfg] ventana, haga clic en **[!UICONTROL component]** para vista de su contenido.
1. Cambie la configuración según sea necesario. Para obtener información sobre los parámetros disponibles en este archivo, consulte Configuración de [comunicaciones](../../../home/c-inst-svr/c-cfg-stgs-ref/c-comm-cfg-stgs.md#concept-aed00587c7a1432fb487bd154aaea6b1).

   ![Información sobre los pasos](assets/cfg_communications_examplevalues.png)

1. Guarde los cambios en el servidor haciendo lo siguiente:

   1. Haga clic con el botón secundario **[!UICONTROL (modified)]** en la parte superior de la ventana y haga clic en **[!UICONTROL Save]**.

   1. En la [!DNL Server Files Manager], haga clic con el botón derecho en la marca de verificación del archivo en la [!DNL Temp] columna y seleccione **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>*.

