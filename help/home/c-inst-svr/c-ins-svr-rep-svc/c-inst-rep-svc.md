---
description: El servicio de replicación de Insight Server permite transmitir los datos de evento recopilados y almacenados en un equipo de Insight Server a otro equipo de Insight Server.
title: Instalación del servicio de replicación
uuid: a6467d5f-ca1c-4368-ba83-0b6bcabbe511
exl-id: a235fe75-a6d0-4c20-8ea2-8b1cbad12da7
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '184'
ht-degree: 4%

---

# Instalación del servicio de replicación{#installing-the-replication-service}

El servicio de replicación de Insight Server permite transmitir los datos de evento recopilados y almacenados en un equipo de Insight Server a otro equipo de Insight Server.

Normalmente, el equipo en el que se recopilan y almacenan los datos está configurado para ejecutarse como un equipo [!DNL Repeater]. Consulte [Funcionalidad del repetidor](../../../home/c-inst-svr/c-rptr-fntly/c-rptr-fntly.md). El [!DNL Replication Service], que está configurado por el archivo [!DNL Replicate.cfg], permite que un equipo [!DNL Insight Server] recupere datos del equipo [!DNL Repeater] y los almacene localmente. El equipo [!DNL Insight Server] se denomina equipo de destino. Varias [!DNL Insight Server] DPUs pueden conectarse a una sola [!DNL Repeater] para solicitar copias de los datos de evento para incluirlos en varios conjuntos de datos.

Puede utilizar [!DNL Replication Service] en infraestructuras de red con varias capas de cortafuegos para lograr comunicaciones de un solo puerto a un solo puerto entre componentes separados por cortafuegos.

**Para instalar el[!DNL Replication Service]**

El archivo [!DNL Replicate.cfg] debe instalarse como parte de la instalación de [!DNL Insight Server]. Puede encontrar el archivo dentro de la carpeta [!DNL Components] del directorio de instalación [!DNL Insight Server]. Si no tiene este archivo, póngase en contacto con el Adobe.
