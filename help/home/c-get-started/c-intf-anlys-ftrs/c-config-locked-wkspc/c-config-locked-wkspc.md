---
description: El Área de trabajo de datos se puede configurar para permitir que solo determinados usuarios cambien ciertas áreas de trabajo.
solution: Analytics
title: Configuración de un espacio de trabajo bloqueado
topic: Data workbench
uuid: 0bb264f6-20b9-43d9-903e-1b2422af21d5
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Configuración de un espacio de trabajo bloqueado{#configure-a-locked-workspace}

El Área de trabajo de datos se puede configurar para permitir que solo determinados usuarios cambien ciertas áreas de trabajo.

Mientras un espacio de trabajo está bloqueado, los usuarios pueden realizar selecciones en la mayoría de las visualizaciones y ordenar los datos en tablas, pero de lo contrario no pueden cambiar el espacio de trabajo. Esta funcionalidad evita que los usuarios realicen cambios no intencionales en los espacios de trabajo.

Los tres elementos siguientes funcionan juntos para controlar el bloqueo de espacios de trabajo:

* **Un archivo folder.lock o *Workspace name*.lock:** Un [!DNL folder.lock] archivo especifica si los espacios de trabajo de una carpeta en particular están bloqueados, mientras que un [!DNL name.lock] archivo de espacio de trabajo especifica si un espacio de trabajo en particular está bloqueado.

* **El parámetro Desbloquear del[!DNL Insight.cfg]archivo de un usuario:** Este parámetro especifica si el usuario puede desbloquear temporalmente espacios de trabajo bloqueados.
* **La opción de menú Desbloquear temporalmente:** Cuando el parámetro Desbloquear en el menú del usuario [!DNL Insight.cfg] se establece en true, esta opción aparece automáticamente en el menú de la barra de título de cada espacio de trabajo bloqueado para proporcionar al usuario una manera de desbloquearlo.

Para obtener información sobre [!DNL folder.lock] y los archivos de espacio de trabajo [!DNL name.lock] , consulte la siguiente sección. Para obtener información sobre la configuración del parámetro Desbloquear, consulte [Configuración del parámetro](../../../../home/c-get-started/c-intf-anlys-ftrs/c-config-locked-wkspc/c-unlck-param.md#concept-b018a85c6217489aa01b17845872df7f)Desbloquear. Para obtener información sobre la [!DNL Temporarily Unlock menu] opción, consulte [Desbloqueo de un espacio de trabajo](../../../../home/c-get-started/c-work-worksp/c-unlock-wksp.md#concept-18ada952aecf45c79a806b31b294023e).
