---
description: Insight Server está disponible en dos tipos de licencia.
solution: Insight
title: Acerca de las unidades de licencia de Insight Server
uuid: e6a48b00-4dc1-416c-9039-01c01b86abbf
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Acerca de las unidades de licencia de Insight Server{#about-insight-server-license-units}

Insight Server está disponible en dos tipos de licencia.

A continuación se indican los dos tipos de licencia:

* [Unidad de procesamiento de datos (DPU)](../../../home/c-inst-svr/c-install-ins-svr/c-abt-inst-svr-lic-units.md#section-bf589e13cf5c43a58f8f85a457de6f65)
* [Unidad de servidor de archivos (FSU)](../../../home/c-inst-svr/c-install-ins-svr/c-abt-inst-svr-lic-units.md#section-8f3a5c8521a34913bbed10f5794b1a0a)

## Unidad de procesamiento de datos (DPU) {#section-bf589e13cf5c43a58f8f85a457de6f65}

Este tipo de datos [!DNL Insight Server] puede procesar, almacenar y proporcionar datos desde un conjunto de datos de Adobe. Opcionalmente, puede almacenar los archivos de registro que contienen los datos de origen a partir de los cuales se construye el conjunto de datos, o puede recibir esos datos de una unidad de servidor de [!DNL Insight Server] archivos (FSU). Un DPU es el tipo de [!DNL Insight Server] interacción directa entre [!DNL Insight] y [!DNL Report] los clientes.

Si va a instalar una [!DNL Insight Server] DPU, consulte Procedimientos [de instalación para una DPU](../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/t-install-proc-inst-svr-dpu.md#task-ce1ac85294604467ab750b24176d25bc)de Insight Server.

## Unidad de servidor de archivos (FSU) {#section-8f3a5c8521a34913bbed10f5794b1a0a}

Este tipo de servidor está configurado para recibir y almacenar datos de eventos de una o más instancias de replicación de datos [!DNL Sensor] o de eventos ( [!DNL Repeater] funcionalidad proporcionada con una licencia de uso especial) y transmitir los datos a una o más unidades de procesamiento [!DNL Insight Server] de datos (DPU) para construir conjuntos de datos de Adobe. Las DPU se comunican con una FSU mediante un protocolo que optimiza la transferencia de datos de eventos al DPU y es mucho más rápido que mantener archivos de registro en servidores de archivos ordinarios. El uso de una FSU también reduce los costos de hardware al permitir que los datos de registro se almacenen en hardware de almacenamiento de menor costo y reduce la complejidad administrativa al permitir que varios [!DNL Sensors] apunten a un solo [!DNL Insight Server].

Si va a instalar una [!DNL Insight Server] FSU, consulte Procedimientos [de instalación de una FSU](../../../home/c-inst-svr/c-install-ins-svr/t-inst-proc-fsu.md#task-e4a4a791b6694119ba45b36f3e573016)de Insight Server.
