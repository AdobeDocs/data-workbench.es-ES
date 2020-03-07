---
description: Para utilizar un clúster, debe designar un servidor de Insight en el clúster para que actúe como servidor maestro de Insight Server.
solution: Insight
title: Instalación de Master Insight Server
uuid: a73214f3-b175-4e9e-8802-7a8451d86d3a
translation-type: tm+mt
source-git-commit: 27600561841db3705f4eee6ff0aeb8890444bbc9

---


# Instalación de Master Insight Server{#installing-the-master-insight-server}

Para utilizar un clúster, debe designar un servidor de Insight en el clúster para que actúe como servidor maestro de Insight Server.

Un componente cliente como [!DNL Insight] o se conecta [!DNL Report] al maestro [!DNL Insight Server] al principio de una sesión. En los puntos posteriores de la sesión, el cliente podría conectarse a otros [!DNL Insight Servers] del clúster para realizar una consulta. Estas conexiones subsiguientes entre el cliente y el otro [!DNL Insight Servers] del clúster son negociadas por el maestro [!DNL Insight Server] y son transparentes para el cliente.

Además de las conexiones de intermediación entre un cliente y otro [!DNL Insight Servers] del clúster, el maestro [!DNL Insight Server] actúa como punto administrativo central para todo el clúster. Al administrar un clúster, se actualiza el maestro [!DNL Insight Server]. Los cambios administrativos que realiza en el patrón [!DNL Insight Server] los recupera el otro [!DNL Insight Servers] del clúster.

**Para instalar el maestro[!DNL Insight Server]**

1. Determinar qué máquina actuará como maestra [!DNL Insight Server].
1. Instale y configure [!DNL Insight Server] (normalmente, una [!DNL Insight Server] FSU) en este equipo como se describe en [Insight Server](../../../../../../home/c-inst-svr/c-msr-server/c-msr-server.md).
1. Instale [!DNL Insight] y configure una conexión con el maestro [!DNL Insight Server] como se describe en la *[!DNL Insight]Guía *del usuario.
