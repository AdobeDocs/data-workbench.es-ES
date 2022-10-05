---
description: Dentro de la carpeta Workspaces del directorio de instalación de la Data Workbench, un archivo folder.lock especifica si los espacios de trabajo de esa carpeta en particular están bloqueados, mientras que un archivo name.lock de espacio de trabajo especifica si un espacio de trabajo en particular está bloqueado.
title: Archivos Folder.lock y Workspace.lock
uuid: d4c69e16-0596-4542-854f-bc614167ae80
exl-id: 980b8692-8aa5-481f-b6bc-33836d8a3a76
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '601'
ht-degree: 1%

---

# Archivos Folder.lock y Workspace.lock{#folder-lock-and-workspace-lock-files}

{{eol}}

Dentro de la carpeta Workspaces del directorio de instalación de la Data Workbench, un archivo folder.lock especifica si los espacios de trabajo de esa carpeta en particular están bloqueados, mientras que un archivo name.lock de espacio de trabajo especifica si un espacio de trabajo en particular está bloqueado.

Al bloquear carpetas enteras, puede bloquearlas en el nivel de carpeta Workspaces o en el nivel de subcarpeta (ficha). También puede bloquear o desbloquear todas las carpetas (en el nivel de carpeta Workspaces) y luego especificar las excepciones para subcarpetas concretas (mediante [!DNL folder.lock] archivos) o espacios de trabajo concretos (mediante *nombre del espacio de trabajo* archivos .lock).

El siguiente ejemplo de la variable [!DNL Profile Manager] resalta tres elementos:

* A [!DNL folder.lock] para la carpeta Workspaces principal
* A [!DNL Monthly Numbers.lock] para [!DNL Monthly Numbers.vw] archivo de espacio de trabajo

* A [!DNL folder.lock] para la subcarpeta Workspaces\Custom

![](assets/wsp_Locking_lockFiles.png)

En este ejemplo, la variable [!DNL Workspaces folder.lock] está definido como bloqueado, lo que bloquea todos los espacios de trabajo en esta instancia de Data Workbench. La subcarpeta Workspaces\Custom [!DNL folder.lock] está definido como desbloqueado, lo que desbloquea todos los espacios de trabajo del [!DNL Custom] pestaña . Por último, la variable [!DNL Monthly Numbers.lock] está configurado como bloqueado, lo que bloquea el espacio de trabajo Números mensuales .

## Creación de archivos .lock {#section-c4f78b4b43c347368a376904effb41d2}

Puede crear un [!DNL new folder.lock] usando la variable [!DNL Create menu] en la [!DNL Profile Manager] o [!DNL Workspaces Manager]. También puede crear un [!DNL folder.lock] o *nombre del espacio de trabajo*.lock archivo copiando y pegando un [!DNL .lock] a la carpeta adecuada, cambiando el nombre del archivo (para *nombre del espacio de trabajo*.lock (sólo archivos .lock) y cambiando la configuración en el archivo si es necesario.

**Para crear un nuevo archivo folder.lock**

1. En la Data Workbench, abra el [!DNL Workspaces Manager] haciendo clic con el botón derecho en un espacio de trabajo y haciendo clic en **[!UICONTROL Manage]** > **[!UICONTROL Profile]** > **[!UICONTROL Workspaces Manager]**.
1. Haga clic en la carpeta para la que desea crear una [!DNL folder.lock] archivo.
1. En el [!DNL User] para esa carpeta, haga clic con el botón derecho en la celda y haga clic en **[!UICONTROL Create]** > **[!UICONTROL folder.lock]**. A [!DNL new folder.lock] aparece. [!DNL New folder.lock] los archivos están configurados en [desbloqueado] de forma predeterminada.
1. (Opcional) Si necesita cambiar la configuración en el archivo:

   1. Haga clic con el botón derecho en la marca de verificación del archivo.
   1. Haga clic **[!UICONTROL Open]** > **[!UICONTROL in Notepad]**. La variable [!DNL folder.lock] se abre.

   1. Cambie la configuración a [bloqueado].
   1. Guarde y cierre el archivo.

1. Para que esta sea la configuración de todos los usuarios que trabajen con el mismo perfil de trabajo, haga clic con el botón derecho en la marca de verificación del archivo y haga clic en **[!UICONTROL Save to]** > *&lt;**[!UICONTROL working profile name]**>*.

Los espacios de trabajo de esta carpeta ahora están bloqueados o desbloqueados según la configuración del nuevo archivo.

**Para crear un archivo .lock a partir de un archivo existente**

1. En el [!DNL Profile Manager] o [!DNL Workspaces Manager], haga clic con el botón derecho en la marca de verificación de una [!DNL .lock] y haga clic en **[!UICONTROL Copy]**.
1. En el [!DNL User] para la carpeta en la que desea pegar el [!DNL .lock] , haga clic con el botón derecho en la celda y haga clic en **[!UICONTROL Paste]**.
1. Si este archivo se utiliza para bloquear un espacio de trabajo individual, haga clic con el botón derecho en la marca de verificación de [!DNL .lock] en el [!DNL User] y cambie su nombre en [!DNL File] para que coincida con el nombre del espacio de trabajo que desea bloquear.

   Por ejemplo, para bloquear la variable [!DNL Monthly Numbers.vw] espacio de trabajo, el nombre del archivo es &quot; [!DNL Monthly Numbers.lock].&quot;Si este archivo se utiliza para bloquear un espacio de trabajo individual, haga clic con el botón derecho en la marca de verificación de [!DNL .lock] en el [!DNL User] y cambie su nombre en [!DNL File] para que coincida con el nombre del espacio de trabajo que desea bloquear. Por ejemplo, para bloquear la variable [!DNL Monthly Numbers.vw] espacio de trabajo, el nombre del archivo es &quot; [!DNL Monthly Numbers.lock].&quot;

1. Para cambiar la configuración en el archivo:

   1. Haga clic con el botón derecho en la marca de verificación del archivo.
   1. Haga clic **[!UICONTROL Open]** > **[!UICONTROL in Notepad]**. La variable [!DNL .lock] se abre.

   1. Cambie la configuración a [bloqueado] o [desbloqueado].
   1. Guarde y cierre el archivo.

1. Para que esta sea la configuración de todos los usuarios que trabajen con el mismo perfil de trabajo, haga clic con el botón derecho en la marca de verificación del archivo y haga clic en **[!UICONTROL Save to]** > *&lt;**[!UICONTROL working profile name]**>*.

Los espacios de trabajo seleccionados ahora están bloqueados o desbloqueados según la configuración del nuevo archivo.
