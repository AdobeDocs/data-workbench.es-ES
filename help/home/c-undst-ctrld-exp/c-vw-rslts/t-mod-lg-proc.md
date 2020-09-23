---
description: Debe agregar el campo x-experience al archivo Log Processing.cfg, que se utiliza para crear una dimensión ampliada.
solution: Analytics,Analytics
title: Modificación de Log Processing.cfg
topic: Data workbench
uuid: 9105b09b-e3d5-4922-a205-b459553a4bec
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '186'
ht-degree: 4%

---


# Modificación de Log Processing.cfg{#modifying-log-processing-cfg}

Debe agregar el campo x-experience al archivo Log Processing.cfg, que se utiliza para crear una dimensión ampliada.

Consulte [Modificación de Transformation.cfg](../../../home/c-undst-ctrld-exp/c-vw-rslts/t-mod-trfmtn.md#task-d61b02853a82492c9a76e3c5fe8a3fb6).

**Para modificar Log Processing.cfg**

1. En [!DNL Insight], abra la [!DNL Profile Manager] ficha haciendo clic con el botón derecho en un espacio de trabajo y haciendo clic en **[!UICONTROL Admin]** > **[!UICONTROL Profile Manager]**, o bien, abriendo el espacio de trabajo de administración de Perfiles en la [!DNL Admin] ficha.
1. En el [!DNL Profile Manager], haga clic **[!UICONTROL Dataset]** para mostrar su contenido.
1. Haga clic con el botón secundario en la marca de verificación situada junto a [!DNL Log Processing.cfg] y haga clic en **[!UICONTROL Make Local]**. En la [!DNL User] columna aparece una marca de verificación para este archivo.
1. Haga clic con el botón secundario en la marca de verificación recién creada y haga clic en **[!UICONTROL Open]** > **[!UICONTROL in Insight]**. Aparecerá la [!DNL Log Processing.cfg] ventana.
1. Haga clic en **[!UICONTROL Fields]** para mostrar su contenido.
1. Haga clic con el botón secundario en el último campo de la lista actual y haga clic en **[!UICONTROL Add new]** > **[!UICONTROL Field]**.
1. Escriba x-experience en el campo recién creado, como se muestra en el siguiente ejemplo:

   ![Información sobre los pasos](assets/logprocessing.png)

1. Haga clic con el botón secundario **[!UICONTROL (modified)]** en la parte superior de la ventana y haga clic en **[!UICONTROL Save]**.
1. En la [!DNL Profile Manager], haga clic con el botón secundario en la marca de verificación de [!DNL Log Processing.cfg] la [!DNL User] columna y, a continuación, haga clic en **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]**>* para guardar los cambios realizados localmente en el perfil de trabajo.

   >[!NOTE]
   >
   >El conjunto de datos comienza a reprocesarse inmediatamente.

   Para obtener más información sobre los campos y el procesamiento de registros, consulte la Guía *de configuración de* conjuntos de datos.

