---
description: De forma predeterminada, las pestañas recién creadas muestran las subcarpetas dentro del directorio asociado como subdirectorios jerárquicos y desplegables en lugar de como subpestañas.
title: Mostrar subcarpetas como subpestañas
uuid: b4d7c6dd-d5ad-4b93-ba67-65a69e11eefc
exl-id: 6a05852b-3efc-4e71-9782-d4cc3a687a26
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '217'
ht-degree: 3%

---

# Mostrar subcarpetas como subpestañas{#display-subfolders-as-subtabs}

{{eol}}

De forma predeterminada, las pestañas recién creadas muestran las subcarpetas dentro del directorio asociado como subdirectorios jerárquicos y desplegables en lugar de como subpestañas.

Puede mostrar las subcarpetas como subfichas (como se muestra en el siguiente ejemplo) colocando una [!DNL empty folder.useTabs] en el *nombre del perfil de trabajo*\Workspaces\*carpeta de nombre de ficha* dentro del directorio de instalación de la Data Workbench.

El siguiente ejemplo muestra la variable [!DNL Custom] con subdirectorios desplegables.

![](assets/client-sub.png)

Si coloca un [!DNL empty folder.useTabs] en la carpeta Workspaces\Custom , todas las subcarpetas de la carpeta Custom se muestran en la [!DNL Worktop] como subpestañas, como se muestra en el siguiente ejemplo:

![](assets/client-sub2.png)

**Para mostrar las subcarpetas como subfichas en la variable[!DNL Worktop]**

>[!NOTE]
>
>Cada nivel de directorio debe tener un [!DNL Tab Name.useTabs] para que el contenido de la subcarpeta aparezca como subpestañas en lugar de como subdirectorios jerárquicos y desplegables.

1. En el [!DNL Profile Manager], haga clic en **[!UICONTROL Workspaces]** para ver su contenido.
1. En el *nombre del perfil de trabajo* , haga clic con el botón derecho en la marca de verificación de una de las [!DNL folder.useTabs] archivos y haga clic en **[!UICONTROL Copy]**.
1. Haga clic con el botón derecho en la [!DNL User] para la carpeta Workspaces\*nombre de ficha* y haga clic en **[!UICONTROL Paste]**. Las subcarpetas de esa ficha ahora se muestran como subfichas.
1. (Opcional) Para que este cambio esté disponible para todos los usuarios del perfil de trabajo, haga clic con el botón derecho en la marca de verificación blanca de la variable [!DNL new folder.useTabs] en el [!DNL User] y haga clic en **[!UICONTROL Save to]** > &lt; **[!UICONTROL working profile name]**>.
