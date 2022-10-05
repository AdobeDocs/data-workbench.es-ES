---
description: La Data Workbench se puede configurar para permitir que solo determinados usuarios cambien determinados espacios de trabajo.
title: Configuración de un espacio de trabajo bloqueado
uuid: 0bb264f6-20b9-43d9-903e-1b2422af21d5
exl-id: e31a786e-064e-4f2c-9bf4-7ceafde814c0
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '201'
ht-degree: 3%

---

# Configuración de un espacio de trabajo bloqueado{#configure-a-locked-workspace}

{{eol}}

La Data Workbench se puede configurar para permitir que solo determinados usuarios cambien determinados espacios de trabajo.

Mientras un espacio de trabajo está bloqueado, los usuarios pueden realizar selecciones en la mayoría de las visualizaciones y ordenar los datos en tablas, pero de lo contrario no podrán cambiar el espacio de trabajo. Esta funcionalidad evita que los usuarios realicen cambios no intencionales en los espacios de trabajo.

Los tres elementos siguientes funcionan juntos para controlar el bloqueo de espacios de trabajo:

* **A folder.lock o *nombre del espacio de trabajo*Archivo .lock:** A [!DNL folder.lock] El archivo especifica si los espacios de trabajo de una carpeta en particular están bloqueados, mientras que un espacio de trabajo [!DNL name.lock] especifica si un espacio de trabajo en particular está bloqueado.

* **El parámetro Desbloquear de un usuario [!DNL Insight.cfg] archivo:** Este parámetro especifica si el usuario puede desbloquear temporalmente espacios de trabajo bloqueados.
* **La opción de menú Desbloquear temporalmente:** Cuando el parámetro Desbloquear en el [!DNL Insight.cfg] se establece en true, esta opción aparece automáticamente en el menú de barra de título de cada espacio de trabajo bloqueado para proporcionar al usuario una forma de desbloquearlo.

Para obtener información sobre [!DNL folder.lock] y espacio de trabajo [!DNL name.lock] , consulte la siguiente sección. Para obtener información sobre cómo configurar el parámetro Desbloquear, consulte [Configuración del parámetro de desbloqueo](../../../../home/c-get-started/c-intf-anlys-ftrs/c-config-locked-wkspc/c-unlck-param.md#concept-b018a85c6217489aa01b17845872df7f). Para obtener información sobre la variable [!DNL Temporarily Unlock menu] , consulte [Desbloquear un espacio de trabajo](../../../../home/c-get-started/c-work-worksp/c-unlock-wksp.md#concept-18ada952aecf45c79a806b31b294023e).
