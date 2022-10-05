---
description: El parámetro Bytes de muestra del archivo Server.cfg especifica el tamaño de la caché de datos (en bytes) para Data Workbench.
title: Server.cfg
uuid: 7e789133-09fc-442d-b643-cca8620f4a97
exl-id: fb7667f6-4061-4bde-8a48-6489b24e0411
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '114'
ht-degree: 1%

---

# Server.cfg{#server-cfg}

{{eol}}

El parámetro Bytes de muestra del archivo Server.cfg especifica el tamaño de la caché de datos (en bytes) para Data Workbench.

El valor predeterminado es 250e6. Instrucciones para abrir y guardar el [!DNL Server.cfg] son los mismos que para [!DNL Log Processing Mode.cfg]. Consulte [Log Processing Mode.cfg](../../../home/c-dataset-const-proc/c-add-config-files/t-log-proc-mode.md#task-e530907cb34f488182afe625e6d9e44a).

>[!NOTE]
>
>Dado que el parámetro de este archivo afecta al rendimiento del sistema, póngase en contacto con el Adobe antes de realizar cualquier cambio.

Puede limitar aún más el tamaño de la caché de datos para el equipo de Data Workbench que se conecta al servidor de Data Workbench estableciendo el parámetro Tamaño máximo de muestra en la variable [!DNL Insight.cfg] archivo. Para obtener más información, consulte la *Guía del usuario de Data Workbench*.
