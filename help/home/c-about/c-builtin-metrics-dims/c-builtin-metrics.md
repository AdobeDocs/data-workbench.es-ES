---
description: Data Workbench incluye métricas integradas.
title: Métricas integradas
uuid: 1e4d91dc-0130-4296-8395-fd2ddb03f6ef
exl-id: a8a2a8dd-dc13-4eb3-92ce-09f02252ecf0
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '310'
ht-degree: 1%

---

# Métricas integradas{#built-in-metrics}

Data Workbench incluye métricas integradas.

La tabla siguiente muestra las métricas integradas disponibles para Data Workbench:

| Métrica integrada | Descripción |
|---|---|
| Con | El valor A partir del tiempo del conjunto de datos en intervalos de 100 nanosegundos desde el 1 de enero de 1600 a las 00:00 UTC. La marca de fecha y hora es la última vez en el conjunto de datos para la que definitivamente se han procesado todos los datos. |
| Bytes de registro leídos | Cantidad total de datos comprimidos (en bytes) que hasta ahora se han procesado durante la fase de procesamiento del registro. |
| Total de bytes de registro | Cantidad total de datos comprimidos (en bytes) en archivos de registro que coinciden con los criterios de las fuentes de registro configuradas y el intervalo de fechas de inicio y finalización del conjunto de datos. Si el procesamiento de registros está en pausa en el archivo de configuración del modo de procesamiento de registros, el total de bytes de registro será el mismo que el de bytes de registro leídos. |
| Progreso del procesamiento de registros | Porcentaje de finalización de la fase de procesamiento de registros del procesamiento de datos de Insight Server. |
| Total de entradas de registro descodificadas | Número de entradas de los archivos de registro que se descodificaron correctamente como parte de la fase de procesamiento de registros del procesamiento de datos de Insight Server. |
| Total de entradas de registro filtradas | El número de entradas en los archivos de registro que después de ser descodificadas fueron aceptadas por el filtro de robot y las condiciones de entrada de registro y otros filtros que se aplican como parte de la fase de procesamiento de registros del procesamiento de datos de Insight Server. |
| Entradas de registro totales | Número de entradas de los archivos de registro que se han procesado hasta ahora mediante la fase de procesamiento de registros del procesamiento de datos de Insight Server. |
| Total de entradas de registro procesadas | Número de entradas de registro filtradas que se han incorporado al conjunto de datos de Adobe. |
| Progreso de la transformación | Porcentaje de finalización de la fase de transformación del procesamiento de datos de Insight Server. |
| Lectura de bytes de registro sin comprimir | Cantidad total de datos sin comprimir (en bytes) que hasta ahora se han procesado durante la fase de procesamiento del registro. |
