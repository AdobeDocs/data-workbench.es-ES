---
description: El propósito de la función de filtrado de tipo de contenido de Sensor es eliminar la necesidad de almacenar y procesar información que no es útil para fines de análisis.
solution: Analytics
title: Filtrado por tipo de contenido
topic: Data workbench
uuid: 8a3b567b-8c7b-4ca2-bfcb-74a1addda2bd
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Filtrado por tipo de contenido{#filtering-by-content-type}

El propósito de la función de filtrado de tipo de contenido de Sensor es eliminar la necesidad de almacenar y procesar información que no es útil para fines de análisis.

Gran parte de los datos de solicitud que están disponibles a través de la API de un servidor web no son útiles en el análisis comercial. El almacenamiento y el procesamiento son costosos y el filtrado de tipo de contenido le permite evitar el almacenamiento y el procesamiento innecesarios. [!DNL Sensor’s]

Para maximizar el rendimiento de procesamiento de datos del registro Web y reducir la cantidad de datos de medición que deben almacenarse, [!DNL Site] adquiere datos de medición (datos de solicitud, entradas de registro, datos de registro, etc.) para todas las solicitudes de tipo de contenido Web, excepto para los tipos de contenido enumerados específicamente (como hojas de estilo en cascada, solicitudes de imagen, etc.), que se filtran antes de que se transmitan al servidor del área de trabajo de datos por [!DNL Sensor]. Este filtro se puede desactivar para un servidor web completo y también se puede anular para un objeto de contenido determinado agregando el par nombre-valor &quot;Log=1&quot; a la cadena de consulta de un objeto incrustado determinado (por ejemplo, [!DNL http://www.mysite.com/advertisement.gif?Log=1]).
