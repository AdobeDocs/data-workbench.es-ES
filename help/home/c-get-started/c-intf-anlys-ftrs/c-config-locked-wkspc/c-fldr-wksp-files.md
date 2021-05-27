---
description: Dentro de la carpeta Workspaces del directorio de instalación de la Data Workbench, un archivo folder.lock especifica si los espacios de trabajo de esa carpeta en particular están bloqueados, mientras que un archivo name.lock de espacio de trabajo especifica si un espacio de trabajo en particular está bloqueado.
title: Archivos Folder.lock y Workspace.lock
uuid: d4c69e16-0596-4542-854f-bc614167ae80
exl-id: 980b8692-8aa5-481f-b6bc-33836d8a3a76
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '601'
ht-degree: 1%

---

# Archivos Folder.lock y Workspace.lock{#folder-lock-and-workspace-lock-files}

Dentro de la carpeta Workspaces del directorio de instalación de la Data Workbench, un archivo folder.lock especifica si los espacios de trabajo de esa carpeta en particular están bloqueados, mientras que un archivo name.lock de espacio de trabajo especifica si un espacio de trabajo en particular está bloqueado.

Al bloquear carpetas enteras, puede bloquearlas en el nivel de carpeta Workspaces o en el nivel de subcarpeta (ficha). También puede bloquear o desbloquear todas las carpetas (en el nivel de carpeta Workspaces) y, a continuación, especificar las excepciones para subcarpetas concretas (mediante archivos [!DNL folder.lock]) o espacios de trabajo concretos (mediante archivos *workspace name*.lock).

El siguiente ejemplo de [!DNL Profile Manager] resalta tres elementos:

* Un archivo [!DNL folder.lock] para la carpeta principal de Workspaces
* Un archivo [!DNL Monthly Numbers.lock] para el archivo de espacio de trabajo [!DNL Monthly Numbers.vw]

* Un archivo [!DNL folder.lock] para la subcarpeta Workspaces\Custom

![](assets/wsp_Locking_lockFiles.png)

En este ejemplo, el archivo [!DNL Workspaces folder.lock] se establece como bloqueado, lo que bloquea todos los espacios de trabajo en esta instancia de Data Workbench. El archivo [!DNL folder.lock] de subcarpeta Workspaces\Custom está definido como desbloqueado, lo que desbloquea todos los espacios de trabajo de la ficha [!DNL Custom]. Por último, el archivo [!DNL Monthly Numbers.lock] se configura como bloqueado, lo que bloquea el espacio de trabajo Números mensuales .

## Creación de archivos .lock {#section-c4f78b4b43c347368a376904effb41d2}

Puede crear un archivo [!DNL new folder.lock] utilizando la opción [!DNL Create menu] en [!DNL Profile Manager] o en [!DNL Workspaces Manager]. También puede crear un archivo [!DNL folder.lock] o *nombre del espacio de trabajo*.lock copiando y pegando un archivo [!DNL .lock] existente en la carpeta adecuada, cambiando el nombre del archivo (solo para *nombre del espacio de trabajo*.lock) y cambiando la configuración del archivo si es necesario.

**Para crear un nuevo archivo folder.lock**

1. En la Data Workbench, abra [!DNL Workspaces Manager] haciendo clic con el botón derecho en un espacio de trabajo y haciendo clic en **[!UICONTROL Manage]** > **[!UICONTROL Profile]** > **[!UICONTROL Workspaces Manager]**.
1. Haga clic en la carpeta para la que desea crear un archivo [!DNL folder.lock].
1. En la columna [!DNL User] de esa carpeta, haga clic con el botón derecho en la celda y haga clic en **[!UICONTROL Create]** > **[!UICONTROL folder.lock]**. Aparece un archivo [!DNL new folder.lock]. [!DNL New folder.lock] de forma predeterminada, los archivos se establecen en  [] unlocked.
1. (Opcional) Si necesita cambiar la configuración en el archivo:

   1. Haga clic con el botón derecho en la marca de verificación del archivo.
   1. Haga clic **[!UICONTROL Open]** > **[!UICONTROL in Notepad]**. Se abre el archivo [!DNL folder.lock].

   1. Cambie la configuración a [locked].
   1. Guarde y cierre el archivo.

1. Para que esta sea la configuración de todos los usuarios que trabajen con el mismo perfil de trabajo, haga clic con el botón derecho en la marca de verificación del archivo y haga clic en **[!UICONTROL Save to]** > *&lt;**[!UICONTROL working profile name]**>*.

Los espacios de trabajo de esta carpeta ahora están bloqueados o desbloqueados según la configuración del nuevo archivo.

**Para crear un archivo .lock a partir de un archivo existente**

1. En [!DNL Profile Manager] o [!DNL Workspaces Manager], haga clic con el botón derecho en la marca de verificación de un archivo [!DNL .lock] existente y haga clic en **[!UICONTROL Copy]**.
1. En la columna [!DNL User] de la carpeta en la que desea pegar el archivo [!DNL .lock], haga clic con el botón derecho en la celda y haga clic en **[!UICONTROL Paste]**.
1. Si este archivo se utiliza para bloquear un espacio de trabajo individual, haga clic con el botón derecho en la marca de verificación del archivo [!DNL .lock] en la columna [!DNL User] y cambie su nombre en el campo [!DNL File] para que coincida con el nombre del espacio de trabajo que desea bloquear.

   Por ejemplo, para bloquear el espacio de trabajo [!DNL Monthly Numbers.vw], debe asignar al archivo el nombre &quot;[!DNL Monthly Numbers.lock]&quot;.Si este archivo se utiliza para bloquear un espacio de trabajo individual, haga clic con el botón derecho en la marca de verificación del archivo [!DNL .lock] en la columna [!DNL User] y cambie su nombre en el campo [!DNL File] para que coincida con el nombre del espacio de trabajo que desea bloquear. Por ejemplo, para bloquear el espacio de trabajo [!DNL Monthly Numbers.vw], debe asignar al archivo el nombre &quot;[!DNL Monthly Numbers.lock]&quot;.

1. Para cambiar la configuración en el archivo:

   1. Haga clic con el botón derecho en la marca de verificación del archivo.
   1. Haga clic **[!UICONTROL Open]** > **[!UICONTROL in Notepad]**. Se abre el archivo [!DNL .lock].

   1. Cambie la configuración a [locked] o [unlocked].
   1. Guarde y cierre el archivo.

1. Para que esta sea la configuración de todos los usuarios que trabajen con el mismo perfil de trabajo, haga clic con el botón derecho en la marca de verificación del archivo y haga clic en **[!UICONTROL Save to]** > *&lt;**[!UICONTROL working profile name]**>*.

Los espacios de trabajo seleccionados ahora están bloqueados o desbloqueados según la configuración del nuevo archivo.
