---
description: Información conceptual a tener en cuenta al editar el archivo Log Processing.cfg.
title: Consideraciones para el archivo de configuración de procesamiento de registros
uuid: 2ccedf63-12d9-40e9-912a-aee030191b1e
exl-id: 278a4a10-d382-4d9f-b3f4-bcc4783eb50c
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '306'
ht-degree: 4%

---

# Consideraciones para el archivo de configuración de procesamiento de registros{#considerations-for-the-log-processing-configuration-file}

{{eol}}

Información conceptual a tener en cuenta al editar el archivo Log Processing.cfg.

* Los archivos de datos no deben moverse entre directorios una vez que se hayan definido las fuentes de un conjunto de datos. Los únicos archivos adicionales que debe recibir un directorio son los recién creados que resultan del servidor de Data Workbench que recibe datos de los sensores.
* Para cambiar cualquiera de los parámetros de este archivo es necesario volver a procesar todos los datos. El parámetro Pausa en la variable [!DNL Log Processing Mode.cfg] para que se produzca el reprocesamiento, el archivo debe estar definido en false . (Tenga en cuenta que el valor predeterminado de este parámetro es false, por lo que puede que no sea necesario cambiar el parámetro). Para obtener información sobre la variable [!DNL Log Processing Mode.cfg] archivo, consulte [Archivos de configuración adicionales](../../../home/c-dataset-const-proc/c-add-config-files/c-add-config-files.md#concept-1afef4f88f1e467ab4326875fd1d3004).

* Si vuelve a procesar los datos, puede comprobar el parámetro Progreso del procesamiento de registros en el informe [!DNL Processing Legend].

   Para obtener información sobre cómo reprocesar los datos, consulte [Reprocesamiento y retransformación](../../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md). Consulte [Leyenda de procesamiento](../../../home/c-get-started/c-admin-intrf/c-pro-lgd.md#concept-233e27c9c84c426f8c178a27cc7ff828).

* La variable [!DNL Log Processing.cfg] se puede compartir con varios perfiles de conjuntos de datos. Transformaciones definidas en la variable [!DNL Log Processing.cfg] se aplican a todos los perfiles de conjuntos de datos que comparten este archivo de configuración.

   >[!NOTE]
   >
   >Adobe recomienda definir transformaciones para el procesamiento de registros en uno o más procesos de registro [!DNL dataset include] archivos. Para obtener más información, consulte [Archivos de inclusión de conjunto de datos de procesamiento de registros](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-log-proc-dataset-inc-files/c-log-proc-dataset-inc-files.md#concept-999475a22519432e98844622ca95b6ab).

* Puede agregar cualquiera de los parámetros descritos anteriormente al [!DNL Log Processing.cfg] abriendo y editando el archivo en el Bloc de notas. Los cambios que realice y guarde aparecerán cuando vuelva a abrir el archivo en Data Workbench. Al añadir un nuevo parámetro, utilice la tecla Space (no la tecla Tab) para sangrar dos espacios (2) a la derecha del nivel de encabezado anterior.

   Todos los errores que se producen durante la fase de procesamiento del registro del proceso de construcción del conjunto de datos para un perfil del conjunto de datos se muestran en la [!DNL Profiles] nodo de la variable [!DNL Detailed Status] en Data Workbench. Para obtener información sobre la variable [!DNL Detailed Status] , consulte la *Guía del usuario de Data Workbench*.
