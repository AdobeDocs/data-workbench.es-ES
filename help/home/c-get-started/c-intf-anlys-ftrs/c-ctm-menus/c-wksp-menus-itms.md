---
description: Estos pasos solo se aplican a la creación de submenús y elementos de menú para el menú Ventana de Workspace.
solution: Analytics
title: Creación de un menú de área de trabajo y un elemento de menú
topic: Data workbench
uuid: 9565fe7a-fa4c-42b6-9aa5-b652a2d62796
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Creación de un menú de área de trabajo y un elemento de menú{#create-a-workspace-menu-and-menu-item}

Estos pasos solo se aplican a la creación de submenús y elementos de menú para el menú Ventana de Workspace.

Puede personalizar los menús de métricas y dimensiones creando nuevas carpetas y nuevas métricas y dimensiones derivadas. Para obtener más información, consulte [Creación y edición de métricas](../../../../home/c-get-started/c-admin-intrf/c-prof-mgr/c-drvd-mtrcs.md#concept-e41723b342a849309874b26232224a40) derivadas y [Creación y edición de dimensiones](../../../../home/c-get-started/c-admin-intrf/c-prof-mgr/c-dvrd-dim.md#concept-ece3c3ea8cdf4fc796680173993bff93)derivadas.

**Creación de un nuevo menú de ventana de espacio de trabajo**

1. En el [!DNL Profile Manager], haga clic en el **[!UICONTROL Menu]** directorio para ver su contenido.
1. En la [!DNL User] columna del directorio Menu, haga clic en **[!UICONTROL Create]** > **[!UICONTROL Folder]**. Aparece una carpeta con el nombre Nueva carpeta en la [!DNL File] columna para [!DNL Menu].

   >[!NOTE]
   >
   >También puede crear una nueva carpeta para cualquier subdirectorio dentro del directorio Menu.

1. Para cambiar el nombre de la nueva carpeta, haga clic con el botón secundario en la columna de la carpeta y escriba el nuevo nombre en el parámetro Dir. [!DNL User]
1. Agregue los archivos deseados a la nueva carpeta.
1. (Opcional) En la columna de la [!DNL User] nueva carpeta, haga clic en **[!UICONTROL Create]** > **[!UICONTROL order.txt]**.

   Aparece un [!DNL order.txt] archivo en la [!DNL File] columna de la nueva carpeta y en la [!DNL User] columna aparece una marca de verificación para el nuevo archivo.

1. (Opcional) Edite el [!DNL order.txt] archivo según sea necesario. Consulte [Personalización de menús con archivos](../../../../home/c-get-started/c-intf-anlys-ftrs/c-ctm-menus/t-cstm-menus-ordr-files.md#task-a391800a8dd444deb3e1516d5189f999)Order.txt.
1. (Opcional) Para que los cambios estén disponibles para todos los usuarios del perfil de trabajo, haga clic con el botón derecho en la marca de verificación blanca de la carpeta en la [!DNL User] columna y haga clic en **[!UICONTROL Save Directory to]** > *&lt;**[!UICONTROL working profile name]**>*.

**Adición de un nuevo elemento de menú a un menú existente**

1. Complete uno de los siguientes pasos:

   * Cree un nuevo elemento (visualización, anotación, etc.) para agregarlo a un menú:

      1. Abra un espacio de trabajo en Área de trabajo de datos y cree el elemento deseado.
      1. Guarde el elemento en el siguiente directorio:

         *Directorio* de instalación del área de trabajo de datos \User\*nombre del perfil de trabajo*\Trabajo

      1. En el [!DNL Profile Manager], haga clic en el **[!UICONTROL Work]** directorio para ver su contenido.
      1. En la [!DNL User] columna, haga clic con el botón secundario en la marca de verificación del archivo deseado y haga clic en **[!UICONTROL Copy]**.
      1. In the [!DNL User] column for the desired folder, click **[!UICONTROL Paste]**.

         Aparece una copia del archivo en la [!DNL File] columna de la nueva carpeta y en la [!DNL User] columna aparece una marca de verificación para el nuevo archivo.
   * Copie y pegue un elemento existente de un menú (carpeta) a otro:

      1. En el [!DNL Profile Manager], haga clic en el **[!UICONTROL Menu]** directorio para ver su contenido.
      1. En la columna del nombre *del perfil de* trabajo, haga clic con el botón secundario en la marca de verificación del archivo deseado y haga clic en **[!UICONTROL Make Local]**.
      1. Haga clic con el botón secundario en la marca de verificación del archivo en la [!DNL User] columna y haga clic en **[!UICONTROL Copy]**.
      1. In the [!DNL User] column for the desired folder, click **[!UICONTROL Paste]**. Aparece una copia del archivo en la [!DNL File] columna de la nueva carpeta y en la [!DNL User] columna aparece una marca de verificación para el nuevo archivo.


1. (Opcional) Edite el [!DNL order.txt] archivo según sea necesario. Consulte [Personalización de menús con archivos](../../../../home/c-get-started/c-intf-anlys-ftrs/c-ctm-menus/t-cstm-menus-ordr-files.md#task-a391800a8dd444deb3e1516d5189f999)Order.txt.
1. (Opcional) Para que los cambios estén disponibles para todos los usuarios del perfil de trabajo, haga clic con el botón derecho en la marca de verificación blanca de cada archivo de la [!DNL User] columna y haga clic en **[!UICONTROL Save to]** > *&lt;**[!UICONTROL working profile name]**>*.
1. (Opcional) Para evitar que un elemento de menú aparezca en varios menús, debe eliminar el archivo correspondiente de su carpeta original haciendo clic con el botón derecho en la marca de verificación del archivo en la columna del nombre *del perfil de* trabajo y haciendo clic en **[!UICONTROL Remove]** > **[!UICONTROL Yes]**.

   Repita este paso para la marca de verificación del archivo en la [!DNL User] columna.

