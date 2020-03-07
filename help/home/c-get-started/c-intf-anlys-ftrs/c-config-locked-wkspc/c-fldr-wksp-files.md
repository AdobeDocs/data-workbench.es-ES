---
description: En la carpeta Workspaces del directorio de instalación de Área de trabajo de datos, un archivo folder.lock especifica si los espacios de trabajo de esa carpeta en particular están bloqueados, mientras que un archivo name.lock de espacio de trabajo especifica si un espacio de trabajo en particular está bloqueado.
solution: Analytics
title: Archivos Folder.lock y Workspace.lock
topic: Data workbench
uuid: d4c69e16-0596-4542-854f-bc614167ae80
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Archivos Folder.lock y Workspace.lock{#folder-lock-and-workspace-lock-files}

En la carpeta Workspaces del directorio de instalación de Área de trabajo de datos, un archivo folder.lock especifica si los espacios de trabajo de esa carpeta en particular están bloqueados, mientras que un archivo name.lock de espacio de trabajo especifica si un espacio de trabajo en particular está bloqueado.

Al bloquear carpetas enteras, puede bloquearlas en el nivel de carpeta Workspaces o en el nivel de subcarpeta (ficha). También puede bloquear o desbloquear todas las carpetas (en el nivel de carpeta Workspaces) y, a continuación, especificar las excepciones para subcarpetas concretas (con [!DNL folder.lock] archivos) o espacios de trabajo concretos (con archivos *de nombre*.lock del espacio de trabajo).

El siguiente ejemplo de [!DNL Profile Manager] resalta tres elementos:

* Un [!DNL folder.lock] archivo para la carpeta Workspaces principal
* Un [!DNL Monthly Numbers.lock] archivo para el archivo del [!DNL Monthly Numbers.vw] espacio de trabajo

* Un [!DNL folder.lock] archivo para la subcarpeta Workspaces\Custom

![](assets/wsp_Locking_lockFiles.png)

En este ejemplo, el [!DNL Workspaces folder.lock] archivo se establece como bloqueado, lo que bloquea todas las áreas de trabajo de esta instancia de Área de trabajo de datos. El archivo de subcarpeta [!DNL folder.lock] Workspaces\Custom se establece en unlocked, lo que desbloquea todos los espacios de trabajo de la [!DNL Custom] ficha. Por último, el [!DNL Monthly Numbers.lock] archivo está bloqueado, lo que bloquea el espacio de trabajo Números mensuales.

## Creación de archivos .lock {#section-c4f78b4b43c347368a376904effb41d2}

Puede crear un [!DNL new folder.lock] archivo con la [!DNL Create menu] opción [!DNL Profile Manager] o [!DNL Workspaces Manager]. También puede crear un archivo name [!DNL folder.lock] .lock *o* espacio de trabajo copiando y pegando un archivo existente en la carpeta correspondiente, cambiando el nombre del archivo (solo para archivos [!DNL .lock] de nombre **.lock) y cambiando la configuración del archivo si es necesario.

**Para crear un nuevo archivo folder.lock**

1. En el Área de trabajo de datos, abra la página haciendo clic con el botón derecho en un espacio de trabajo y haciendo clic en [!DNL Workspaces Manager] > **[!UICONTROL Manage]** > **[!UICONTROL Profile]** **[!UICONTROL Workspaces Manager]**.
1. Haga clic en la carpeta para la que desea crear un [!DNL folder.lock] archivo.
1. En la [!DNL User] columna de esa carpeta, haga clic con el botón derecho en la celda y haga clic en **[!UICONTROL Create]** > **[!UICONTROL folder.lock]**. Aparece un [!DNL new folder.lock] archivo. [!DNL New folder.lock] de forma predeterminada, los archivos se definen como [desbloqueados] .
1. (Opcional) Si necesita cambiar la configuración en el archivo:

   1. Haga clic con el botón secundario en la marca de verificación del archivo.
   1. Haga clic **[!UICONTROL Open]** > **[!UICONTROL in Notepad]**. Se abre el [!DNL folder.lock] archivo.

   1. Cambie la configuración a [bloqueada].
   1. Guarde y cierre el archivo.

1. Para que esta opción sea la configuración de todos los usuarios que trabajen con el mismo perfil de trabajo, haga clic con el botón secundario en la marca de verificación del archivo y haga clic en **[!UICONTROL Save to]** > *&lt;**[!UICONTROL working profile name]**>*.

Los espacios de trabajo de esta carpeta ahora están bloqueados o desbloqueados según la configuración del nuevo archivo.

**Creación de un archivo .lock a partir de un archivo existente**

1. En la casilla [!DNL Profile Manager] o [!DNL Workspaces Manager], haga clic con el botón derecho en la marca de verificación de un [!DNL .lock] archivo existente y haga clic en **[!UICONTROL Copy]**.
1. En la [!DNL User] columna de la carpeta en la que desea pegar el [!DNL .lock] archivo, haga clic con el botón derecho en la celda y haga clic en **[!UICONTROL Paste]**.
1. Si este archivo se utiliza para bloquear un espacio de trabajo individual, haga clic con el botón derecho en la marca de verificación del [!DNL .lock] archivo en la [!DNL User] columna y cambie su nombre en el [!DNL File] campo para que coincida con el nombre del espacio de trabajo que desea bloquear.

   Por ejemplo, para bloquear el [!DNL Monthly Numbers.vw] espacio de trabajo, debe asignar al archivo el nombre &quot; [!DNL Monthly Numbers.lock]&quot;.Si este archivo se utiliza para bloquear un espacio de trabajo individual, haga clic con el botón derecho en la marca de verificación del [!DNL .lock] archivo en la [!DNL User] columna y cambie su nombre en el [!DNL File] campo para que coincida con el nombre del espacio de trabajo que desea bloquear. Por ejemplo, para bloquear el [!DNL Monthly Numbers.vw] espacio de trabajo, debe asignar al archivo el nombre &quot; [!DNL Monthly Numbers.lock]&quot;.

1. Para cambiar la configuración en el archivo:

   1. Haga clic con el botón secundario en la marca de verificación del archivo.
   1. Haga clic **[!UICONTROL Open]** > **[!UICONTROL in Notepad]**. Se abre el [!DNL .lock] archivo.

   1. Cambie la configuración a [bloqueada] o [desbloqueada].
   1. Guarde y cierre el archivo.

1. Para que esta opción sea la configuración de todos los usuarios que trabajen con el mismo perfil de trabajo, haga clic con el botón secundario en la marca de verificación del archivo y haga clic en **[!UICONTROL Save to]** > *&lt;**[!UICONTROL working profile name]**>*.

Los espacios de trabajo seleccionados ahora están bloqueados o desbloqueados según la configuración del nuevo archivo.
