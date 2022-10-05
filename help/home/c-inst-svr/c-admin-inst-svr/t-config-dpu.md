---
description: El archivo de configuración de DPU, DPU.cfg, especifica varios parámetros de rendimiento para Insight Server.
title: Configuración de DPU.cfg
uuid: c348622b-7d4b-4cfa-a8f8-a07d91e440d5
exl-id: 55e4ea7f-fee3-4af7-9cbc-d121e79e6ab2
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '206'
ht-degree: 1%

---

# Configuración de DPU.cfg{#configuring-dpu-cfg}

{{eol}}

El archivo de configuración de DPU, DPU.cfg, especifica varios parámetros de rendimiento para Insight Server.

La forma de configurar estos parámetros depende del tamaño del conjunto de datos y de muchos otros factores. Póngase en contacto con los servicios de consultoría de Adobe para obtener ayuda con el ajuste del rendimiento.

**Frecuencia recomendada:** Solo cuando sea necesario

**Para cambiar [!DNL Insight Server] Configuración de rendimiento de DPU**

1. En [!DNL Insight], en el [!DNL Admin] > [!DNL Dataset and Profile] , haga clic en la pestaña **[!UICONTROL Servers Manager]** miniatura para abrir el espacio de trabajo del Administrador de servidores.
1. Haga clic con el botón derecho en el icono de la variable [!DNL Insight Server] desea configurar y hacer clic en **[!UICONTROL Server Files]**.
1. En el [!DNL Server Files Manager], haga clic en **[!UICONTROL Components]** para ver su contenido. La variable [!DNL DPU.cfg] se encuentra dentro de este directorio.
1. Haga clic con el botón derecho en la marca de verificación de la *nombre del servidor* para [!DNL DPU.cfg] y haga clic en **[!UICONTROL Make Local]**. Aparece una marca de verificación en la variable [!DNL Temp] para [!DNL DPU.cfg].
1. Haga clic con el botón derecho en la marca de verificación recién creada en la [!DNL Temp] y haga clic en **[!UICONTROL Open]** > **[!UICONTROL in Insight]**.
1. En el [!DNL DPU.cfg] , haga clic en componente para ver su contenido.
1. Cambie el rendimiento y la configuración de la ruta, según sea necesario. Para obtener una lista de los parámetros disponibles en este archivo, consulte [Configuración de rendimiento de DPU](../../../home/c-inst-svr/c-cfg-stgs-ref/c-dpu-perf-stgs.md#concept-477c4c526de44bda84176e62266c3df1).

   >[!NOTE]
   >
   >Póngase en contacto con Adobe antes de cambiar cualquiera de los parámetros de este archivo.

   ![](assets/cfg_DPU_egvalues.png)

1. Guarde los cambios en el servidor haciendo lo siguiente:

   1. Clic con el botón derecho **[!UICONTROL (modified)]** en la parte superior de la ventana y haga clic en **[!UICONTROL Save]**.

   1. En el [!DNL Server Files Manager], haga clic con el botón derecho en la marca de verificación del archivo en la variable [!DNL Temp] y seleccione **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>*.
