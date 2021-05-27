---
description: Para utilizar un clúster, debe designar un servidor de Insight en el clúster para que actúe como servidor maestro de Insight Server.
title: Instalación de Master Insight Server
uuid: a73214f3-b175-4e9e-8802-7a8451d86d3a
exl-id: 710f1ffe-f620-4920-b4f9-a644cc68d4cc
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '197'
ht-degree: 5%

---

# Instalación de Master Insight Server{#installing-the-master-insight-server}

Para utilizar un clúster, debe designar un servidor de Insight en el clúster para que actúe como servidor maestro de Insight Server.

Un componente cliente como [!DNL Insight] o [!DNL Report] se conecta al [!DNL Insight Server] maestro al principio de una sesión. En los puntos siguientes durante la sesión, el cliente puede conectarse a otros [!DNL Insight Servers] del clúster para realizar una consulta. Estas conexiones subsiguientes entre el cliente y el otro [!DNL Insight Servers] del clúster son intermediadas por el maestro [!DNL Insight Server] y son transparentes para el cliente.

Además de corretear las conexiones entre un cliente y otros [!DNL Insight Servers] del clúster, el [!DNL Insight Server] maestro actúa como punto administrativo central para todo el clúster. Cuando administra un clúster, actualiza el [!DNL Insight Server] maestro. Los cambios administrativos que realice en el [!DNL Insight Server] maestro los recupera el otro [!DNL Insight Servers] del clúster.

**Para instalar el maestro[!DNL Insight Server]**

1. Determine qué máquina actuará como la maestra [!DNL Insight Server].
1. Instale y configure [!DNL Insight Server] (normalmente, una [!DNL Insight Server] FSU) en este equipo como se describe en [Insight Server](../../../../../../home/c-inst-svr/c-msr-server/c-msr-server.md).
1. Instale [!DNL Insight] y configure una conexión con el [!DNL Insight Server] maestro tal como se describe en la *[!DNL Insight]Guía del usuario*.
