---
description: Información conceptual a tener en cuenta al editar el archivo Log Processing.cfg.
title: Consideraciones para el archivo de configuración de procesamiento de registros
uuid: 2ccedf63-12d9-40e9-912a-aee030191b1e
exl-id: 278a4a10-d382-4d9f-b3f4-bcc4783eb50c
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '306'
ht-degree: 4%

---

# Consideraciones para el archivo de configuración de procesamiento de registros{#considerations-for-the-log-processing-configuration-file}

Información conceptual a tener en cuenta al editar el archivo Log Processing.cfg.

* Los archivos de datos no deben moverse entre directorios una vez que se hayan definido las fuentes de un conjunto de datos. Los únicos archivos adicionales que debe recibir un directorio son los recién creados que resultan del servidor de Data Workbench que recibe datos de los sensores.
* Para cambiar cualquiera de los parámetros de este archivo es necesario volver a procesar todos los datos. El parámetro Pause del archivo [!DNL Log Processing Mode.cfg] debe establecerse en false para que se produzca el reprocesamiento. (Tenga en cuenta que el valor predeterminado de este parámetro es false, por lo que puede que no sea necesario cambiar el parámetro). Para obtener información sobre el archivo [!DNL Log Processing Mode.cfg], consulte [Archivos de configuración adicionales](../../../home/c-dataset-const-proc/c-add-config-files/c-add-config-files.md#concept-1afef4f88f1e467ab4326875fd1d3004).

* Si vuelve a procesar los datos, puede comprobar el parámetro Progreso del procesamiento de registros en [!DNL Processing Legend] de Data Workbench.

   Para obtener información sobre el reprocesamiento de los datos, consulte [Reprocesamiento y retransformación](../../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md). Consulte [Leyenda de procesamiento](../../../home/c-get-started/c-admin-intrf/c-pro-lgd.md#concept-233e27c9c84c426f8c178a27cc7ff828).

* El archivo [!DNL Log Processing.cfg] se puede compartir mediante varios perfiles de conjuntos de datos. Las transformaciones definidas en el archivo [!DNL Log Processing.cfg] se aplican a todos los perfiles de conjuntos de datos que comparten este archivo de configuración.

   >[!NOTE]
   >
   >Adobe recomienda definir transformaciones para el procesamiento de registros en uno o varios archivos [!DNL dataset include] de procesamiento de registros. Para obtener más información, consulte [Archivos de inclusión de conjunto de datos de procesamiento de registros](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-log-proc-dataset-inc-files/c-log-proc-dataset-inc-files.md#concept-999475a22519432e98844622ca95b6ab).

* Puede agregar cualquiera de los parámetros descritos anteriormente al archivo [!DNL Log Processing.cfg] abriendo y editando el archivo en el Bloc de notas. Los cambios que realice y guarde aparecerán cuando vuelva a abrir el archivo en Data Workbench. Al añadir un nuevo parámetro, utilice la tecla Space (no la tecla Tab) para sangrar dos espacios (2) a la derecha del nivel de encabezado anterior.

   Cualquier error que se produzca durante la fase de procesamiento de registros del proceso de construcción del conjunto de datos para un perfil de conjunto de datos se muestra en el nodo [!DNL Profiles] de la interfaz [!DNL Detailed Status] en Data Workbench. Para obtener más información sobre la interfaz [!DNL Detailed Status], consulte la *Guía del usuario de Data Workbench*.
