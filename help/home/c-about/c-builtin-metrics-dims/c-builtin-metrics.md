---
description: Área de trabajo de datos incluye métricas integradas.
solution: Analytics
title: Métricas integradas
topic: Data workbench
uuid: 1e4d91dc-0130-4296-8395-fd2ddb03f6ef
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Métricas integradas{#built-in-metrics}

Área de trabajo de datos incluye métricas integradas.

En la tabla siguiente se muestran las métricas integradas disponibles para el área de trabajo de datos:

| Métrica integrada | Descripción |
|---|---|
| A partir de | El valor Con respecto al tiempo del conjunto de datos en intervalos de 100 nanosegundos desde el 1 de enero de 1600 00:00 UTC. La marca de tiempo Con fecha es la última vez en el conjunto de datos para la que se han procesado definitivamente todos los datos. |
| Bytes de registro leídos | Cantidad total de datos comprimidos (en bytes) que hasta ahora se han procesado durante la fase de procesamiento del registro. |
| Total de bytes de registro | Cantidad total de datos comprimidos (en bytes) en archivos de registro que coinciden con los criterios de fuentes de registro configurados y el intervalo de fechas de inicio y finalización del conjunto de datos. Si el procesamiento del registro se pone en pausa en el archivo de configuración del modo de procesamiento del registro, el total de bytes de registro será el mismo que el de bytes de registro leídos. |
| Progreso del procesamiento de registros | Porcentaje de finalización de la fase de procesamiento de registros del procesamiento de datos de Insight Server. |
| Total de entradas de registro descodificadas | Número de entradas de los archivos de registro que se descodificaron correctamente como parte de la fase de procesamiento de registros del procesamiento de datos de Insight Server. |
| Total de entradas de registro filtradas | Número de entradas en los archivos de registro que después de ser descodificadas fueron aceptadas por el filtro de robot y las condiciones de entrada de registro y otros filtros que se aplican como parte de la fase de procesamiento de registros del procesamiento de datos de Insight Server. |
| Entradas de registro totales | Número de entradas en los archivos de registro que hasta ahora han sido procesadas por la fase de procesamiento de registros del procesamiento de datos de Insight Server. |
| Total de entradas de registro procesadas | El número de entradas de registro filtradas que se han incorporado al conjunto de datos de Adobe. |
| Progreso de la transformación | Porcentaje de finalización de la fase de transformación del procesamiento de datos de Insight Server. |
| Bytes de registro sin comprimir leídos | Cantidad total de datos sin comprimir (en bytes) que hasta ahora se han procesado durante la fase de procesamiento del registro. |

