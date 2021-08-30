---
description: El Administrador de perfiles muestra todos los directorios asociados con su perfil de trabajo.
title: Creación de un administrador de perfiles
uuid: e16741e2-740b-4f57-861d-e2f57d30abbc
exl-id: 43b95473-ab3e-4a80-9b91-7c221e74b096
source-git-commit: 232117a8cacaecf8e5d7fcaccc5290d6297947e5
workflow-type: tm+mt
source-wordcount: '390'
ht-degree: 2%

---

# Creación de un administrador de perfiles{#create-a-profile-manager}

El Administrador de perfiles muestra todos los directorios asociados con su perfil de trabajo.

Es posible que desee acceder a un subdirectorio de [!DNL Profile Manager] sin tener que desplazarse por toda la estructura de directorios. Por ejemplo, las opciones de menú [!DNL Metrics] y [!DNL Workspaces] disponibles en el menú [!DNL Manage] del menú de la ventana del espacio de trabajo permiten abrir las carpetas Métricas y Espacios de trabajo del Administrador de perfiles, respectivamente.

Para obtener más información sobre [!DNL Profile Manager], consulte [El administrador de perfiles](https://experienceleague.adobe.com/docs/data-workbench/using/client/ui-analysis-features/cstm-prof-files-mgrs/c-new-prof-mgrs.html).

De forma predeterminada, tiene acceso a los siguientes administradores:

* **[!DNL Metrics Manager]:** Muestra el contenido de la carpeta Métricas del Administrador de perfiles. Puede abrir, editar, eliminar o copiar las métricas definidas en cada perfil.
* **[!DNL Reports Manager]:** Muestra el contenido de la carpeta Informes del Administrador de perfiles. Puede abrir, editar, quitar o copiar espacios de trabajo de informes o archivos [!DNL report.cfg].

* **[!DNL Workspaces Manager]:** muestra el contenido de la carpeta Workspaces del Administrador de perfiles. Todos los archivos para configurar las pestañas de [!DNL Worktop] se encuentran aquí. Consulte [Personalización de las fichas de escritorio](../../../../home/c-get-started/c-intf-anlys-ftrs/c-cstm-wktp-tabs/c-cstm-wktp-tabs.md).

La Data Workbench permite crear administradores de perfil adicionales que muestren un subdirectorio desde [!DNL Profile Manager]. Cada administrador que cree debe tener un archivo [!DNL .vw] que especifique el directorio [!DNL Profile Manager] cuyo contenido muestra y las propiedades de esa ventana. Puede utilizar el archivo [!DNL .vw] para cualquiera de los administradores proporcionados como plantilla.

**Para crear un administrador de perfiles**

1. En [!DNL Profile Manager], haga clic en el directorio **[!UICONTROL Menu]** para ver su contenido.
1. Dentro del directorio Menu, haga clic en el directorio **[!UICONTROL Admin]** y luego en el directorio **[!UICONTROL Profile]**. Los archivos [!DNL .vw] para los administradores existentes se encuentran aquí.
1. En la columna *nombre del perfil*, haga clic con el botón derecho en la marca de verificación de uno de los archivos [!DNL .vw] (por ejemplo, [!DNL Workspaces.vw]) y, a continuación, haga clic en **[!UICONTROL Make Local]**.

   En la columna [!DNL User] aparece una marca de verificación para el archivo.

1. Haga clic con el botón derecho en la marca de verificación del archivo [!DNL .vw] en la columna [!DNL User] y haga clic en **[!UICONTROL Open]** > **[!UICONTROL in Notepad]**.
1. En el campo [!DNL Profile Path], escriba el directorio [!DNL Profile Manager] para el que desea crear un nuevo administrador. Asegúrese de incluir la barra diagonal (/) después del nombre del directorio.

   ```
   window = simpleBorderWindow:
   client = scrollWindow: 
   client = fileManager:
     Profile Path = string: directory name/
     size = v3d: (820, 5649, 0)
     scroll_offset = v3d: (0, 0, 0)
     size = v3d: (830, 881, 0)
     pos = v3d: (525, 162, 0)
     size = v3d: (830, 900, 0)
   ```

1. En el Bloc de notas, haga clic en **[!UICONTROL File]** > **[!UICONTROL Save As]** para guardar el archivo editado en la *carpeta de instalación de la Data Workbench*\User\*nombre del perfil de trabajo*\Menu\Admin\Profile Management.

   Asegúrese de cambiar el nombre del archivo [!DNL .vw] para que refleje el directorio en el [!DNL Profile Manager] al que corresponde.

1. (Opcional) Para que los cambios estén disponibles para todos los usuarios del perfil de trabajo, haga clic con el botón derecho en la marca de verificación del archivo [!DNL .vw] en la columna [!DNL User] y haga clic en **[!UICONTROL Save to]** > &lt; **[!UICONTROL working profile name]**.
