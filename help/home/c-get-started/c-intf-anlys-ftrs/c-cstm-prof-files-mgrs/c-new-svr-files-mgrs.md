---
description: El Administrador de archivos del servidor muestra todos los directorios del directorio de instalación del servidor de Data Workbench, incluidos los archivos de configuración y búsqueda.
title: Creación de administrador de archivos de servidor
uuid: 9fb2163d-3756-40d2-9817-4a89bd8a38c9
exl-id: 9e0c8144-0f52-4e46-85d8-c2dcd60ddcb8
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '312'
ht-degree: 3%

---

# Creación de administrador de archivos de servidor{#create-a-server-files-manager}

{{eol}}

El Administrador de archivos del servidor muestra todos los directorios del directorio de instalación del servidor de Data Workbench, incluidos los archivos de configuración y búsqueda.

Puede que desee acceder a una parte de la variable [!DNL Server Files Manager] sin tener que navegar por toda su estructura de directorios o mostrar solo unos cuantos subdirectorios para satisfacer una necesidad particular. Por ejemplo, puede que desee crear una [!DNL Server Files Manager] que muestra únicamente los subdirectorios Control de acceso y Usuarios , lo que le permite administrar sus usuarios y su acceso.

Cada administrador que cree debe tener un [!DNL .vw] archivo. Puede usar la variable [!DNL Server Files.vw] como plantilla.

Para obtener más información sobre la variable [!DNL Server Files Manager], consulte [Administrador de archivos del servidor](../../../../home/c-get-started/c-admin-intrf/c-svr-files-mgr.md#concept-73a0808487c8424285ae7302f53bc5f4).

**Para crear un Administrador de archivos de servidor**

1. En el [!DNL Profile Manager], haga clic en **[!UICONTROL Menu]** , luego el **[!UICONTROL Admin]** directorio. La variable [!DNL Server Files.vw] se encuentra aquí.
1. En el *nombre de perfil* , haga clic con el botón derecho en la marca de verificación del [!DNL Server Files.vw] y haga clic en **[!UICONTROL Make Local]**. Aparece una marca de verificación para el archivo en la variable [!DNL User] para abrir el Navegador.
1. Haga clic con el botón derecho en la marca de verificación de la variable [!DNL Server Files.vw] en el [!DNL User] y haga clic en **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**. La variable [!DNL Server Files.vw] se abre.
1. Para quitar un directorio, haga clic con el botón derecho en el borde superior del [!DNL Server Files Manager] y haga clic en **[!UICONTROL Server Directories]** > **[!UICONTROL Remove]** > *&lt;**[!UICONTROL directory name]**>*.
1. Para añadir un directorio, haga clic con el botón derecho en el borde superior del [!DNL Server Files Manager], haga clic en **[!UICONTROL Server Directories]** > **[!UICONTROL Add]** > **[!UICONTROL Directory]**.

   Escriba el URI del directorio en el campo URI y haga clic en **[!UICONTROL OK]**.

   >[!NOTE]
   >
   >Puede designar varios directorios en el campo URI. Por ejemplo, si escribe [!DNL Profiles\Marketing\], el administrador de archivos del servidor contiene el subdirectorio Marketing , pero no hay otro subdirectorio dentro del directorio Profiles .

1. Haga clic con el botón derecho en la parte superior del borde superior del [!DNL Server Files Manager] y haga clic en **[!UICONTROL Save]**.
1. Para crear un nuevo administrador, cambie el nombre de archivo en la [!DNL File Name] y, a continuación, haga clic en **[!UICONTROL Save]**. Para sobrescribir el administrador existente, haga clic en **[!UICONTROL Save]**.
1. (Opcional) Para que los cambios estén disponibles para todos los usuarios del perfil de trabajo, haga clic con el botón derecho en la marca de verificación de [!DNL .vw] en el [!DNL User] para abrir el Navegador.

   A continuación, debe hacer clic en **[!UICONTROL Save to]** > *&lt;**[!UICONTROL working profile name]**>*.
