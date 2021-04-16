---
description: Debe añadir el campo x-experimentar al archivo Log Processing.cfg , que se utiliza para crear una dimensión ampliada.
solution: Analytics,Analytics
title: Modificación de Log Processing.cfg
uuid: 9105b09b-e3d5-4922-a205-b459553a4bec
exl-id: 23c7873f-8ffd-422f-896b-d6c7e16aabbd
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '186'
ht-degree: 4%

---

# Modificación de Log Processing.cfg{#modifying-log-processing-cfg}

Debe añadir el campo x-experimentar al archivo Log Processing.cfg , que se utiliza para crear una dimensión ampliada.

Consulte [Modificación de Transformation.cfg](../../../home/c-undst-ctrld-exp/c-vw-rslts/t-mod-trfmtn.md#task-d61b02853a82492c9a76e3c5fe8a3fb6).

**Para modificar Log Processing.cfg**

1. En [!DNL Insight], abra [!DNL Profile Manager] haciendo clic con el botón derecho en un espacio de trabajo y haciendo clic en **[!UICONTROL Admin]** > **[!UICONTROL Profile Manager]**, o abriendo el espacio de trabajo Administración de perfiles en la pestaña [!DNL Admin] .
1. En [!DNL Profile Manager], haga clic en **[!UICONTROL Dataset]** para mostrar su contenido.
1. Haga clic con el botón derecho en la marca de verificación situada junto a [!DNL Log Processing.cfg] y haga clic en **[!UICONTROL Make Local]**. En la columna [!DNL User] aparece una marca de verificación para este archivo.
1. Haga clic con el botón derecho en la marca de verificación recién creada y haga clic en **[!UICONTROL Open]** > **[!UICONTROL in Insight]**. Aparece la ventana [!DNL Log Processing.cfg].
1. Haga clic en **[!UICONTROL Fields]** para mostrar su contenido.
1. Haga clic con el botón derecho en el último campo de la lista actual y haga clic en **[!UICONTROL Add new]** > **[!UICONTROL Field]**.
1. Escriba x-experimentar en el campo recién creado, como se muestra en el siguiente ejemplo:

   ![Información sobre los pasos](assets/logprocessing.png)

1. Haga clic con el botón derecho **[!UICONTROL (modified)]** en la parte superior de la ventana y haga clic en **[!UICONTROL Save]**.
1. En [!DNL Profile Manager], haga clic con el botón derecho en la marca de verificación de [!DNL Log Processing.cfg] en la columna [!DNL User] y, a continuación, haga clic en **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]**>* para guardar los cambios realizados localmente en el perfil de trabajo.

   >[!NOTE]
   >
   >El conjunto de datos comienza a reprocesarse inmediatamente.

   Para obtener más información sobre Procesamiento de registros y campos, consulte la *Guía de configuración de conjuntos de datos*.
