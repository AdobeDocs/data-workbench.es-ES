---
description: El servicio de replicación de Insight Server permite transmitir los datos de evento recopilados y almacenados en un equipo de Insight Server a otro equipo de Insight Server.
solution: Analytics
title: Instalación del servicio de replicación
uuid: a6467d5f-ca1c-4368-ba83-0b6bcabbe511
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '184'
ht-degree: 4%

---


# Instalación del servicio de replicación{#installing-the-replication-service}

El servicio de replicación de Insight Server permite transmitir los datos de evento recopilados y almacenados en un equipo de Insight Server a otro equipo de Insight Server.

Normalmente, la máquina en la que se recopilan y almacenan los datos está configurada para ejecutarse como [!DNL Repeater] equipo. Consulte Funcionalidad [de repetición](../../../home/c-inst-svr/c-rptr-fntly/c-rptr-fntly.md). El [!DNL Replication Service], configurado por el [!DNL Replicate.cfg] archivo, permite a un [!DNL Insight Server] equipo recuperar datos del [!DNL Repeater] equipo y almacenarlos localmente. La [!DNL Insight Server] máquina se denomina máquina de destinatario. Varios DPU [!DNL Insight Server] se pueden conectar a un único [!DNL Repeater] para solicitar copias de los datos de evento para incluirlas en varios conjuntos de datos.

Puede utilizar el [!DNL Replication Service] en infraestructuras de red con varias capas de cortafuegos para lograr comunicaciones de un solo puerto a un solo puerto entre componentes separados por firewalls.

**Para instalar el[!DNL Replication Service]**

El [!DNL Replicate.cfg] archivo debe instalarse como parte de la [!DNL Insight Server] instalación. Puede encontrar el archivo dentro de la [!DNL Components] carpeta del directorio [!DNL Insight Server] de instalación. Si no tiene este archivo, póngase en contacto con Adobe.
