---
description: Información sobre cómo especificar parámetros en el archivo Transform.cfg en función de los distintos escenarios.
solution: Analytics
title: Archivos Transform.cfg de Área de trabajo de datos de muestra
topic: Data workbench
uuid: cb473a5a-54e2-4bf7-84fb-c9c27910ef64
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Archivos Transform.cfg de Área de trabajo de datos de muestra{#sample-data-workbench-transform-cfg-files}

Información sobre cómo especificar parámetros en el archivo Transform.cfg en función de los distintos escenarios.

* [Un archivo Transform.cfg de perspectiva simple](../../../../../home/c-dataset-const-proc/c-transf-func/c-config-files-transf/t-ins-transf-file/c-sample-transf-files.md#section-b7e83cafa3a947c597bd09d316930190)
* [Salida con valores separados por comas](../../../../../home/c-dataset-const-proc/c-transf-func/c-config-files-transf/t-ins-transf-file/c-sample-transf-files.md#section-03916934ad574efc8695abbae54a1816)
* [Archivos de registro de muestra](../../../../../home/c-dataset-const-proc/c-transf-func/c-config-files-transf/t-ins-transf-file/c-sample-transf-files.md#section-113b3b0c0c7547ea9536bb2f465c0875)
* [División de archivos de registro por sección del sitio Web](../../../../../home/c-dataset-const-proc/c-transf-func/c-config-files-transf/t-ins-transf-file/c-sample-transf-files.md#section-2cac205cd3934d31abb6c6ed8780196d)

En cada muestra, el archivo se muestra como una [!DNL Transform.cfg] ventana en el área de trabajo de datos.

## Archivo Transform.cfg de Área de trabajo de datos simple {#section-b7e83cafa3a947c597bd09d316930190}

La siguiente [!DNL Transform.cfg] ventana proporciona instrucciones para leer [!DNL .vsl] archivos del [!DNL Logs] directorio y exportar los campos x-timestring y x-trackingid a un archivo de texto almacenado en el directorio Logs\VT. Dado que no se especifica un período de rotación de archivos ni un formato de nombre de archivo de salida, cada archivo contiene datos de un día natural y tiene un nombre en el formato predeterminado [!DNL %yyyy%%mm%%dd%-%x-mask%.txt].

![](assets/cfg_VisualTransform_SimpleExample.png)

## Salida con valores separados por comas {#section-03916934ad574efc8695abbae54a1816}

La siguiente [!DNL Transform.cfg] ventana proporciona instrucciones para leer [!DNL .vsl] archivos del directorio Registros y exportar los campos 0 a 13 a un archivo delimitado por comas ( [!DNL .csv]) almacenado en el directorio Logs\VT\CSV directory. Dado que no se especifica ningún período de rotación de archivos, cada archivo contiene datos de un día natural. Los archivos de salida son [!DNL .csv] archivos con el nombre en formato [!DNL %yyyy%%mm%%dd%-%x-mask%.csv].

![](assets/cfg_VisualTransform_CSVExample.png)

## Archivos de registro de muestra {#section-113b3b0c0c7547ea9536bb2f465c0875}

Puede configurar la funcionalidad de transformación para crear y mantener una versión compacta y actualizada de los archivos de registro completos. Esto le permite probar rápidamente las configuraciones del conjunto de datos, con tiempos de reprocesamiento de segundos o minutos en lugar de horas necesarias para volver a procesar todo el conjunto de datos. El siguiente ejemplo proporciona un ejemplo de cómo configurar la funcionalidad de transformación para realizar esto.

La siguiente [!DNL Transform.cfg] ventana proporciona instrucciones para leer [!DNL .vsl] archivos del directorio Registros y exportar los campos x-timestring y x-trackingid a un archivo de texto almacenado en el directorio Registros\VT. El Umbral hash especificado filtra ciertos ID de seguimiento del conjunto de datos, creando así un conjunto de datos que se muestra con un factor de 100. Dado que no se especifica ningún período de rotación de archivos, cada archivo contiene datos de un día natural. Los nombres de los archivos de salida tienen el formato predeterminado [!DNL %yyyy%%mm%%dd%-%x-mask%.txt].

![](assets/cfg_VisualTransform_SampledExample.png)

## División de archivos de registro por sección del sitio Web {#section-2cac205cd3934d31abb6c6ed8780196d}

La siguiente [!DNL Transform.cfg] ventana proporciona instrucciones para leer [!DNL .vsl]archivos del directorio Registros y exportar los campos x-timestring y x-trackingid a un archivo de texto almacenado en el directorio Registros\VT. La transformación de expresión regular ( [!DNL RETransform]) toma como entrada el campo cs-uri-stem y crea un nuevo campo (x-site) que define una sección del sitio. El campo x-site se incluye en el nombre de los archivos de texto de salida, cada uno de los cuales contiene datos de un día calendario.

![](assets/cfg_VisualTransform_SplittingExample.png)

