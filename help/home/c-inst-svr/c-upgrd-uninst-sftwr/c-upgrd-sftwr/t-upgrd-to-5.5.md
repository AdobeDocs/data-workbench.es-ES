---
description: Actualización de los componentes del servidor para la Data Workbench 6.1 de la instalación 5.4.
title: Actualización del servidor DWB de 5.4 a 5.5
uuid: 9cf9f493-f098-4c6d-a8b5-786833496557
exl-id: dd8c2a89-6a40-4ebf-a964-eb4851ab94a5
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '192'
ht-degree: 2%

---

# Actualización del servidor DWB: de 5.4 a 5.5{#dwb-server-upgrade-to}

Actualización de los componentes del servidor para la Data Workbench 6.1 de la instalación 5.4.

En consecuencia, la actualización de [!DNL Insight] 5.4 a [!DNL Insight] 5.5 es relativamente sencilla.

También puede actualizar directamente de [!DNL Insight] 5.3 a [!DNL Insight] 5.5 siguiendo los pasos a continuación. Asegúrese de realizar todas las tareas de actualización enumeradas en la sección [Actualización de Insight 5.4 a 5.5](../../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/t-upgrd-to-5.5.md#task-b581e47952e941158d52db3e68f076b9) y en la sección [Actualización de Insight 5.4 a 5.5](../../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/t-upgrd-to-5.5.md#task-b581e47952e941158d52db3e68f076b9).

1. Detenga los servicios [!DNL Insight Server] en todos los servidores del clúster excepto en el [!DNL Insight Master Server].

   1. Copie los nuevos archivos [!DNL ReportServer.exe] y [!DNL Insight.exe] a la carpeta Software\Insight .

   1. Una vez actualizado el cliente [!DNL Insight], copie los archivos [!DNL InsightServer.exe] y [!DNL InsightServer64.exe] en la carpeta \Bin.

   1. Espere a que se inicie [!DNL Insight Master Server] y, a continuación, verifique la versión que se está ejecutando mediante la visualización [!DNL Connections].

1. En el [!DNL Master Server] del clúster en el cliente [!DNL Insight]:

   1. Realice una copia local del perfil [!DNL Base] existente y cambie el nombre (por ejemplo, BaseBackup).
   1. Copie el nuevo perfil [!DNL Base] en la carpeta Perfiles .
   1. Repita estos dos pasos para la carpeta Transform .

1. Copie la carpeta Scripts del paquete de servidor en el [!DNL Master Server] directorio de instalación del servidor.
1. Copie el archivo [!DNL Terrain Images.cfg.off] en la carpeta Componentes de [!DNL Master Server].
   **Para actualizar el software cliente de  [!DNL Insight] 5.4 a 5.5**

En el archivo [!DNL Insight.cfg], asegúrese de que la configuración Actualizar software está establecida en TRUE.
