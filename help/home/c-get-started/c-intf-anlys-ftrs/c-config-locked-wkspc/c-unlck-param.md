---
description: El parámetro Desbloquear del archivo Insight.cfg de un usuario especifica si el usuario tiene permiso para desbloquear temporalmente los espacios de trabajo bloqueados para editarlos.
title: Definición del parámetro de desbloqueo
uuid: db094e32-7d82-4f93-a492-a6bed33ae722
exl-id: 5eda919f-4cfe-4692-9dbf-f7cf64fde1de
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '215'
ht-degree: 3%

---

# Definición del parámetro de desbloqueo{#set-the-unlock-parameter}

El parámetro Desbloquear del archivo Insight.cfg de un usuario especifica si el usuario tiene permiso para desbloquear temporalmente los espacios de trabajo bloqueados para editarlos.

Si el parámetro Desbloquear ya está presente en el archivo [!DNL Insight.cfg] del usuario, puede editar el parámetro mediante la Data Workbench . Si no está presente en el archivo [!DNL Insight.cfg] del usuario, debe agregarlo al archivo con un editor de texto, como el Bloc de notas.

**Para establecer un  [!DNL Unlock] parámetro existente en el archivo Insight.cfg**

1. En un espacio de trabajo, haga clic con el botón derecho en **[!UICONTROL Admin]** > **[!UICONTROL Client Configuration]**. Se abre el archivo [!DNL Insight.cfg].
1. Para el parámetro Desbloquear , escriba true o false. True permite al usuario desbloquear temporalmente cualquier espacio de trabajo bloqueado, mientras que false no lo hace.
1. Para guardar los cambios de configuración, haga clic con el botón derecho en **[!UICONTROL Insight.cfg (modified)]** en la parte superior de la ventana y haga clic en **[!UICONTROL Save as Insight.cfg]**.

**Para añadir el parámetro Desbloquear al archivo Insight.cfg**

1. Vaya al directorio de instalación de la Data Workbench y abra el archivo [!DNL Insight.cfg] utilizando un editor de texto, como el Bloc de notas.
1. Añada el parámetro Unlock al final del archivo, como en el siguiente ejemplo:

[!DNL Unlock = bool: false]

1. Establezca el valor en true o false. True permite al usuario desbloquear temporalmente cualquier espacio de trabajo bloqueado, mientras que false no lo hace.
1. Guarde y cierre el archivo.
