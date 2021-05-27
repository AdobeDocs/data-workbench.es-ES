---
description: El archivo Log Processing.cfg controla la fase de procesamiento de registros de la construcción del conjunto de datos, durante la cual se leen los datos sin ordenar de las fuentes de datos (denominadas fuentes de registro) y se aplican filtros y transformaciones a los datos.
title: Acerca del archivo de configuración de procesamiento de registros
uuid: 1f5f5d75-8a24-4122-adc8-8c8aef916631
exl-id: 11ee3298-272d-46c8-bcfe-e485b01606b1
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '238'
ht-degree: 5%

---

# Acerca del archivo de configuración de procesamiento de registros{#about-the-log-processing-configuration-file}

El archivo Log Processing.cfg controla la fase de procesamiento de registros de la construcción del conjunto de datos, durante la cual se leen los datos sin ordenar de las fuentes de datos (denominadas fuentes de registro) y se aplican filtros y transformaciones a los datos.

Debe editar el archivo [!DNL Log Processing.cfg] para realizar cualquiera de las siguientes tareas de configuración del conjunto de datos:

* Especificación de las fuentes de registro. Consulte [Orígenes de registro](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md).
* Determinar qué entradas de registro ingresan al conjunto de datos durante el procesamiento del registro. Consulte [Filtros de datos](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md) y [Condición de entrada de registro](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md).

* Habilitar la división de ID de seguimiento con grandes cantidades de datos de evento. Consulte [División de claves](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md).
* Configuración de un servidor de Data Workbench para que se ejecute como una unidad de servidor de archivos. Consulte [Configuración de una unidad de servidor de archivos de Insight Server](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-ins-svr-file-svr-unit.md).
* Configuración de un servidor de Data Workbench para que se ejecute como servidor de normalización centralizado. Consulte [Configuración de una unidad de servidor de archivos de Insight Server](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-ins-svr-file-svr-unit.md).

>[!NOTE]
>
>[!DNL Log Processing Dataset Include] los archivos pueden contener instrucciones adicionales para la fase de procesamiento de registros de la construcción del conjunto de datos. Estos archivos existen en el directorio Dataset\Log Processing para cualquier perfil heredado. Normalmente definen parámetros específicos de la aplicación (como parámetros de configuración específicos de la web para la aplicación del sitio). Para obtener información sobre los archivos [!DNL Log Processing Dataset Include], consulte [Archivos de inclusión de conjunto de datos](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-abt-dataset-inc-files.md). Para obtener información sobre los parámetros de configuración específicos de la web para el sitio, consulte [Configuración de datos web](../../../home/c-dataset-const-proc/c-config-web-data/c-config-web-data.md).
