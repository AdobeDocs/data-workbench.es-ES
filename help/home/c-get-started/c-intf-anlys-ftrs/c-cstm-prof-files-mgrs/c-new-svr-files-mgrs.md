---
description: El Administrador de archivos del servidor muestra todos los directorios del directorio de instalación del servidor de Data Workbench, incluidos los archivos de configuración y búsqueda.
title: Creación de administrador de archivos de servidor
uuid: 9fb2163d-3756-40d2-9817-4a89bd8a38c9
exl-id: 9e0c8144-0f52-4e46-85d8-c2dcd60ddcb8
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '312'
ht-degree: 3%

---

# Creación de administrador de archivos de servidor{#create-a-server-files-manager}

El Administrador de archivos del servidor muestra todos los directorios del directorio de instalación del servidor de Data Workbench, incluidos los archivos de configuración y búsqueda.

Puede que desee acceder a una parte de [!DNL Server Files Manager] sin tener que navegar por toda la estructura de directorios o mostrar solo unos cuantos subdirectorios para satisfacer una necesidad concreta. Por ejemplo, es posible que desee crear un [!DNL Server Files Manager] independiente que muestre únicamente los subdirectorios Control de acceso y Usuarios, lo que le permitirá administrar sus usuarios y su acceso.

Cada administrador que cree debe tener un archivo [!DNL .vw]. Puede utilizar el archivo [!DNL Server Files.vw] como plantilla.

Para obtener más información sobre [!DNL Server Files Manager], consulte [El Administrador de archivos del servidor](../../../../home/c-get-started/c-admin-intrf/c-svr-files-mgr.md#concept-73a0808487c8424285ae7302f53bc5f4).

**Para crear un Administrador de archivos de servidor**

1. En [!DNL Profile Manager], haga clic en el directorio **[!UICONTROL Menu]** y, a continuación, en el directorio **[!UICONTROL Admin]**. El archivo [!DNL Server Files.vw] se encuentra aquí.
1. En la columna *profile name*, haga clic con el botón derecho en la marca de verificación del archivo [!DNL Server Files.vw] y haga clic en **[!UICONTROL Make Local]**. En la columna [!DNL User] aparece una marca de verificación para el archivo.
1. Haga clic con el botón derecho en la marca de verificación del archivo [!DNL Server Files.vw] en la columna [!DNL User] y haga clic en **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**. Se abre el archivo [!DNL Server Files.vw].
1. Para quitar un directorio, haga clic con el botón derecho en el borde superior de [!DNL Server Files Manager] y haga clic en **[!UICONTROL Server Directories]** > **[!UICONTROL Remove]** > *&lt;**[!UICONTROL directory name]**>*.
1. Para añadir un directorio, haga clic con el botón derecho en el borde superior del [!DNL Server Files Manager], haga clic en **[!UICONTROL Server Directories]** > **[!UICONTROL Add]** > **[!UICONTROL Directory]**.

   Escriba el URI del directorio en el campo URI y haga clic en **[!UICONTROL OK]**.

   >[!NOTE]
   >
   >Puede designar varios directorios en el campo URI. Por ejemplo, si escribe [!DNL Profiles\Marketing\], el administrador de archivos del servidor contiene el subdirectorio Marketing , pero no hay otro subdirectorio dentro del directorio Profiles .

1. Haga clic con el botón derecho en la parte superior del borde superior del [!DNL Server Files Manager] y haga clic en **[!UICONTROL Save]**.
1. Para crear un nuevo administrador, cambie el nombre del archivo en el campo [!DNL File Name] y haga clic en **[!UICONTROL Save]**. Para sobrescribir el administrador existente, haga clic en **[!UICONTROL Save]**.
1. (Opcional) Para que los cambios estén disponibles para todos los usuarios del perfil de trabajo, haga clic con el botón derecho en la marca de verificación del archivo [!DNL .vw] en la columna [!DNL User].

   A continuación, debe hacer clic en **[!UICONTROL Save to]** > *&lt;**[!UICONTROL working profile name]**>*.
