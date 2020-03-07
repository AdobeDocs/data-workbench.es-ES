---
description: El Administrador de perfiles muestra todos los directorios asociados a su perfil de trabajo.
solution: Analytics
title: Crear un administrador de perfiles
topic: Data workbench
uuid: e16741e2-740b-4f57-861d-e2f57d30abbc
translation-type: tm+mt
source-git-commit: 27600561841db3705f4eee6ff0aeb8890444bbc9

---


# Crear un administrador de perfiles{#create-a-profile-manager}

El Administrador de perfiles muestra todos los directorios asociados a su perfil de trabajo.

Es posible que desee acceder a un subdirectorio del [!DNL Profile Manager] sin tener que navegar por toda la estructura de directorio. Por ejemplo, las opciones de menú [!DNL Metrics] y [!DNL Workspaces] disponibles en el [!DNL Manage] menú de la ventana del espacio de trabajo permiten abrir las carpetas Métricas y Espacios de trabajo del Administrador de perfiles, respectivamente.

Para obtener más información sobre el [!DNL Profile Manager], consulte [El Administrador](https://docs.adobe.com/content/help/en/data-workbench/using/client/ui-analysis-features/cstm-prof-files-mgrs/c-new-prof-mgrs.html)de perfiles.

De forma predeterminada, tiene acceso a los siguientes administradores:

* **[!DNL Metrics Manager]::**Muestra el contenido de la carpeta Métricas del Administrador de perfiles. Puede abrir, editar, eliminar o copiar las métricas definidas en cada perfil.
* **[!DNL Reports Manager]::**Muestra el contenido de la carpeta Informes del Administrador de perfiles. Puede abrir, editar, eliminar o copiar espacios de trabajo o[!DNL report.cfg]archivos de informes.

* **[!DNL Workspaces Manager]::**Muestra el contenido de la carpeta Workspaces del Administrador de perfiles. Aquí se encuentran todos los archivos para configurar las fichas[!DNL Worktop]de. Consulte[Personalización de fichas](../../../../home/c-get-started/c-intf-anlys-ftrs/c-cstm-wktp-tabs/c-cstm-wktp-tabs.md)de escritorio.

Área de trabajo de datos permite crear administradores de perfil adicionales que muestran un subdirectorio desde el [!DNL Profile Manager]. Cada administrador que cree debe tener un [!DNL .vw] archivo que especifique el directorio [!DNL Profile Manager] cuyo contenido muestra y las propiedades de esa ventana. Puede utilizar el [!DNL .vw] archivo para cualquiera de los administradores proporcionados como plantilla.

**Para crear un administrador de perfiles**

1. En el [!DNL Profile Manager], haga clic en el **[!UICONTROL Menu]** directorio para ver su contenido.
1. En el directorio Menu, haga clic en el **[!UICONTROL Admin]** directorio y, a continuación, en el **[!UICONTROL Profile]** directorio. Los [!DNL .vw] archivos de los administradores existentes se encuentran aquí.
1. En la columna del nombre *del* perfil, haga clic con el botón secundario en la marca de verificación de uno de los [!DNL .vw] archivos (por ejemplo, [!DNL Workspaces.vw]) y, a continuación, haga clic en **[!UICONTROL Make Local]**.

   En la [!DNL User] columna aparece una marca de verificación para el archivo.

1. Haga clic con el botón secundario en la marca de verificación del [!DNL .vw] archivo en la [!DNL User] columna y haga clic en **[!UICONTROL Open]** > **[!UICONTROL in Notepad]**.
1. En el [!DNL Profile Path] campo, escriba el [!DNL Profile Manager] directorio para el que desea crear un nuevo administrador. Asegúrese de incluir la barra (/) después del nombre del directorio.

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

1. En el Bloc de notas, haga clic en **[!UICONTROL File]** > **[!UICONTROL Save As]** para guardar el archivo editado en la carpeta *de instalación*&#x200B;Área de trabajo de datos \User\*nombre de perfil de trabajo*\Menu\Admin\Profile Management.

   Asegúrese de cambiar el nombre del [!DNL .vw] archivo para reflejar el directorio en el [!DNL Profile Manager] que corresponde.

1. (Opcional) Para que los cambios estén disponibles para todos los usuarios del perfil de trabajo, haga clic con el botón secundario en la marca de verificación del [!DNL .vw] archivo en la [!DNL User] columna y haga clic en **[!UICONTROL Save to]** > &lt; **[!UICONTROL working profile name]**>.

