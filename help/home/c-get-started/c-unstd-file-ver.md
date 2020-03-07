---
description: El escritorio facilita la determinación de dónde se almacena cada espacio de trabajo concreto, ya sea en el servidor del Área de trabajo de datos, en el equipo local o en ambos.
solution: Analytics
title: Versiones de archivos
topic: Data workbench
uuid: 5e7430f3-1425-41d2-828b-bc8f5786bf3b
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Versiones de archivos{#file-versioning}

El escritorio facilita la determinación de dónde se almacena cada espacio de trabajo concreto, ya sea en el servidor del Área de trabajo de datos, en el equipo local o en ambos.

## Identificación de versiones de archivos {#section-d555c96b016344f19b356c12213dd2a9}

**Servidor**

Un espacio de trabajo de servidor se almacena en el servidor del Área de trabajo de datos conectado y está disponible para todos los usuarios que tengan acceso a este perfil y esta ficha. Un espacio de trabajo de servidor se muestra como una sola miniatura.

![](assets/wsp_thumb_server.png)

Los espacios de trabajo del servidor se almacenan de forma predeterminada en la subcarpeta correspondiente de la carpeta Workspaces del servidor del Área de trabajo de datos conectado.

**Local**

Un espacio de trabajo local es la versión local de un espacio de trabajo de servidor. Un espacio de trabajo local se muestra como dos miniaturas superpuestas. La miniatura de la parte superior está inicialmente rodeada por un resplandor, lo que indica que los cambios recientes se han realizado localmente en el espacio de trabajo del servidor. Este resplandor se disipa con el tiempo.

![](assets/wsp_thumb_local.png)

Los espacios de trabajo locales se almacenan de forma predeterminada en la carpeta [!DNL User\working profile name\Workspaces\tab] name del directorio de instalación de Área de trabajo de datos (o Insight).

>[!NOTE]
>
>Cuando tiene una versión local de un espacio de trabajo de servidor, debe volver a la versión de servidor para poder descargar una versión actualizada del espacio de trabajo de servidor. Para volver a la versión del servidor sin cambios locales, haga clic con el botón secundario en la miniatura del espacio de trabajo local y haga clic en **[!UICONTROL Revert to server version]**.

**Usuario**

Un espacio de trabajo de usuario es un espacio de trabajo que se creó en el equipo local y que sólo existe en él. Un espacio de trabajo de usuario se muestra como una sola miniatura con un contorno de puntos de un espacio de trabajo en blanco detrás de él, lo que indica que no hay espacio de trabajo de origen en el servidor del Área de trabajo de datos conectado.

![](assets/wsp_thumb_user.png)

Los espacios de trabajo del usuario se almacenan de forma predeterminada en la carpeta User\*nombre de perfil de trabajo*\Workspaces\*nombre de ficha* del directorio de instalación de Insight.
