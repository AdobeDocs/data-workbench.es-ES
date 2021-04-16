---
description: Insight Server está disponible en dos tipos de licencias.
title: Acerca de las unidades de licencia de Insight Server
uuid: e6a48b00-4dc1-416c-9039-01c01b86abbf
exl-id: 82d6fa29-d36e-480d-a975-f5a5e60a32d2
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '239'
ht-degree: 7%

---

# Acerca de las unidades de licencia de Insight Server{#about-insight-server-license-units}

Insight Server está disponible en dos tipos de licencias.

A continuación se indican los dos tipos de licencia:

* [Unidad de procesamiento de datos (DPU)](../../../home/c-inst-svr/c-install-ins-svr/c-abt-inst-svr-lic-units.md#section-bf589e13cf5c43a58f8f85a457de6f65)
* [Unidad de servidor de archivos (FSU)](../../../home/c-inst-svr/c-install-ins-svr/c-abt-inst-svr-lic-units.md#section-8f3a5c8521a34913bbed10f5794b1a0a)

## Unidad de procesamiento de datos (DPU) {#section-bf589e13cf5c43a58f8f85a457de6f65}

Este tipo de [!DNL Insight Server] puede procesar, almacenar y servir datos de un conjunto de datos de Adobe. Opcionalmente, puede almacenar los archivos de registro que contienen los datos de origen desde los que se construye el conjunto de datos, o puede recibir esos datos de una [!DNL Insight Server] Unidad de servidor de archivos (FSU). Una DPU es el tipo de [!DNL Insight Server] con el que los clientes [!DNL Insight] y [!DNL Report] interactúan directamente.

Si está instalando una DPU [!DNL Insight Server], consulte [Procedimientos de instalación para una DPU de Insight Server](../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/t-install-proc-inst-svr-dpu.md#task-ce1ac85294604467ab750b24176d25bc).

## Unidad de servidor de archivos (FSU) {#section-8f3a5c8521a34913bbed10f5794b1a0a}

Este tipo de servidor está configurado para recibir y almacenar datos de evento de una o más [!DNL Sensor] instancias de replicación de datos de evento ( [!DNL Repeater] funcionalidad proporcionada con una licencia de uso especial) y transmitir los datos a una o más [!DNL Insight Server] unidades de procesamiento de datos (DPU) para construir conjuntos de datos de Adobe. Las DPU se comunican con una FSU mediante un protocolo que optimiza la transferencia de datos de evento a la DPU y es considerablemente más rápida que mantener archivos de registro en servidores de archivos normales. El uso de una FSU también reduce los costos de hardware al permitir que los datos de registro se almacenen en hardware de almacenamiento de menor costo y reduce la complejidad administrativa al permitir que múltiples [!DNL Sensors] apunten a un único [!DNL Insight Server].

Si está instalando una FSU [!DNL Insight Server], consulte [Procedimientos de instalación para una FSU de Insight Server](../../../home/c-inst-svr/c-install-ins-svr/t-inst-proc-fsu.md#task-e4a4a791b6694119ba45b36f3e573016).
