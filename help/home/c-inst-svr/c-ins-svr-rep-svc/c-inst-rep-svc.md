---
description: El servicio de replicación de Insight Server permite transmitir los datos de evento recopilados y almacenados en un equipo de Insight Server a otro equipo de Insight Server.
title: Instalación del servicio de replicación
uuid: a6467d5f-ca1c-4368-ba83-0b6bcabbe511
exl-id: a235fe75-a6d0-4c20-8ea2-8b1cbad12da7
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '184'
ht-degree: 4%

---

# Instalación del servicio de replicación{#installing-the-replication-service}

{{eol}}

El servicio de replicación de Insight Server permite transmitir los datos de evento recopilados y almacenados en un equipo de Insight Server a otro equipo de Insight Server.

Normalmente, el equipo en el que se recopilan y almacenan los datos está configurado para ejecutarse como un [!DNL Repeater] máquina. Consulte [Funcionalidad del repetidor](../../../home/c-inst-svr/c-rptr-fntly/c-rptr-fntly.md). La variable [!DNL Replication Service], que el [!DNL Replicate.cfg] activa un [!DNL Insight Server] máquina para recuperar datos de [!DNL Repeater] manipularlo y almacenarlo localmente. La variable [!DNL Insight Server] máquina se denomina máquina de destino. Múltiple [!DNL Insight Server] Las DPU pueden conectarse a una sola [!DNL Repeater] para solicitar copias de los datos de evento para incluirlos en varios conjuntos de datos.

Puede usar la variable [!DNL Replication Service] en infraestructuras de red con múltiples capas de cortafuegos para lograr comunicaciones de un solo puerto a un solo puerto entre componentes separados por cortafuegos.

**Para instalar el[!DNL Replication Service]**

La variable [!DNL Replicate.cfg] debe instalarse como parte de su [!DNL Insight Server] instalación. Puede encontrar el archivo dentro de la variable [!DNL Components] carpeta de [!DNL Insight Server] directorio de instalación. Si no tiene este archivo, póngase en contacto con el Adobe.
