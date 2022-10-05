---
description: Para utilizar un clúster, debe designar un servidor de Insight en el clúster para que actúe como servidor maestro de Insight Server.
title: Instalación de Master Insight Server
uuid: a73214f3-b175-4e9e-8802-7a8451d86d3a
exl-id: 710f1ffe-f620-4920-b4f9-a644cc68d4cc
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '197'
ht-degree: 5%

---

# Instalación de Master Insight Server{#installing-the-master-insight-server}

{{eol}}

Para utilizar un clúster, debe designar un servidor de Insight en el clúster para que actúe como servidor maestro de Insight Server.

Un componente cliente como [!DNL Insight] o [!DNL Report] se conecta al maestro [!DNL Insight Server] al principio de una sesión. En los puntos siguientes durante la sesión, el cliente puede conectarse a otros [!DNL Insight Servers] en el clúster para realizar una consulta. Estas conexiones subsiguientes entre el cliente y el otro [!DNL Insight Servers] en el clúster están negociados por el maestro [!DNL Insight Server] y son transparentes para el cliente.

Además de las conexiones de intermediación entre un cliente y otro [!DNL Insight Servers] en el clúster, el maestro [!DNL Insight Server] actúa como punto administrativo central para todo el clúster. Cuando administra un clúster, actualiza el maestro [!DNL Insight Server]. Los cambios administrativos que realice en el maestro [!DNL Insight Server] son recuperadas por el otro [!DNL Insight Servers] en el clúster.

**Para instalar el maestro[!DNL Insight Server]**

1. Determinar qué máquina actuará como maestra [!DNL Insight Server].
1. Instalación y configuración [!DNL Insight Server] (normalmente, un [!DNL Insight Server] FSU) en este equipo tal como se describe en [Insight Server](../../../../../../home/c-inst-svr/c-msr-server/c-msr-server.md).
1. Instalar [!DNL Insight] y configurar una conexión con el maestro [!DNL Insight Server] tal como se describe en la sección *[!DNL Insight]Guía del usuario*.
