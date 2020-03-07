---
description: El archivo de configuración DPU, DPU.cfg, especifica varios parámetros de rendimiento para Insight Server.
solution: Insight
title: Configuración de DPU.cfg
uuid: c348622b-7d4b-4cfa-a8f8-a07d91e440d5
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Configuración de DPU.cfg{#configuring-dpu-cfg}

El archivo de configuración DPU, DPU.cfg, especifica varios parámetros de rendimiento para Insight Server.

La manera de configurar estos parámetros depende del tamaño del conjunto de datos y de muchos otros factores. Póngase en contacto con los servicios de consultoría de Adobe para obtener ayuda con el ajuste del rendimiento.

**Frecuencia recomendada:** Sólo cuando sea necesario

**Para cambiar la configuración[!DNL Insight Server]de rendimiento de DPU**

1. En [!DNL Insight], en la ficha [!DNL Admin] > [!DNL Dataset and Profile] , haga clic en la **[!UICONTROL Servers Manager]** miniatura para abrir el espacio de trabajo del Administrador de servidores.
1. Haga clic con el botón secundario en el icono del [!DNL Insight Server] que desee configurar y haga clic en **[!UICONTROL Server Files]**.
1. En el [!DNL Server Files Manager], haga clic **[!UICONTROL Components]** para ver su contenido. El [!DNL DPU.cfg] archivo se encuentra dentro de este directorio.
1. Haga clic con el botón secundario en la marca de verificación de la columna del nombre *del* servidor [!DNL DPU.cfg] y haga clic en **[!UICONTROL Make Local]**. Aparece una marca de verificación en la [!DNL Temp] columna para [!DNL DPU.cfg].
1. Haga clic con el botón secundario en la marca de verificación recién creada en la [!DNL Temp] columna y haga clic en **[!UICONTROL Open]** > **[!UICONTROL in Insight]**.
1. En la [!DNL DPU.cfg] ventana, haga clic en el componente para ver su contenido.
1. Cambie el rendimiento y la configuración de ruta, según sea necesario. Para obtener una lista de los parámetros disponibles en este archivo, consulte Configuración [de rendimiento de](../../../home/c-inst-svr/c-cfg-stgs-ref/c-dpu-perf-stgs.md#concept-477c4c526de44bda84176e62266c3df1)DPU.

   >[!NOTE]
   >
   >Póngase en contacto con Adobe antes de cambiar cualquiera de los parámetros de este archivo.

   ![](assets/cfg_DPU_egvalues.png)

1. Guarde los cambios en el servidor haciendo lo siguiente:

   1. Haga clic con el botón secundario **[!UICONTROL (modified)]** en la parte superior de la ventana y haga clic en **[!UICONTROL Save]**.

   1. En la [!DNL Server Files Manager], haga clic con el botón derecho en la marca de verificación del archivo en la [!DNL Temp] columna y seleccione **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>*.

