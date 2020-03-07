---
description: El parámetro Desbloquear del archivo Insight.cfg de un usuario especifica si ese usuario tiene permiso para desbloquear temporalmente los espacios de trabajo bloqueados para editarlos.
solution: Analytics
title: Definir el parámetro de desbloqueo
topic: Data workbench
uuid: db094e32-7d82-4f93-a492-a6bed33ae722
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Definir el parámetro de desbloqueo{#set-the-unlock-parameter}

El parámetro Desbloquear del archivo Insight.cfg de un usuario especifica si ese usuario tiene permiso para desbloquear temporalmente los espacios de trabajo bloqueados para editarlos.

Si el parámetro Desbloquear ya está presente en el archivo [!DNL Insight.cfg] del usuario, puede editarlo mediante Área de trabajo de datos. Si aún no está presente en el archivo del usuario, debe agregarlo al [!DNL Insight.cfg] archivo con un editor de texto, como el Bloc de notas.

**Para establecer un[!DNL Unlock]parámetro existente en el archivo Insight.cfg**

1. En un espacio de trabajo, haga clic con el botón derecho **[!UICONTROL Admin]** > **[!UICONTROL Client Configuration]**. Se abre el [!DNL Insight.cfg] archivo.
1. Para el parámetro Desbloquear, escriba true o false. True permite al usuario desbloquear temporalmente cualquier espacio de trabajo bloqueado, mientras que false no lo hace.
1. Para guardar los cambios de configuración, haga clic con el botón derecho **[!UICONTROL Insight.cfg (modified)]** en la parte superior de la ventana y haga clic en **[!UICONTROL Save as Insight.cfg]**.

**Para agregar el parámetro Desbloquear al archivo Insight.cfg**

1. Vaya al directorio de instalación de Área de trabajo de datos y abra el [!DNL Insight.cfg] archivo con un editor de texto, como el Bloc de notas.
1. Agregue el parámetro Desbloquear al final del archivo, como en el ejemplo siguiente:

[!DNL Unlock = bool: false]

1. Establezca el valor en true o false. True permite al usuario desbloquear temporalmente cualquier espacio de trabajo bloqueado, mientras que false no lo hace.
1. Guarde y cierre el archivo.

