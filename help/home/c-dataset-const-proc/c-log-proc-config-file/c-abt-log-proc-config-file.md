---
description: El archivo Log Processing.cfg controla la fase de procesamiento de registros de la construcción de conjuntos de datos, durante la cual se leen los datos sin ordenar de las fuentes de datos (denominadas fuentes de registro) y se aplican filtros y transformaciones a los datos.
solution: Analytics
title: Acerca del archivo de configuración de procesamiento de registros
topic: Data workbench
uuid: 1f5f5d75-8a24-4122-adc8-8c8aef916631
translation-type: tm+mt
source-git-commit: 27600561841db3705f4eee6ff0aeb8890444bbc9

---


# Acerca del archivo de configuración de procesamiento de registros{#about-the-log-processing-configuration-file}

El archivo Log Processing.cfg controla la fase de procesamiento de registros de la construcción de conjuntos de datos, durante la cual se leen los datos sin ordenar de las fuentes de datos (denominadas fuentes de registro) y se aplican filtros y transformaciones a los datos.

Debe editar el [!DNL Log Processing.cfg] archivo para realizar cualquiera de las siguientes tareas de configuración del conjunto de datos:

* Especificación de orígenes de registro. Consulte Fuentes [de registro](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md).
* Determinar qué entradas de registro ingresan al conjunto de datos durante el procesamiento del registro. Consulte Filtros [](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md) de datos y Condición [de entrada](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md)de registro.

* Habilitar la división de ID de seguimiento con grandes cantidades de datos de eventos. Consulte División [de clave](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md).
* Configuración de un servidor del área de trabajo de datos para que se ejecute como una unidad de servidor de archivos. Consulte [Configuración de una unidad](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-ins-svr-file-svr-unit.md)de servidor de archivos de Insight Server.
* Configuración de un servidor del área de trabajo de datos para que se ejecute como servidor de normalización centralizada. Consulte [Configuración de una unidad](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-ins-svr-file-svr-unit.md)de servidor de archivos de Insight Server.

>[!NOTE]
>
>[!DNL Log Processing Dataset Include] los archivos pueden contener instrucciones adicionales para la fase de procesamiento de registros de la construcción de conjuntos de datos. Estos archivos existen en el directorio Dataset\Log Processing para cualquier perfil heredado. Generalmente definen parámetros específicos de la aplicación (como parámetros de configuración específicos de la Web para la aplicación del sitio). Para obtener información sobre [!DNL Log Processing Dataset Include] los archivos, consulte [Conjunto de datos Incluir archivos](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-abt-dataset-inc-files.md). Para obtener información sobre los parámetros de configuración específicos de la web para el sitio, consulte Configuración [de configuración para datos](../../../home/c-dataset-const-proc/c-config-web-data/c-config-web-data.md)web.

