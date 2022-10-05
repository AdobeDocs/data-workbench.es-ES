---
description: Estos pasos se aplican únicamente a la creación de submenús y elementos de menú para el menú Ventana de Workspace.
title: Creación de un menú de espacio de trabajo y un elemento de menú
uuid: 9565fe7a-fa4c-42b6-9aa5-b652a2d62796
exl-id: 26f2b85c-ab23-41a4-bf4b-9e507952fede
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '503'
ht-degree: 3%

---

# Creación de un menú de espacio de trabajo y un elemento de menú{#create-a-workspace-menu-and-menu-item}

{{eol}}

Estos pasos se aplican únicamente a la creación de submenús y elementos de menú para el menú Ventana de Workspace.

Puede personalizar los menús de métricas y dimensiones creando nuevas carpetas y nuevas métricas y dimensiones derivadas. Para obtener más información, consulte [Creación y edición de métricas derivadas](../../../../home/c-get-started/c-admin-intrf/c-prof-mgr/c-drvd-mtrcs.md#concept-e41723b342a849309874b26232224a40) y [Creación y edición de Dimension derivados](../../../../home/c-get-started/c-admin-intrf/c-prof-mgr/c-dvrd-dim.md#concept-ece3c3ea8cdf4fc796680173993bff93).

**Creación de un nuevo menú de ventana de espacio de trabajo**

1. En el [!DNL Profile Manager], haga clic en **[!UICONTROL Menu]** para ver su contenido.
1. En el [!DNL User] para el directorio Menu , haga clic en **[!UICONTROL Create]** > **[!UICONTROL Folder]**. Aparece una carpeta denominada Nueva carpeta en la [!DNL File] para [!DNL Menu].

   >[!NOTE]
   >
   >También puede crear una nueva carpeta para cualquier subdirectorio dentro del directorio Menu .

1. Cambie el nombre de la nueva carpeta haciendo clic con el botón derecho en la [!DNL User] para la carpeta y escriba el nuevo nombre en el parámetro Dir .
1. Agregue los archivos deseados a la nueva carpeta.
1. (Opcional) En la [!DNL User] para la nueva carpeta, haga clic en **[!UICONTROL Create]** > **[!UICONTROL order.txt]**.

   Un [!DNL order.txt] El archivo aparece en la sección [!DNL File] para la nueva carpeta y aparecerá una marca de verificación para el nuevo archivo en la [!DNL User] para abrir el Navegador.

1. (Opcional) Edite el [!DNL order.txt] según sea necesario. Consulte [Personalización de menús mediante archivos Order.txt](../../../../home/c-get-started/c-intf-anlys-ftrs/c-ctm-menus/t-cstm-menus-ordr-files.md#task-a391800a8dd444deb3e1516d5189f999).
1. (Opcional) Para que los cambios estén disponibles para todos los usuarios del perfil de trabajo, haga clic con el botón derecho en la marca de verificación blanca de la carpeta en la [!DNL User] y haga clic en **[!UICONTROL Save Directory to]** > *&lt;**[!UICONTROL working profile name]**>*.

**Adición de un nuevo elemento de menú a un menú existente**

1. Complete uno de los siguientes pasos:

   * Cree un nuevo elemento (visualización, anotación, etc.) para agregarlo a un menú:

      1. Abra un espacio de trabajo en Data Workbench y cree el elemento deseado.
      1. Guarde el elemento en el siguiente directorio:

         *Directorio de instalación de Data Workbench*\Usuario\*nombre de perfil de trabajo*\Trabajo

      1. En el [!DNL Profile Manager], haga clic en **[!UICONTROL Work]** para ver su contenido.
      1. En el [!DNL User] , haga clic con el botón derecho en la marca de verificación del archivo deseado y haga clic en **[!UICONTROL Copy]**.
      1. En el [!DNL User] para la carpeta deseada, haga clic en **[!UICONTROL Paste]**.

         Una copia del archivo aparece en el [!DNL File] para la nueva carpeta y aparecerá una marca de verificación para el nuevo archivo en la [!DNL User] para abrir el Navegador.
   * Copie y pegue un elemento existente de un menú (carpeta) a otro:

      1. En el [!DNL Profile Manager], haga clic en **[!UICONTROL Menu]** para ver su contenido.
      1. En el *nombre del perfil de trabajo* , haga clic con el botón derecho en la marca de verificación del archivo deseado y haga clic en **[!UICONTROL Make Local]**.
      1. Haga clic con el botón derecho en la marca de verificación del archivo en la [!DNL User] y haga clic en **[!UICONTROL Copy]**.
      1. En el [!DNL User] para la carpeta deseada, haga clic en **[!UICONTROL Paste]**. Una copia del archivo aparece en el [!DNL File] para la nueva carpeta y aparecerá una marca de verificación para el nuevo archivo en la [!DNL User] para abrir el Navegador.


1. (Opcional) Edite el [!DNL order.txt] según sea necesario. Consulte [Personalización de menús mediante archivos Order.txt](../../../../home/c-get-started/c-intf-anlys-ftrs/c-ctm-menus/t-cstm-menus-ordr-files.md#task-a391800a8dd444deb3e1516d5189f999).
1. (Opcional) Para que los cambios estén disponibles para todos los usuarios del perfil de trabajo, haga clic con el botón derecho en la marca de verificación blanca de cada archivo de la variable [!DNL User] y haga clic en **[!UICONTROL Save to]** > *&lt;**[!UICONTROL working profile name]**>*.
1. (Opcional) Para evitar que un elemento de menú aparezca en varios menús, debe eliminar el archivo correspondiente de su carpeta original haciendo clic con el botón derecho en la marca de verificación del archivo en la *nombre del perfil de trabajo* y haga clic en **[!UICONTROL Remove]** > **[!UICONTROL Yes]**.

   Repita este paso para la marca de verificación del archivo en el [!DNL User] para abrir el Navegador.
