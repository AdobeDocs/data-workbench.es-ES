---
description: El archivo Transformation.cfg controla la fase de transformación de la construcción del conjunto de datos durante la cual se aplican transformaciones de datos adicionales a los datos que ya se han procesado durante el procesamiento del registro para crear dimensiones ampliadas que se utilizarán en el análisis.
title: Acerca del archivo de configuración de transformación
uuid: 56e11b71-1a86-47d4-8d2a-2795532b0770
exl-id: 860562d7-6ed3-486b-9f62-1bd06878bf7e
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '176'
ht-degree: 5%

---

# Acerca del archivo de configuración de transformación{#about-the-transformation-configuration-file}

{{eol}}

El archivo Transformation.cfg controla la fase de transformación de la construcción del conjunto de datos durante la cual se aplican transformaciones de datos adicionales a los datos que ya se han procesado durante el procesamiento del registro para crear dimensiones ampliadas que se utilizarán en el análisis.

Debe editar la variable [!DNL Transformation.cfg] para realizar cualquiera de las siguientes tareas de configuración del conjunto de datos:

* Filtrado de datos del procesamiento de registros definiendo la variable [!DNL log entry condition] para transformación.
* Configuración de la zona horaria que se utilizará para crear dimensiones horarias y realizar conversiones horarias. Consulte [Zonas horarias](../../../home/c-dataset-const-proc/c-trans-config-file/c-spec-trans-param/c-time-zones.md#concept-9cf16b1cb4874f7d85e1dd950fdb4956).

>[!NOTE]
>
>[!DNL Transformation Dataset Include] los archivos pueden contener instrucciones adicionales para la fase de transformación de la construcción del conjunto de datos. Estos archivos existen en el directorio Dataset\Transformation de cualquier perfil heredado y normalmente definen parámetros específicos de la aplicación (como parámetros de configuración específicos de la web para la variable [!DNL Site] aplicación). Para obtener información sobre [!DNL Transformation Dataset Include] archivos, consulte [Archivos de inclusión de conjunto de datos](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-abt-dataset-inc-files.md). Para obtener información sobre los parámetros de configuración específicos de la web para el sitio, consulte [Ajustes de configuración para datos web](../../../home/c-dataset-const-proc/c-config-web-data/c-config-web-data.md#concept-9a306b65483a484bb3f6f3c1d7e77519).
