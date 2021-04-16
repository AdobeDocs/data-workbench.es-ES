---
description: La funcionalidad del repetidor permite que una FSU de Insight Server reciba datos de evento adquiridos por el sensor de una o más fuentes y los replique a una o más FSU de Insight Server que ejecuten el servicio de replicación de Insight Server.
title: Configuración de la funcionalidad del repetidor
uuid: 45dca069-a91f-4fd4-bd47-c8c2e6aab834
exl-id: 61b70772-07fb-4963-b09f-6b2cf97b01a1
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '205'
ht-degree: 9%

---

# Configuración de la funcionalidad del repetidor{#configuring-repeater-functionality}

La funcionalidad del repetidor permite que una FSU de Insight Server reciba datos de evento adquiridos por el sensor de una o más fuentes y los replique a una o más FSU de Insight Server que ejecuten el servicio de replicación de Insight Server.

Consulte [Servicio de replicación de Insight Server](../../../../home/c-inst-svr/c-ins-svr-rep-svc/c-ins-svr-rep-svc.md#concept-926e654e80d943a0b6ac44a82a510d92). Esta función permite la replicación de datos en instalaciones redundantes con fines de recuperación ante desastres. Los servidores de destino actúan como clientes de red, conectándose a la FSU de origen para solicitar copias de los datos de evento para incluirlos en varios conjuntos de datos.

Puede utilizar la funcionalidad del repetidor en infraestructuras de red con varias capas de cortafuegos para lograr comunicaciones de un solo puerto a un solo puerto entre componentes separados por cortafuegos.

Para obtener información sobre los requisitos del sistema para instalar, configurar y operar [!DNL Repeater], consulte el documento *Minimum System Requirements*.

Para instalar [!DNL Repeater], debe realizar los pasos que se indican para los dos procedimientos siguientes:

* [Configuración de una FSU de Insight Server para el repetidor](../../../../home/c-inst-svr/c-rptr-fntly/c-cnfg-rptr-fntly/t-cfg-fsu-rptr.md#task-1ad7fa5777b845f4bd398f97226e56b2)
* [Configuración del control de acceso para equipos de destino](../../../../home/c-inst-svr/c-rptr-fntly/c-cnfg-rptr-fntly/t-cfg-acc-ctrll-tgt-mach.md#task-0e49953728444839bc0a26234501a4c5)

Si los cortafuegos de red permiten el acceso a su [!DNL Repeater] desde [!DNL Insight], puede crear una conexión tal como se describe en [Creación de una conexión entre Insight y el repetidor](../../../../home/c-inst-svr/c-rptr-fntly/c-cnfg-rptr-fntly/t-crt-conn-ins-rptr.md#task-785bfe5f0e31484683e4345038add118).
