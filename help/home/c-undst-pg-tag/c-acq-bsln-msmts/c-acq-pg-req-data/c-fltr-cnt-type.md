---
description: El propósito de la capacidad de filtrado de tipo contenido del sensor es eliminar la necesidad de almacenar y procesar información que no es útil para fines de análisis.
title: Filtrado por tipo de contenido
uuid: 8a3b567b-8c7b-4ca2-bfcb-74a1addda2bd
exl-id: 0ed93a18-ef47-462b-8609-3ec98b037e6b
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '195'
ht-degree: 4%

---

# Filtrado por tipo de contenido{#filtering-by-content-type}

El propósito de la capacidad de filtrado de tipo contenido del sensor es eliminar la necesidad de almacenar y procesar información que no es útil para fines de análisis.

Gran parte de los datos de solicitud disponibles a través de la API de un servidor web no son útiles en el análisis empresarial. El almacenamiento y el procesamiento son costosos y el filtrado de tipo de contenido [!DNL Sensor’s] permite evitar el almacenamiento y el procesamiento innecesarios.

Para maximizar el rendimiento del procesamiento de datos del registro web y reducir la cantidad de datos de medición que se deben almacenar, [!DNL Site] adquiere datos de medición (datos de solicitud, entradas de registro, datos de registro, etc.) para todas las solicitudes de tipo de contenido web, excepto para los tipos de contenido enumerados específicamente (como hojas de estilo en cascada, solicitudes de imagen, etc.), que se filtran antes de transmitirse al servidor de Data Workbench mediante [!DNL Sensor]. Este filtro se puede desactivar para un servidor web completo y también se puede anular para un objeto de contenido determinado añadiendo el par nombre-valor &quot;Log=1&quot; a la cadena de consulta de un objeto incrustado determinado (por ejemplo, [!DNL http://www.mysite.com/advertisement.gif?Log=1]).
