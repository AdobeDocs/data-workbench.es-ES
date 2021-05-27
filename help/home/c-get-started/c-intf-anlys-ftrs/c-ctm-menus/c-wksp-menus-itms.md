---
description: Estos pasos se aplican únicamente a la creación de submenús y elementos de menú para el menú Ventana de Workspace.
title: Creación de un menú de espacio de trabajo y un elemento de menú
uuid: 9565fe7a-fa4c-42b6-9aa5-b652a2d62796
exl-id: 26f2b85c-ab23-41a4-bf4b-9e507952fede
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '503'
ht-degree: 3%

---

# Creación de un menú de espacio de trabajo y un elemento de menú{#create-a-workspace-menu-and-menu-item}

Estos pasos se aplican únicamente a la creación de submenús y elementos de menú para el menú Ventana de Workspace.

Puede personalizar los menús de métricas y dimensiones creando nuevas carpetas y nuevas métricas y dimensiones derivadas. Para obtener más información, consulte [Creación y edición de métricas derivadas](../../../../home/c-get-started/c-admin-intrf/c-prof-mgr/c-drvd-mtrcs.md#concept-e41723b342a849309874b26232224a40) y [Creación y edición de Dimension derivados](../../../../home/c-get-started/c-admin-intrf/c-prof-mgr/c-dvrd-dim.md#concept-ece3c3ea8cdf4fc796680173993bff93).

**Creación de un nuevo menú de ventana de espacio de trabajo**

1. En [!DNL Profile Manager], haga clic en el directorio **[!UICONTROL Menu]** para ver su contenido.
1. En la columna [!DNL User] del directorio Menu, haga clic en **[!UICONTROL Create]** > **[!UICONTROL Folder]**. Aparece una carpeta denominada Nueva carpeta en la columna [!DNL File] de [!DNL Menu].

   >[!NOTE]
   >
   >También puede crear una nueva carpeta para cualquier subdirectorio dentro del directorio Menu .

1. Para cambiar el nombre de la nueva carpeta, haga clic con el botón derecho en la columna [!DNL User] de la carpeta y escriba el nuevo nombre en el parámetro Dir.
1. Agregue los archivos deseados a la nueva carpeta.
1. (Opcional) En la columna [!DNL User] de la nueva carpeta, haga clic en **[!UICONTROL Create]** > **[!UICONTROL order.txt]**.

   Aparece un archivo [!DNL order.txt] en la columna [!DNL File] de la nueva carpeta y en la columna [!DNL User] aparece una marca de verificación para el nuevo archivo.

1. (Opcional) Edite el archivo [!DNL order.txt] según sea necesario. Consulte [Personalización de menús mediante archivos Order.txt](../../../../home/c-get-started/c-intf-anlys-ftrs/c-ctm-menus/t-cstm-menus-ordr-files.md#task-a391800a8dd444deb3e1516d5189f999).
1. (Opcional) Para que los cambios estén disponibles para todos los usuarios del perfil de trabajo, haga clic con el botón derecho en la marca de verificación blanca de la carpeta en la columna [!DNL User] y haga clic en **[!UICONTROL Save Directory to]** > *&lt;**[!UICONTROL working profile name]**>*.

**Adición de un nuevo elemento de menú a un menú existente**

1. Complete uno de los siguientes pasos:

   * Cree un nuevo elemento (visualización, anotación, etc.) para agregarlo a un menú:

      1. Abra un espacio de trabajo en Data Workbench y cree el elemento deseado.
      1. Guarde el elemento en el siguiente directorio:

         *Directorio de instalación de Data Workbench*\User\*nombre del perfil de trabajo*\Trabajo

      1. En [!DNL Profile Manager], haga clic en el directorio **[!UICONTROL Work]** para ver su contenido.
      1. En la columna [!DNL User] , haga clic con el botón derecho en la marca de verificación del archivo deseado y haga clic en **[!UICONTROL Copy]**.
      1. En la columna [!DNL User] de la carpeta deseada, haga clic en **[!UICONTROL Paste]**.

         En la columna [!DNL File] de la nueva carpeta aparece una copia del archivo y en la columna [!DNL User] aparece una marca de verificación para el nuevo archivo.
   * Copie y pegue un elemento existente de un menú (carpeta) a otro:

      1. En [!DNL Profile Manager], haga clic en el directorio **[!UICONTROL Menu]** para ver su contenido.
      1. En la columna *nombre del perfil de trabajo*, haga clic con el botón derecho en la marca de verificación del archivo deseado y haga clic en **[!UICONTROL Make Local]**.
      1. Haga clic con el botón derecho en la marca de verificación del archivo en la columna [!DNL User] y haga clic en **[!UICONTROL Copy]**.
      1. En la columna [!DNL User] de la carpeta deseada, haga clic en **[!UICONTROL Paste]**. En la columna [!DNL File] de la nueva carpeta aparece una copia del archivo y en la columna [!DNL User] aparece una marca de verificación para el nuevo archivo.


1. (Opcional) Edite el archivo [!DNL order.txt] según sea necesario. Consulte [Personalización de menús mediante archivos Order.txt](../../../../home/c-get-started/c-intf-anlys-ftrs/c-ctm-menus/t-cstm-menus-ordr-files.md#task-a391800a8dd444deb3e1516d5189f999).
1. (Opcional) Para que los cambios estén disponibles para todos los usuarios del perfil de trabajo, haga clic con el botón derecho en la marca de verificación blanca de cada archivo de la columna [!DNL User] y haga clic en **[!UICONTROL Save to]** > *&lt;**[!UICONTROL working profile name]**>*.
1. (Opcional) Para evitar que un elemento de menú aparezca en varios menús, debe eliminar el archivo correspondiente de su carpeta original haciendo clic con el botón derecho en la marca de verificación del archivo en la columna *nombre del perfil de trabajo* y haciendo clic en **[!UICONTROL Remove]** > **[!UICONTROL Yes]**.

   Repita este paso para la marca de verificación del archivo en la columna [!DNL User].
