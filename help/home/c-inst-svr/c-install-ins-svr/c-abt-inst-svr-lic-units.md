---
description: Insight Server está disponible en dos tipos de licencia.
solution: Analytics
title: Acerca de las unidades de licencia de Insight Server
uuid: e6a48b00-4dc1-416c-9039-01c01b86abbf
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '239'
ht-degree: 7%

---


# Acerca de las unidades de licencia de Insight Server{#about-insight-server-license-units}

Insight Server está disponible en dos tipos de licencia.

A continuación se indican los dos tipos de licencia:

* [Unidad de procesamiento de datos (DPU)](../../../home/c-inst-svr/c-install-ins-svr/c-abt-inst-svr-lic-units.md#section-bf589e13cf5c43a58f8f85a457de6f65)
* [Unidad de servidor de archivos (FSU)](../../../home/c-inst-svr/c-install-ins-svr/c-abt-inst-svr-lic-units.md#section-8f3a5c8521a34913bbed10f5794b1a0a)

## Unidad de procesamiento de datos (DPU) {#section-bf589e13cf5c43a58f8f85a457de6f65}

Este tipo de datos [!DNL Insight Server] puede procesar, almacenar y proporcionar datos desde un conjunto de datos de Adobe. It optionally can store the log files that contain the source data from which the dataset is constructed, or it can receive that data from an [!DNL Insight Server] File Server Unit (FSU). Un DPU es el tipo de [!DNL Insight Server] interacción directa entre [!DNL Insight] y [!DNL Report] los clientes.

Si va a instalar una [!DNL Insight Server] DPU, consulte Procedimientos [de instalación para una DPU](../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/t-install-proc-inst-svr-dpu.md#task-ce1ac85294604467ab750b24176d25bc)de Insight Server.

## Unidad de servidor de archivos (FSU) {#section-8f3a5c8521a34913bbed10f5794b1a0a}

Este tipo de servidor está configurado para recibir y almacenar datos de evento de una o más instancias de replicación de datos de evento [!DNL Sensor] o de uno o más ( [!DNL Repeater] funcionalidad proporcionada con una licencia de uso especial) y transmitir los datos a una o más unidades [!DNL Insight Server] de procesamiento de datos (DPU) para construir conjuntos de datos de Adobe. Los DPU se comunican con un FSU mediante un protocolo que optimiza la transferencia de datos de evento al DPU y es mucho más rápido que mantener archivos de registro en servidores de archivos ordinarios. The use of an FSU also reduces hardware costs by enabling log data to be stored on lower cost storage hardware and reduces administrative complexity by allowing multiple [!DNL Sensors] to point to a single [!DNL Insight Server].

Si va a instalar una [!DNL Insight Server] FSU, consulte Procedimientos [de instalación de una FSU](../../../home/c-inst-svr/c-install-ins-svr/t-inst-proc-fsu.md#task-e4a4a791b6694119ba45b36f3e573016)de Insight Server.
