---
description: Pasos para cambiar la visualización predeterminada.
title: Configuración de la interfaz de esquema del conjunto de datos
uuid: 953909e8-3382-43cf-98c0-d4785c6d1dda
exl-id: 0227663f-4789-4780-b753-d0deb35f6144
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '265'
ht-degree: 4%

---

# Configuración de la interfaz de esquema del conjunto de datos{#configure-the-dataset-schema-interface}

{{eol}}

Pasos para cambiar la visualización predeterminada.

Puede controlar qué tipo de visualización aparece al hacer clic en un nombre de dimensión en una [!DNL Dataset Schema Interface] añadiendo archivos a la carpeta Profiles\*profile name*\Context\Dimension Legend de la carpeta de instalación del servidor de Data Workbench. La variable [!DNL Default.1d] en esta carpeta controla el tipo de visualización predeterminado para todas las dimensiones. Al agregar una *nombre de dimensión* Archivo .1d (por ejemplo, [!DNL Hour.1d]) a esta carpeta, puede controlar la visualización predeterminada para esa dimensión en particular.

Para obtener más información, consulte [!DNL Dataset Schema Interfaces], consulte [Interfaz de esquema de conjunto de datos](../../../home/c-get-started/c-admin-intrf/c-dtst-sch-intrf.md#concept-e147b3a5b542453ca2b121e1c85bb175).

**Cambiar la visualización predeterminada**

1. En cualquier espacio de trabajo, cree una visualización que contenga los datos que desea que aparezcan en la nueva visualización predeterminada.

   Por ejemplo, si desea que la dimensión se muestre en un gráfico de barras, cree una visualización de gráfico de barras que muestre la métrica y la dimensión deseadas.

1. Haga clic con el botón derecho en el borde superior de la ventana de llamada y haga clic en **[!UICONTROL Save]**.
1. En el [!DNL Save] ventana, haga clic en ![](assets/btn_folder_up.png), doble clic **[!UICONTROL Context]** y, a continuación, haga doble clic en **[!UICONTROL Dimension Legend]**.
1. En el [!DNL File Name] , escriba el nombre de la dimensión.

   El nombre del [!DNL .1d] debe coincidir exactamente con el nombre de la dimensión. Por ejemplo, [!DNL Hour.1d].

1. Cambie la extensión de archivo a &quot;1d&quot; y haga clic en **[!UICONTROL Save]**.

   El archivo se guarda en la carpeta User\*working profile name*\Context\Dimension Legend .

   La próxima vez que haga clic en esa dimensión desde en una [!DNL Dataset Schema Interface], se muestra la visualización que ha especificado.

1. (Opcional) Para que este cambio esté disponible para todos los usuarios del perfil de trabajo:

   1. En el [!DNL Profile Manager], haga clic en **[!UICONTROL Context]** y haga clic en **[!UICONTROL Dimension Legend]**.

   1. Haga clic con el botón derecho en la marca de verificación situada junto al nombre de archivo de la nueva llamada en la [!DNL User] y haga clic en **[!UICONTROL Save to]** > *&lt;**[!UICONTROL working profile name]**>*.
