---
description: La funcionalidad Repetidor permite que una FSU de Insight Server reciba datos de eventos adquiridos por el sensor de una o más fuentes y replique los datos a una o más FSU de Insight Server que ejecutan el servicio Insight ServerReplication.
solution: Insight
title: Configuración de la funcionalidad del repetidor
uuid: 45dca069-a91f-4fd4-bd47-c8c2e6aab834
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Configuración de la funcionalidad del repetidor{#configuring-repeater-functionality}

La funcionalidad Repetidor permite que una FSU de Insight Server reciba datos de eventos adquiridos por el sensor de una o más fuentes y replique los datos a una o más FSU de Insight Server que ejecutan el servicio Insight ServerReplication.

Consulte [Servicio](../../../../home/c-inst-svr/c-ins-svr-rep-svc/c-ins-svr-rep-svc.md#concept-926e654e80d943a0b6ac44a82a510d92)de replicación de Insight Server. Esta función permite la replicación de datos en instalaciones redundantes para fines de recuperación ante desastres. Los servidores de destino actúan como clientes de red, conectándose a la FSU de origen para solicitar copias de los datos del evento para incluirlas en varios conjuntos de datos.

Puede utilizar la funcionalidad repetidor en infraestructuras de red con varias capas de cortafuegos para lograr comunicaciones de un solo puerto a un solo puerto entre componentes separados por firewalls.

Para obtener información sobre los requisitos del sistema para la instalación, configuración y funcionamiento [!DNL Repeater], consulte el documento Requisitos ** mínimos del sistema.

Para realizar la instalación [!DNL Repeater], debe realizar los pasos que se indican para los dos procedimientos siguientes:

* [Configuración de una FSU de Insight Server para Repetidor](../../../../home/c-inst-svr/c-rptr-fntly/c-cnfg-rptr-fntly/t-cfg-fsu-rptr.md#task-1ad7fa5777b845f4bd398f97226e56b2)
* [Configuración del control de acceso para equipos de destino](../../../../home/c-inst-svr/c-rptr-fntly/c-cnfg-rptr-fntly/t-cfg-acc-ctrll-tgt-mach.md#task-0e49953728444839bc0a26234501a4c5)

Si los servidores de seguridad de red permiten el acceso a su [!DNL Repeater] desde [!DNL Insight], puede crear una conexión como se describe en [Creación de una conexión entre Insight y Repetidor](../../../../home/c-inst-svr/c-rptr-fntly/c-cnfg-rptr-fntly/t-crt-conn-ins-rptr.md#task-785bfe5f0e31484683e4345038add118).