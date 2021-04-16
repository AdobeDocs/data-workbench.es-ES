---
description: La Data Workbench se puede configurar para permitir que solo determinados usuarios cambien determinados espacios de trabajo.
title: Configuración de un espacio de trabajo bloqueado
uuid: 0bb264f6-20b9-43d9-903e-1b2422af21d5
exl-id: e31a786e-064e-4f2c-9bf4-7ceafde814c0
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '201'
ht-degree: 3%

---

# Configuración de un espacio de trabajo bloqueado{#configure-a-locked-workspace}

La Data Workbench se puede configurar para permitir que solo determinados usuarios cambien determinados espacios de trabajo.

Mientras un espacio de trabajo está bloqueado, los usuarios pueden realizar selecciones en la mayoría de las visualizaciones y ordenar los datos en tablas, pero de lo contrario no podrán cambiar el espacio de trabajo. Esta funcionalidad evita que los usuarios realicen cambios no intencionales en los espacios de trabajo.

Los tres elementos siguientes funcionan juntos para controlar el bloqueo de espacios de trabajo:

* **Un archivo folder.lock o  *workspace name*.lock:** un  [!DNL folder.lock] archivo especifica si los espacios de trabajo de una carpeta en particular están bloqueados, mientras que un  [!DNL name.lock] archivo de espacio de trabajo especifica si un espacio de trabajo en particular está bloqueado.

* **El parámetro Desbloquear en el  [!DNL Insight.cfg] archivo de un usuario:** este parámetro especifica si el usuario puede desbloquear temporalmente los espacios de trabajo bloqueados.
* **La opción de menú Desbloquear temporalmente:** cuando el parámetro Desbloquear en el del usuario  [!DNL Insight.cfg] está establecido en true, esta opción aparece automáticamente en el menú de barra de título de cada espacio de trabajo bloqueado para proporcionar al usuario una forma de desbloquearlo.

Para obtener información sobre los archivos [!DNL folder.lock] y [!DNL name.lock] del espacio de trabajo, consulte la siguiente sección. Para obtener información sobre la configuración del parámetro Desbloquear, consulte [Configuración del parámetro de desbloqueo](../../../../home/c-get-started/c-intf-anlys-ftrs/c-config-locked-wkspc/c-unlck-param.md#concept-b018a85c6217489aa01b17845872df7f). Para obtener información sobre la opción [!DNL Temporarily Unlock menu], consulte [Desbloquear un espacio de trabajo](../../../../home/c-get-started/c-work-worksp/c-unlock-wksp.md#concept-18ada952aecf45c79a806b31b294023e).
