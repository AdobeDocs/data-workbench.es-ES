---
description: El parámetro Desbloquear del archivo Insight.cfg de un usuario especifica si el usuario tiene permiso para desbloquear temporalmente los espacios de trabajo bloqueados para editarlos.
title: Definición del parámetro de desbloqueo
uuid: db094e32-7d82-4f93-a492-a6bed33ae722
exl-id: 5eda919f-4cfe-4692-9dbf-f7cf64fde1de
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '215'
ht-degree: 3%

---

# Definición del parámetro de desbloqueo{#set-the-unlock-parameter}

{{eol}}

El parámetro Desbloquear del archivo Insight.cfg de un usuario especifica si el usuario tiene permiso para desbloquear temporalmente los espacios de trabajo bloqueados para editarlos.

Si el parámetro Desbloquear ya está presente en la sección [!DNL Insight.cfg] , puede editar el parámetro mediante la Data Workbench . Si no está presente en el informe [!DNL Insight.cfg] , debe agregarlo al archivo utilizando un editor de texto, como el Bloc de notas.

**Para establecer una [!DNL Unlock] en el archivo Insight.cfg**

1. En un espacio de trabajo, haga clic con el botón derecho **[!UICONTROL Admin]** > **[!UICONTROL Client Configuration]**. La variable [!DNL Insight.cfg] se abre.
1. Para el parámetro Desbloquear , escriba true o false. True permite al usuario desbloquear temporalmente cualquier espacio de trabajo bloqueado, mientras que false no lo hace.
1. Para guardar los cambios de configuración, haga clic con el botón derecho del ratón **[!UICONTROL Insight.cfg (modified)]** en la parte superior de la ventana y haga clic en **[!UICONTROL Save as Insight.cfg]**.

**Para añadir el parámetro Desbloquear al archivo Insight.cfg**

1. Vaya al directorio de instalación de la Data Workbench y abra la [!DNL Insight.cfg] utilizando un editor de texto, como el Bloc de notas.
1. Añada el parámetro Unlock al final del archivo, como en el siguiente ejemplo:

[!DNL Unlock = bool: false]

1. Establezca el valor en true o false. True permite al usuario desbloquear temporalmente cualquier espacio de trabajo bloqueado, mientras que false no lo hace.
1. Guarde y cierre el archivo.
