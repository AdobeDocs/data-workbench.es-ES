---
description: El Administrador de archivos del servidor muestra todos los directorios del directorio de instalación del servidor de Área de trabajo de datos, incluidos los archivos de configuración y de búsqueda.
solution: Analytics
title: Crear un Administrador de archivos de servidor
topic: Data workbench
uuid: 9fb2163d-3756-40d2-9817-4a89bd8a38c9
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Crear un Administrador de archivos de servidor{#create-a-server-files-manager}

El Administrador de archivos del servidor muestra todos los directorios del directorio de instalación del servidor de Área de trabajo de datos, incluidos los archivos de configuración y de búsqueda.

Es posible que desee acceder a una parte de la sección [!DNL Server Files Manager] sin tener que navegar por toda la estructura de directorio o mostrar sólo algunos de los subdirectorios para abordar una necesidad concreta. Por ejemplo, es posible que desee crear un subdirectorio independiente [!DNL Server Files Manager] que muestre únicamente los subdirectorios Control de acceso y Usuarios, permitiéndole administrar los usuarios y su acceso.

Cada administrador que cree debe tener un [!DNL .vw] archivo. Puede utilizar el [!DNL Server Files.vw] archivo como plantilla.

Para obtener más información sobre el [!DNL Server Files Manager], consulte [El Administrador](../../../../home/c-get-started/c-admin-intrf/c-svr-files-mgr.md#concept-73a0808487c8424285ae7302f53bc5f4)de archivos del servidor.

**Para crear un Administrador de archivos de servidor**

1. En el [!DNL Profile Manager], haga clic en el **[!UICONTROL Menu]** directorio y, a continuación, en el **[!UICONTROL Admin]** directorio. El [!DNL Server Files.vw] archivo se encuentra aquí.
1. En la columna *del nombre* del perfil, haga clic con el botón secundario en la marca de verificación del [!DNL Server Files.vw] archivo y haga clic en **[!UICONTROL Make Local]**. En la [!DNL User] columna aparece una marca de verificación para el archivo.
1. Haga clic con el botón secundario en la marca de verificación del [!DNL Server Files.vw] archivo en la [!DNL User] columna y haga clic en **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**. Se abre el [!DNL Server Files.vw] archivo.
1. Para eliminar un directorio, haga clic con el botón derecho en el borde superior del [!DNL Server Files Manager] y haga clic en **[!UICONTROL Server Directories]** > **[!UICONTROL Remove]** > *&lt;**[!UICONTROL directory name]**>*.
1. Para agregar un directorio, haga clic con el botón derecho en el borde superior del [!DNL Server Files Manager], haga clic en **[!UICONTROL Server Directories]** > **[!UICONTROL Add]** > **[!UICONTROL Directory]**.

   Escriba el URI del directorio en el campo URI y haga clic en **[!UICONTROL OK]**.

   >[!NOTE]
   >
   >Puede designar varios directorios en el campo URI. Por ejemplo, si escribe [!DNL Profiles\Marketing\], el administrador de archivos del servidor contendrá el subdirectorio Marketing, pero no otro subdirectorio dentro del directorio Perfiles.

1. Haga clic con el botón derecho en la parte superior del borde superior del [!DNL Server Files Manager] y haga clic en **[!UICONTROL Save]**.
1. Para crear un nuevo administrador, cambie el nombre del archivo en el [!DNL File Name] campo y haga clic en **[!UICONTROL Save]**. Para sobrescribir el administrador existente, haga clic en **[!UICONTROL Save]**.
1. (Opcional) Para que los cambios estén disponibles para todos los usuarios del perfil de trabajo, haga clic con el botón secundario en la marca de verificación del [!DNL .vw] archivo de la [!DNL User] columna.

   A continuación, debe hacer clic en **[!UICONTROL Save to]** > *&lt;**[!UICONTROL working profile name]**>*.

