---
description: Pasos para cambiar la visualización predeterminada.
solution: Analytics
title: Configuración de la interfaz de esquema de conjunto de datos
topic: Data workbench
uuid: 953909e8-3382-43cf-98c0-d4785c6d1dda
translation-type: tm+mt
source-git-commit: 25366087936dfa5e31c5921aac400535ec259f2e

---


# Configuración de la interfaz de esquema de conjunto de datos{#configure-the-dataset-schema-interface}

Pasos para cambiar la visualización predeterminada.

Puede controlar qué tipo de visualización se muestra al hacer clic en el nombre de una dimensión en una [!DNL Dataset Schema Interface] ventana agregando archivos al nombre de perfil\*nombre de perfil*\Context\Dimension Legend folder of the Data Workbench server installation folder. El [!DNL Default.1d] archivo de esta carpeta controla el tipo de visualización predeterminado para todas las dimensiones. Al agregar un archivo *dimension name*.1d (como [!DNL Hour.1d]) a esta carpeta, puede controlar la visualización predeterminada de esa dimensión en particular.

Para obtener más información sobre [!DNL Dataset Schema Interfaces], consulte [La interfaz](../../../home/c-get-started/c-admin-intrf/c-dtst-sch-intrf.md#concept-e147b3a5b542453ca2b121e1c85bb175)de esquema de conjunto de datos.

**Cambiar la visualización predeterminada**

1. En cualquier espacio de trabajo, cree una visualización que contenga los datos que desea que aparezcan en la nueva visualización predeterminada.

   Por ejemplo, si desea que la dimensión se muestre en un gráfico de barras, cree una visualización de gráfico de barras que muestre la métrica y la dimensión que desee.

1. Haga clic con el botón secundario en el borde superior de la ventana de llamada y haga clic en **[!UICONTROL Save]**.
1. En la [!DNL Save] ventana, haga clic en ![](assets/btn_folder_up.png), haga doble clic **[!UICONTROL Context]** y, a continuación, haga doble clic en **[!UICONTROL Dimension Legend]**.
1. En el [!DNL File Name] campo, escriba el nombre de la dimensión.

   The name of the [!DNL .1d] file must match the name of the dimension exactly. Por ejemplo: [!DNL Hour.1d].

1. Cambie la extensión de archivo a &quot;1d&quot; y haga clic en **[!UICONTROL Save]**.

   El archivo se guarda en el usuario\*nombre de perfil de trabajo*\Context\Dimension Legend folder.

   La próxima vez que haga clic en esa dimensión desde dentro de una [!DNL Dataset Schema Interface], se mostrará la visualización especificada.

1. (Opcional) Para que este cambio esté disponible para todos los usuarios del perfil de trabajo:

   1. In the [!DNL Profile Manager], click **[!UICONTROL Context]**, then click **[!UICONTROL Dimension Legend]**.

   1. Haga clic con el botón secundario en la marca de verificación situada junto al nombre de archivo de la nueva llamada en la [!DNL User] columna y haga clic en **[!UICONTROL Save to]** > *&lt;**[!UICONTROL working profile name]**>*.

