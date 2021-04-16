---
description: A continuación se enumeran las métricas incluidas en el perfil de monitorización histórica de Data Workbench y cómo se derivan.
title: Métricas en el perfil de monitorización histórica de Data Workbench
uuid: 47b874f7-8acb-4593-9ac9-5997d5279e52
exl-id: 65f0f605-f128-45bb-8f6c-95284b2da740
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '718'
ht-degree: 2%

---

# Métricas en el perfil de monitorización histórica de Data Workbench{#metrics-in-the-data-workbench-historical-monitoring-profile}

A continuación se enumeran las métricas incluidas en el perfil de monitorización histórica de Data Workbench y cómo se derivan.

| **Críticos de alertas** | La suma de la dimensión Alerta crítica para cada ping. |
|---|---|
| **Desventajas de alertas** | La suma de la dimensión Alerta abajo para cada ping. |
| **Advertencias de alerta** | La suma de la dimensión Advertencia de alerta para cada ping. |
| **Todos los componentes** | Recuento de pings en los que el éxito de la comprobación de componentes es igual a &quot;1&quot; dividido por la métrica Anclajes multiplicada por 100. |
| **Con retraso en minutos** | Esta métrica es la suma de los minutos con fecha de retraso para cada ping y, a continuación, se divide por la métrica Anuncios. |
| **Bloques** | La suma de uno para cada bloque. |
| **Bloquear todo** | Todos los bloques. |
| **Capacidad general** | La métrica Tamaño de capacidad es de dos veces más la métrica Fila de capacidad, dividida por 3. |
| **Fila de capacidad** | La suma de la dimensión Porcentaje de fila de capacidad para cada ping dividida por la métrica Anclajes. |
| **Tamaño de la capacidad** | La suma de la dimensión Porcentaje de tamaño de capacidad para cada ping, dividida por la métrica Anclajes. |
| **Comunicaciones** | El número de pings en los que el éxito de la comprobación rápida coincide con &quot;1&quot;, dividido por la métrica Anuncios. |
| **Segundos de comprobación detallados** | La suma de la dimensión Segundos de comprobación detallados para cada ping donde el tipo de ping es &quot;servidor&quot;, dividida por la métrica Anuncios. |
| **Dimension GigaBytes** | La suma de Gigabytes Dimension para cada Ping, dividida por la métrica Pings. |
| **Disco &quot;x&quot;** | Las métricas de disco se calculan tomando la suma de su Porcentaje de disco usado para cada ping, dividido por la métrica Anclajes. |
| **Minutos de barrido estimados** | Esta es la suma de los segundos del Dekasds de barrido estimados para cada ping, dividido por la métrica Anillos donde los segundos de barrido estimados son buenos a cero, todos divididos por 6. |
| **Entrada rápida MB por minuto** | La suma de MegaBytes de Entrada Rápida por Minuto para cada Ping dividido por el número de Pings cuando MegaBytes de Entrada Rápida por Minuto es buena a cero. |
| **Modo de entrada rápida** | Anclajes en los que la dimensión Modo de procesamiento es igual a &quot;Entrada rápida&quot; dividido por Anillos. |
| **MegaBytes de fusión rápida por minuto** | La suma de Megabytes de Fusión Rápida por Minuto para cada Ping, dividido por la métrica Anclajes. |
| **Modo de combinación rápida** | Anclajes en los que el modo de procesamiento es igual a &quot;combinación rápida&quot; dividido por la métrica Anclajes. |
| **Field GigaBytes** | La suma de la dimensión Gigabytes de campo para cada ping dividido por la métrica Anclajes. |
| **Carga** | La suma de la dimensión Media de carga para cada ping, dividida por la métrica Anclajes. |
| **Lectura de registros** | La suma de la dimensión Procesamiento de lectura de registros para cada ping, dividida por la métrica Anclajes, todas divididas por 10. |
| **Página Memoria** | La suma de Porcentaje de archivos de página de memoria para cada ping, dividida por la métrica Anclajes. |
| **Memoria física** | La suma de la dimensión Porcentaje físico de memoria para cada ping, dividida por la métrica Anclajes. |
| **Consulta de memoria** | La suma del porcentaje de consulta de memoria para cada ping, dividido por la métrica Anclajes. |
| **Memoria total GB** | La suma de la dimensión MegaBytes totales físicos de memoria para cada ping, dividida por la métrica Anclajes. |
| **Conexiones de red** | Esta es la suma de las conexiones de red para cada ping dividido por la métrica Anclajes. |
| **Pings x Capacidad General** | La métrica Anclajes multiplicada por la métrica Capacidad general . |
| **Milisegundos de latencia de encuesta** | La suma de la dimensión de los centísegundos de latencia de encuesta para cada ping, dividida por la métrica Anillos, todos multiplicados por 10. |
| **Consulta en ejecución** | La suma de uno para cada ping donde el Dekassegundo de barrido estimado es bueno que &quot;0&quot;, dividido por la métrica Anclajes donde el Tipo de ping es igual a &quot;servidor&quot;. |
| **Comprobación rápida en segundos** | La suma de segundos de comprobación rápida para cada ping donde el tipo de ping es igual a &quot;servidor&quot;, dividido por la métrica Anuncios. |
| **Filas de salida** | La suma de la dimensión Filas de salida para cada ping dividido por la métrica Anuncios, multiplicada por 100000. |
| **Modo en tiempo real** | El número de pings en los que la dimensión Modo de procesamiento es igual a &quot;tiempo real&quot;, dividido por la métrica Anuncios, todos multiplicados por 100. |
| **Modo de reprocesamiento** | 100 menos el número de pings donde el Modo de procesamiento es igual a &quot;tiempo real&quot; dividido por la métrica Anuncios, multiplicado por 100. |
| **Atascado** | La suma de la dimensión Procesamiento demorado en el perfil Insight [Estado del perfil](../../../home/monitoring-installation/monitoring-appendix/monitoring-profile-status.md#concept-d4cd7da41c8a42bab4aea25418264e64). |
| **Base de datos temporal** | La suma del porcentaje de espacio de base de datos temporal para cada ping, dividido por la métrica Anclajes. |
| **Transformación** | La suma de porcentaje de transformación para cada ping dividida por la métrica Anclajes, todos divididos por 10. |
