---
description: Puede utilizar el Administrador de perfiles para descargar los archivos que desee modificar.
solution: Analytics
title: Modificación de archivos locales en el perfil de usuario
topic: Data workbench
uuid: 839417d1-34db-4b14-a103-8f5297af55b7
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Modificación de archivos locales en el perfil de usuario{#modify-local-files-in-the-user-profile}

Puede utilizar el Administrador de perfiles para descargar los archivos que desee modificar.

Es posible que desee descargar un archivo para sobrescribir el archivo local existente con la versión original del archivo o abrir, ver y modificar archivos a los que no se puede acceder desde los menús del área de trabajo.

**Para descargar un archivo**

1. En la carpeta [!DNL Profile Manager], abra las carpetas y subcarpetas necesarias para localizar el archivo que desea descargar.
1. Haga clic con el botón derecho en la marca de verificación situada junto al nombre del archivo y haga clic en **[!UICONTROL Make Local]**.

   >[!NOTE]
   >
   >Los archivos de configuración ( [!DNL .cfg]), dimensión ( [!DNL .dim]) y métrica ( [!DNL .metric]) se pueden editar directamente en una carpeta de perfil y guardar en el servidor sin convertirlos en locales y guardarlos por separado en el servidor. Simplemente haga clic con el botón derecho en la marca de verificación situada junto al nombre del archivo y haga clic **[!UICONTROL Open]** > **en la estación de trabajo**.

Después de descargar el archivo en el equipo local, aparece una marca de verificación en la [!DNL User] columna, que indica que una copia local del archivo reside en la carpeta User\*profile name* del equipo. Tenga en cuenta que la marca de verificación tiene el mismo color que la marca de verificación de la columna del nombre *del* perfil. Esto indica que el archivo local tiene la misma fecha y hora de modificación que el archivo de la carpeta del nombre *del* perfil.

**Para modificar el archivo**

1. Haga clic con el botón secundario en la marca de verificación situada junto al nombre del archivo en la [!DNL User] columna.
1. Haga clic en una de las siguientes opciones de menú, según cómo desee editar el archivo:

   * **[!UICONTROL Open]** > **[!UICONTROL in workstation]** si está editando un [!DNL .vw] archivo o un [!DNL .cfg] archivo en un espacio de trabajo.

   * **Abra** > **en vw. Editor **si está editando un archivo .vw para agregar nuevos parámetros.

   * **[!UICONTROL Open]** > **[!UICONTROL In Notepad]** si va a abrir un archivo de texto o necesita agregar parámetros nuevos a un [!DNL .cfg] archivo.

   * **[!UICONTROL Open]** > **[!UICONTROL folder]** si desea abrir la carpeta en la que se encuentra el archivo en el equipo

1. Edite el archivo como desee y luego guárdelo.

En la [!DNL Profile Manager], tenga en cuenta que la marca de verificación de la [!DNL User] columna del archivo que ha editado ha cambiado de color. Esto indica que el archivo local ahora es diferente de la versión de la carpeta de nombres *de* perfil. Si es necesario, puede publicar la versión revisada del archivo en el perfil para que lo utilicen otros usuarios que trabajen con este perfil.
