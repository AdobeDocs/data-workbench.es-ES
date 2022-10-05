---
description: Actualización de los componentes del servidor para la Data Workbench 6.1 de la instalación 5.4.
title: Actualización del servidor DWB de 5.4 a 5.5
uuid: 9cf9f493-f098-4c6d-a8b5-786833496557
exl-id: dd8c2a89-6a40-4ebf-a964-eb4851ab94a5
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '192'
ht-degree: 2%

---

# Actualización del servidor DWB: de 5.4 a 5.5{#dwb-server-upgrade-to}

{{eol}}

Actualización de los componentes del servidor para la Data Workbench 6.1 de la instalación 5.4.

Por lo tanto, actualizar desde [!DNL Insight] De 5.4 a [!DNL Insight] 5.5 es relativamente sencillo.

También puede actualizar directamente desde [!DNL Insight] De 5.3 a [!DNL Insight] 5.5 siguiendo los pasos a continuación. Asegúrese de realizar todas las tareas de actualización enumeradas en la [Actualización de Insight 5.4 a 5.5](../../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/t-upgrd-to-5.5.md#task-b581e47952e941158d52db3e68f076b9) y [Actualización de Insight 5.4 a 5.5](../../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/t-upgrd-to-5.5.md#task-b581e47952e941158d52db3e68f076b9) para obtener más información.

1. Detenga el [!DNL Insight Server] servicios en todos los servidores del clúster excepto en el [!DNL Insight Master Server].

   1. Copie el nuevo [!DNL ReportServer.exe] y [!DNL Insight.exe] a la carpeta Software\Insight .

   1. Después de la [!DNL Insight] el cliente se ha actualizado, copie el [!DNL InsightServer.exe] y [!DNL InsightServer64.exe] en la carpeta \Bin.

   1. Espere a que se [!DNL Insight Master Server] para empezar, compruebe la versión que se está ejecutando mediante el [!DNL Connections] visualización.

1. En el [!DNL Master Server] en el [!DNL Insight] cliente:

   1. Crear una copia local de la [!DNL Base] y renómbrale (por ejemplo, BaseBackup).
   1. Copie el nuevo [!DNL Base] a la carpeta Perfiles.
   1. Repita estos dos pasos para la carpeta Transform .

1. Copie la carpeta Scripts del paquete de servidor en el [!DNL Master Server] en el directorio de instalación del servidor.
1. Copie el [!DNL Terrain Images.cfg.off] en la carpeta Componentes de [!DNL Master Server].
   **Para actualizar el software cliente desde [!DNL Insight] 5.4 a 5.5**

En el [!DNL Insight.cfg] , asegúrese de que la configuración Actualizar software está establecida en TRUE.
