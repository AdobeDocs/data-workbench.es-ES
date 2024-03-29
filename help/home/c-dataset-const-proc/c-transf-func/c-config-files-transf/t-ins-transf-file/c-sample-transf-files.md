---
description: Información sobre cómo especificar parámetros en el archivo Transform.cfg en función de los distintos escenarios.
title: Archivos Transform.cfg de Data Workbench de muestra
uuid: cb473a5a-54e2-4bf7-84fb-c9c27910ef64
exl-id: f7aadde4-6d89-4bd4-b34b-192a81a71dc3
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '409'
ht-degree: 2%

---

# Archivos Transform.cfg de Data Workbench de muestra{#sample-data-workbench-transform-cfg-files}

{{eol}}

Información sobre cómo especificar parámetros en el archivo Transform.cfg en función de los distintos escenarios.

* [Un archivo Transform.cfg de Insight simple](../../../../../home/c-dataset-const-proc/c-transf-func/c-config-files-transf/t-ins-transf-file/c-sample-transf-files.md#section-b7e83cafa3a947c597bd09d316930190)
* [Salida con valores separados por comas](../../../../../home/c-dataset-const-proc/c-transf-func/c-config-files-transf/t-ins-transf-file/c-sample-transf-files.md#section-03916934ad574efc8695abbae54a1816)
* [Archivos de registro de muestra](../../../../../home/c-dataset-const-proc/c-transf-func/c-config-files-transf/t-ins-transf-file/c-sample-transf-files.md#section-113b3b0c0c7547ea9536bb2f465c0875)
* [División de archivos de registro por sección de sitio web](../../../../../home/c-dataset-const-proc/c-transf-func/c-config-files-transf/t-ins-transf-file/c-sample-transf-files.md#section-2cac205cd3934d31abb6c6ed8780196d)

En cada ejemplo, el archivo se muestra como un [!DNL Transform.cfg] en data workbench.

## Un archivo Transform.cfg de Data Workbench simple {#section-b7e83cafa3a947c597bd09d316930190}

Lo siguiente [!DNL Transform.cfg] window proporciona instrucciones para leer [!DNL .vsl] los archivos de [!DNL Logs] y exporte los campos x-timestring y x-trackingid a un archivo de texto almacenado en el directorio Logs\VT. Dado que no se especifica ningún período de rotación de archivos ni el formato del nombre del archivo de salida, cada archivo contiene datos de un día del calendario y tiene un nombre en el formato predeterminado [!DNL %yyyy%%mm%%dd%-%x-mask%.txt].

![](assets/cfg_VisualTransform_SimpleExample.png)

## Salida con valores separados por comas {#section-03916934ad574efc8695abbae54a1816}

Lo siguiente [!DNL Transform.cfg] window proporciona instrucciones para leer [!DNL .vsl] archivos del directorio Registros y exportar campos 0 a 13 delimitados por comas ( [!DNL .csv]) almacenado en el directorio Logs\VT\CSV. Dado que no se especifica ningún período de rotación de archivos, cada archivo contiene datos de un día del calendario. Los archivos de salida son [!DNL .csv] archivos con el formato [!DNL %yyyy%%mm%%dd%-%x-mask%.csv].

![](assets/cfg_VisualTransform_CSVExample.png)

## Archivos de registro de muestra {#section-113b3b0c0c7547ea9536bb2f465c0875}

Puede configurar la funcionalidad de transformación para crear y mantener una versión compacta y actualizada de sus archivos de registro completos. Al hacerlo, puede probar rápidamente las configuraciones del conjunto de datos, con tiempos de reprocesamiento de segundos o minutos en lugar de horas necesarias para reprocesar todo el conjunto de datos. El siguiente ejemplo proporciona un ejemplo de cómo configurar la funcionalidad de transformación para hacerlo.

Lo siguiente [!DNL Transform.cfg] window proporciona instrucciones para leer [!DNL .vsl] archivos del directorio Logs y exporte los campos x-timestring y x-trackingid a un archivo de texto almacenado en el directorio Logs\VT. El Umbral hash especificado filtra ciertos ID de seguimiento del conjunto de datos, creando así un conjunto de datos que se muestra con un factor de 100. Dado que no se especifica ningún período de rotación de archivos, cada archivo contiene datos de un día del calendario. Los nombres de los archivos de salida tienen el formato predeterminado [!DNL %yyyy%%mm%%dd%-%x-mask%.txt].

![](assets/cfg_VisualTransform_SampledExample.png)

## División de archivos de registro por sección de sitio web {#section-2cac205cd3934d31abb6c6ed8780196d}

Lo siguiente [!DNL Transform.cfg] window proporciona instrucciones para leer [!DNL .vsl]archivos del directorio Logs y exporte los campos x-timestring y x-trackingid a un archivo de texto almacenado en el directorio Logs\VT. La transformación de la expresión regular ( [!DNL RETransform]) toma como entrada el campo cs-uri-stem y crea un nuevo campo (sitio x) que define una sección del sitio. El campo x-site se incluye en el nombre de los archivos de texto de salida, cada uno de los cuales contiene datos de un día del calendario.

![](assets/cfg_VisualTransform_SplittingExample.png)
