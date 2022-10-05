---
description: El Administrador de perfiles muestra todos los directorios asociados con su perfil de trabajo.
title: Creación de un administrador de perfiles
uuid: e16741e2-740b-4f57-861d-e2f57d30abbc
exl-id: 43b95473-ab3e-4a80-9b91-7c221e74b096
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '390'
ht-degree: 2%

---

# Creación de un administrador de perfiles{#create-a-profile-manager}

{{eol}}

El Administrador de perfiles muestra todos los directorios asociados con su perfil de trabajo.

Puede que desee acceder a un subdirectorio de la variable [!DNL Profile Manager] sin tener que navegar por toda su estructura de directorios. Por ejemplo, la variable [!DNL Metrics] y [!DNL Workspaces] opciones de menú disponibles en [!DNL Manage] del menú de la ventana del espacio de trabajo, permite abrir las carpetas Métricas y Espacios de trabajo del Administrador de perfiles , respectivamente.

Para obtener más información sobre la variable [!DNL Profile Manager], consulte [Administrador de perfiles](https://experienceleague.adobe.com/docs/data-workbench/using/client/ui-analysis-features/cstm-prof-files-mgrs/c-new-prof-mgrs.html).

De forma predeterminada, tiene acceso a los siguientes administradores:

* **[!DNL Metrics Manager]:** Muestra el contenido de la carpeta Métricas del Administrador de perfiles . Puede abrir, editar, eliminar o copiar las métricas definidas en cada perfil.
* **[!DNL Reports Manager]:** Muestra el contenido de la carpeta Informes del Administrador de perfiles. Puede abrir, editar, quitar o copiar espacios de trabajo del informe o [!DNL report.cfg] archivos.

* **[!DNL Workspaces Manager]:** Muestra el contenido de la carpeta Workspaces del Administrador de perfiles. Todos los archivos para configurar la variable [!DNL Worktop]Las pestañas de se encuentran aquí. Consulte [Personalización de las fichas de escritorio](../../../../home/c-get-started/c-intf-anlys-ftrs/c-cstm-wktp-tabs/c-cstm-wktp-tabs.md).

La Data Workbench permite crear administradores de perfil adicionales que muestren un subdirectorio desde el [!DNL Profile Manager]. Cada administrador que cree debe tener un [!DNL .vw] archivo que especifica la variable [!DNL Profile Manager] directorio cuyo contenido muestra y las propiedades de esa ventana. Puede usar la variable [!DNL .vw] para cualquiera de los administradores proporcionados como plantilla.

**Para crear un administrador de perfiles**

1. En el [!DNL Profile Manager], haga clic en **[!UICONTROL Menu]** para ver su contenido.
1. En el directorio Menu , haga clic en el **[!UICONTROL Admin]** y luego el **[!UICONTROL Profile]** directorio. La variable [!DNL .vw] los archivos para los administradores existentes se encuentran aquí.
1. En el *nombre de perfil* , haga clic con el botón derecho en la marca de verificación de una de las [!DNL .vw] archivos (por ejemplo, [!DNL Workspaces.vw]) y, a continuación, haga clic en **[!UICONTROL Make Local]**.

   Aparece una marca de verificación para el archivo en la variable [!DNL User] para abrir el Navegador.

1. Haga clic con el botón derecho en la marca de verificación de la variable [!DNL .vw] en el [!DNL User] y haga clic en **[!UICONTROL Open]** > **[!UICONTROL in Notepad]**.
1. En el [!DNL Profile Path] , escriba la variable [!DNL Profile Manager] para el que desea crear un nuevo administrador. Asegúrese de incluir la barra diagonal (/) después del nombre del directorio.

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

1. En el Bloc de notas, haga clic en **[!UICONTROL File]** > **[!UICONTROL Save As]** para guardar el archivo editado en el *carpeta de instalación de Data Workbench*\Usuario\*nombre de perfil de trabajo*\Menu\Admin\Profile Management.

   Asegúrese de cambiar el nombre del [!DNL .vw] para reflejar el directorio en la variable [!DNL Profile Manager] al que corresponde.

1. (Opcional) Para que los cambios estén disponibles para todos los usuarios del perfil de trabajo, haga clic con el botón derecho en la marca de verificación de [!DNL .vw] en el [!DNL User] y haga clic en **[!UICONTROL Save to]** > &lt; **[!UICONTROL working profile name]**>.
