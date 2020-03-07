---
description: A continuación se enumeran las métricas incluidas en el perfil de supervisión histórica del área de trabajo de datos y cómo se obtienen.
solution: Analytics
title: Métricas en el perfil de supervisión histórica del área de trabajo de datos
topic: Data workbench
uuid: 47b874f7-8acb-4593-9ac9-5997d5279e52
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Métricas en el perfil de supervisión histórica del área de trabajo de datos{#metrics-in-the-data-workbench-historical-monitoring-profile}

A continuación se enumeran las métricas incluidas en el perfil de supervisión histórica del área de trabajo de datos y cómo se obtienen.

| **Críticos de alerta** | La suma de la dimensión Alerta crítica para cada ping. |
|---|---|
| **Alertas de alertas** | La suma de la dimensión Alerta hacia abajo para cada ping. |
| **Advertencias de alerta** | La suma de la dimensión Advertencia de alerta para cada ping. |
| **Todos los componentes** | Recuento de ping donde el éxito de la comprobación de componentes es igual a &quot;1&quot; dividido por la métrica Anuncios multiplicada por 100. |
| **A Los Minutos De Demora** | Esta métrica es la suma de los Minutos con retraso de cada ping y, a continuación, se divide por la métrica Anuncios. |
| **Bloques** | La suma de uno para cada bloque. |
| **Bloquear todo** | Todos los bloques. |
| **Capacidad general** | La métrica Tamaño de capacidad es dos veces más la métrica Fila de capacidad, dividida por 3. |
| **Fila de capacidad** | La suma de la dimensión Porcentaje de fila de capacidad para cada ping dividida por la métrica Anclajes. |
| **Tamaño de capacidad** | La suma de la dimensión Porcentaje de tamaño de capacidad para cada ping, dividida por la métrica Anclajes. |
| **Comunicaciones** | El número de ping en los que el éxito de la comprobación rápida coincide con &quot;1&quot;, dividido por la métrica Anuncios. |
| **Segundos de comprobación detallados** | La suma de la dimensión Comprobar segundos detallados para cada ping donde el tipo de ping es &quot;server&quot;, dividida por la métrica Anuncios. |
| **Bytes GigaBytes de dimensión** | La suma de gigabytes de dimensión para cada ping, dividida por la métrica Anclajes. |
| **Disco &quot;x&quot;** | Las métricas de disco se calculan tomando la suma del porcentaje de disco usado para cada ping, dividido por la métrica Anuncios. |
| **Minutos de barrido estimados** | Esta es la suma de los segundos de barrido estimados para cada ping, dividida por la métrica Pings, donde los segundos de barrido estimados son buenos a cero, todos divididos por 6. |
| **Entrada rápida MB por minuto** | La suma de MegaBytes de entrada rápida por minuto para cada ping dividida por el número de ping cuando MegaBytes de entrada rápida por minuto es buena a cero. |
| **Modo de entrada rápido** | Pings donde la dimensión Modo de procesamiento es igual a &quot;Entrada rápida&quot; dividido por Pings. |
| **MegaBytes de combinación rápida por minuto** | La suma de Megabytes de combinación rápida por minuto para cada ping, dividida por la métrica Anclajes. |
| **Modo de combinación rápida** | Anuncios en los que el modo de procesamiento es igual a &quot;combinación rápida&quot; dividido por la métrica Anclajes. |
| **GigaBytes de campo** | La suma de la dimensión Gigabytes de campo para cada ping dividido por la métrica Anclajes. |
| **Carga** | La suma de la dimensión Cargar promedio para cada ping, dividida por la métrica Anclajes. |
| **Lectura de registro** | La suma de la dimensión Procesamiento de lectura de registros para cada ping, dividida por la métrica Anclajes, todas divididas por 10. |
| **Página Memoria** | Suma del porcentaje de archivo de página de memoria para cada ping, dividido por la métrica Anuncios. |
| **Memoria física** | La suma de la dimensión Porcentaje físico de memoria para cada ping, dividida por la métrica Anuncios. |
| **Consulta de memoria** | La suma del porcentaje de consulta de memoria para cada ping, dividido por la métrica Anuncios. |
| **GB total de memoria** | La suma de la dimensión MegaBytes totales físicos de memoria para cada ping, dividida por la métrica Anclajes. |
| **Conexiones de red** | Es la suma de las conexiones de red para cada ping dividido por la métrica Anclajes. |
| **Pings x Capacidad general** | La métrica Anuncios multiplicada por la métrica Capacidad total. |
| **Milisegundos de latencia de la encuesta** | La suma de la dimensión Centisegundos de latencia de encuesta para cada ping, dividida por la métrica Anuncios, todas multiplicadas por 10. |
| **Consulta en ejecución** | La suma de uno para cada ping donde Dekaseconds de barrido estimados es buena a &quot;0&quot;, dividida por la métrica Anclajes donde Tipo de ping es igual a &quot;servidor&quot;. |
| **Segundos de comprobación rápida** | Suma de segundos de comprobación rápida para cada ping donde el tipo de ping es igual a &quot;servidor&quot;, dividido por la métrica Anuncios. |
| **Filas de salida** | La suma de la dimensión Filas de salida para cada ping dividido por la métrica Anuncios, multiplicada por 100000. |
| **Modo en tiempo real** | El número de ping donde la dimensión Modo de procesamiento es igual a &quot;tiempo real&quot;, dividido por la métrica Anuncios, todos multiplicados por 100. |
| **Modo de reprocesamiento** | 100 menos el número de Anuncios en los que el modo de procesamiento es igual a &quot;tiempo real&quot; dividido por la métrica Anuncios, multiplicado por 100. |
| **Atascado** | La suma de la dimensión Procesamiento detenido en el perfil Estado [del](../../../home/monitoring-installation/monitoring-appendix/monitoring-profile-status.md#concept-d4cd7da41c8a42bab4aea25418264e64) perfil de perspectiva. |
| **Base de datos temporal** | La suma del porcentaje de espacio de base de datos temporal para cada ping, dividido por la métrica Anuncios. |
| **Transformación** | La suma del porcentaje de transformación para cada ping dividido por la métrica Anclajes, todo dividido por 10. |

