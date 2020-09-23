---
description: Actualización de los componentes del servidor para la instalación de Data Workbench 6.1 desde la versión 5.4.
solution: Analytics
title: Actualización 5.4 a 5.5 de DWB Server
uuid: 9cf9f493-f098-4c6d-a8b5-786833496557
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '192'
ht-degree: 2%

---


# Actualización del servidor DWB: de 5.4 a 5.5{#dwb-server-upgrade-to}

Actualización de los componentes del servidor para la instalación de Data Workbench 6.1 desde la versión 5.4.

En consecuencia, la actualización de [!DNL Insight] 5.4 a [!DNL Insight] 5.5 es relativamente sencilla.

También puede actualizar directamente de [!DNL Insight] 5.3 a [!DNL Insight] 5.5 siguiendo los pasos a continuación. Asegúrese de realizar todas las tareas de actualización enumeradas en la sección [Actualización de Insight 5.4 a 5.5](../../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/t-upgrd-to-5.5.md#task-b581e47952e941158d52db3e68f076b9) y en la sección [Actualización de Insight 5.4 a 5.5](../../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/t-upgrd-to-5.5.md#task-b581e47952e941158d52db3e68f076b9) .

1. Detenga los [!DNL Insight Server] servicios en todos los servidores del clúster excepto en el [!DNL Insight Master Server].

   1. Copie los nuevos [!DNL ReportServer.exe] y [!DNL Insight.exe] archivos en la carpeta Software\Insight.

   1. Una vez que el [!DNL Insight] cliente se haya actualizado, copie los archivos [!DNL InsightServer.exe] y [!DNL InsightServer64.exe] en la carpeta \Bin.

   1. Espere a que el inicio [!DNL Insight Master Server] se ejecute y, a continuación, compruebe la versión que se está ejecutando mediante la [!DNL Connections] visualización.

1. En el clúster [!DNL Master Server] en el [!DNL Insight] cliente:

   1. Realice una copia local del [!DNL Base] perfil existente y cámbiele el nombre (por ejemplo, BaseBackup).
   1. Copie el nuevo [!DNL Base] perfil en la carpeta Perfiles.
   1. Repita estos dos pasos para la carpeta Transformar.

1. Copie la carpeta Scripts del paquete de servidor en el [!DNL Master Server] directorio de instalación del servidor.
1. Copie el [!DNL Terrain Images.cfg.off] archivo en la carpeta Componentes del [!DNL Master Server].
   **Para actualizar el software cliente de[!DNL Insight]5.4 a 5.5**

En el [!DNL Insight.cfg] archivo, asegúrese de que la configuración Actualizar software está establecida en VERDADERO.
