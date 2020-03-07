---
description: De forma predeterminada, las fichas recién creadas muestran las subcarpetas dentro del directorio asociado como subdirectorios jerárquicos y desplegables en lugar de como subfichas.
solution: Analytics
title: Mostrar subcarpetas como subfichas
topic: Data workbench
uuid: b4d7c6dd-d5ad-4b93-ba67-65a69e11eefc
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Mostrar subcarpetas como subfichas{#display-subfolders-as-subtabs}

De forma predeterminada, las fichas recién creadas muestran las subcarpetas dentro del directorio asociado como subdirectorios jerárquicos y desplegables en lugar de como subfichas.

Puede mostrar las subcarpetas como subfichas (como se muestra en el ejemplo siguiente) colocando un [!DNL empty folder.useTabs] archivo en el nombre del perfil de *trabajo*\Workspaces\*carpeta de nombre de ficha* dentro del directorio de instalación de Área de trabajo de datos.

El ejemplo siguiente muestra la ficha [!DNL Custom] con subdirectorios desplegables.

![](assets/client-sub.png)

Si coloca un [!DNL empty folder.useTabs] archivo en la carpeta Workspaces\Custom, todas las subcarpetas de la carpeta Custom se muestran en las subfichas [!DNL Worktop] , como se muestra en el siguiente ejemplo:

![](assets/client-sub2.png)

**Para mostrar las subcarpetas como subfichas en la variable[!DNL Worktop]**

>[!NOTE]
>
>Cada nivel de directorio debe tener un [!DNL Tab Name.useTabs] archivo para que el contenido de la subcarpeta aparezca como subfichas en lugar de como subdirectorios jerárquicos y desplegables.

1. En el [!DNL Profile Manager], haga clic **[!UICONTROL Workspaces]** para ver su contenido.
1. En la columna del nombre *del perfil de* trabajo, haga clic con el botón secundario en la marca de verificación de uno de los [!DNL folder.useTabs] archivos y haga clic en **[!UICONTROL Copy]**.
1. Haga clic con el botón secundario en la columna de la carpeta Workspaces\*nombre de ficha* y haga clic en [!DNL User] **[!UICONTROL Paste]**. Las subcarpetas dentro de esa ficha ahora se muestran como subfichas.
1. (Opcional) Para que este cambio esté disponible para todos los usuarios del perfil de trabajo, haga clic con el botón derecho en la marca de verificación blanca del [!DNL new folder.useTabs] archivo en la [!DNL User] columna y haga clic en **[!UICONTROL Save to]** > &lt; **[!UICONTROL working profile name]**>.

