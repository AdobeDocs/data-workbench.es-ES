---
description: El archivo Transformation.cfg controla la fase de transformación de la construcción de conjuntos de datos durante la cual se aplican transformaciones de datos adicionales a los datos ya procesados durante el procesamiento del registro para crear dimensiones ampliadas que se utilizarán en el análisis.
solution: Analytics
title: Acerca del archivo de configuración de transformación
topic: Data workbench
uuid: 56e11b71-1a86-47d4-8d2a-2795532b0770
translation-type: tm+mt
source-git-commit: 27600561841db3705f4eee6ff0aeb8890444bbc9

---


# Acerca del archivo de configuración de transformación{#about-the-transformation-configuration-file}

El archivo Transformation.cfg controla la fase de transformación de la construcción de conjuntos de datos durante la cual se aplican transformaciones de datos adicionales a los datos ya procesados durante el procesamiento del registro para crear dimensiones ampliadas que se utilizarán en el análisis.

Debe editar el [!DNL Transformation.cfg] archivo para realizar cualquiera de las siguientes tareas de configuración del conjunto de datos:

* Filtrado de datos del procesamiento de registros definiendo el [!DNL log entry condition] formulario de transformación.
* Configuración del huso horario que se utilizará para crear dimensiones horarias y realizar conversiones horarias. Consulte [Husos](../../../home/c-dataset-const-proc/c-trans-config-file/c-spec-trans-param/c-time-zones.md#concept-9cf16b1cb4874f7d85e1dd950fdb4956)horarios.

>[!NOTE]
>
>[!DNL Transformation Dataset Include] los archivos pueden contener instrucciones adicionales para la fase de transformación de la construcción de conjuntos de datos. Estos archivos existen en el directorio Dataset\Transformation para cualquier perfil heredado y generalmente definen parámetros específicos de la aplicación (como parámetros de configuración específicos de Web para la [!DNL Site] aplicación). Para obtener información sobre [!DNL Transformation Dataset Include] los archivos, consulte [Conjunto de datos Incluir archivos](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-abt-dataset-inc-files.md). Para obtener información sobre los parámetros de configuración específicos de la web para el sitio, consulte Configuración [de configuración para datos](../../../home/c-dataset-const-proc/c-config-web-data/c-config-web-data.md#concept-9a306b65483a484bb3f6f3c1d7e77519)web.

