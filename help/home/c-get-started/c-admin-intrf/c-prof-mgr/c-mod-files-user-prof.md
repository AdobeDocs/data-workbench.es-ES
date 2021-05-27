---
description: Puede utilizar el Administrador de perfiles para descargar los archivos que desee modificar.
title: Modificación de archivos locales en el perfil del usuario
uuid: 839417d1-34db-4b14-a103-8f5297af55b7
exl-id: 187d67a1-e436-4bfd-87ad-17b6c70dbee4
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '388'
ht-degree: 3%

---

# Modificación de archivos locales en el perfil del usuario{#modify-local-files-in-the-user-profile}

Puede utilizar el Administrador de perfiles para descargar los archivos que desee modificar.

Puede que desee descargar un archivo para sobrescribir el archivo local existente con la versión original del archivo o abrir, ver y modificar archivos a los que no se puede acceder desde los menús del espacio de trabajo.

**Para descargar un archivo**

1. En [!DNL Profile Manager], abra las carpetas y subcarpetas necesarias para localizar el archivo que desea descargar.
1. Haga clic con el botón derecho en la marca de verificación situada junto al nombre del archivo y haga clic en **[!UICONTROL Make Local]**.

   >[!NOTE]
   >
   >Los archivos de configuración ( [!DNL .cfg]), dimensión ( [!DNL .dim]) y métrica ( [!DNL .metric]) se pueden editar directamente en una carpeta de perfil y guardar en el servidor sin hacerlos locales y guardarlos por separado en el servidor. Simplemente haga clic con el botón derecho en la marca de verificación situada junto al nombre del archivo y haga clic en **[!UICONTROL Open]** > **en la estación de trabajo**.

Una vez descargado el archivo en el equipo local, aparece una marca de verificación en la columna [!DNL User], que indica que una copia local del archivo reside en la carpeta User\*profile name* del equipo. Tenga en cuenta que la marca de verificación tiene el mismo color que la marca de verificación de la columna *nombre de perfil*. Esto indica que el archivo local tiene la misma fecha y hora de modificación que el archivo de la carpeta *nombre de perfil*.

**Para modificar el archivo**

1. Haga clic con el botón derecho en la marca de verificación situada junto al nombre del archivo en la columna [!DNL User].
1. Haga clic en una de las siguientes opciones de menú, según cómo desee editar el archivo:

   * **[!UICONTROL Open]** >  **[!UICONTROL in workstation]** si está editando un  [!DNL .vw] archivo o un  [!DNL .cfg] archivo en un espacio de trabajo.

   * **Abra**  > **en vw. Editor **si está editando un archivo .vw para agregar nuevos parámetros.

   * **[!UICONTROL Open]** >  **[!UICONTROL In Notepad]** si está abriendo un archivo de texto o necesita añadir nuevos parámetros a un  [!DNL .cfg] archivo.

   * **[!UICONTROL Open]** >  **[!UICONTROL folder]** si desea abrir la carpeta en la que se encuentra el archivo en el equipo

1. Edite el archivo como desee y, a continuación, guarde el archivo.

En [!DNL Profile Manager], tenga en cuenta que la marca de verificación de la columna [!DNL User] del archivo que ha editado ha cambiado de color. Esto indica que el archivo local ahora es diferente de la versión de la carpeta *nombre de perfil*. Si es necesario, puede publicar la versión revisada del archivo en el perfil para que lo utilicen otros usuarios que trabajen con este perfil.
