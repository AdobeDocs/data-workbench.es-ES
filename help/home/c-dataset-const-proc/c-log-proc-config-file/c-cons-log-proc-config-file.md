---
description: Información conceptual que debe tenerse en cuenta al editar el archivo Log Processing.cfg.
solution: Analytics
title: Consideraciones para el archivo de configuración de procesamiento de registros
topic: Data workbench
uuid: 2ccedf63-12d9-40e9-912a-aee030191b1e
translation-type: tm+mt
source-git-commit: 27600561841db3705f4eee6ff0aeb8890444bbc9

---


# Consideraciones para el archivo de configuración de procesamiento de registros{#considerations-for-the-log-processing-configuration-file}

Información conceptual que debe tenerse en cuenta al editar el archivo Log Processing.cfg.

* Los archivos de datos no deben moverse entre directorios una vez definidas las fuentes de un conjunto de datos. Los únicos archivos adicionales que debe recibir un directorio son los recién creados que resultan del servidor del área de trabajo de datos que recibe datos de los sensores.
* Cambiar cualquiera de los parámetros de este archivo requiere un reprocesamiento de todos los datos. El parámetro Pausar del [!DNL Log Processing Mode.cfg] archivo debe establecerse en false para que se produzca el reprocesamiento. (Tenga en cuenta que el valor predeterminado de este parámetro es false, por lo que puede que no sea necesario cambiar el parámetro). Para obtener información sobre el [!DNL Log Processing Mode.cfg] archivo, consulte Archivos [de configuración](../../../home/c-dataset-const-proc/c-add-config-files/c-add-config-files.md#concept-1afef4f88f1e467ab4326875fd1d3004)adicionales.

* Si vuelve a procesar los datos, puede comprobar el parámetro Progreso del procesamiento de registros en el área de trabajo de datos [!DNL Processing Legend].

   Para obtener información sobre el reprocesamiento de los datos, consulte [Reprocesamiento y retransformación](../../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md). Consulte Leyenda [de procesamiento](../../../home/c-get-started/c-admin-intrf/c-pro-lgd.md#concept-233e27c9c84c426f8c178a27cc7ff828).

* El [!DNL Log Processing.cfg] archivo se puede compartir con varios perfiles de conjunto de datos. Las transformaciones definidas en el [!DNL Log Processing.cfg] archivo se aplican a todos los perfiles de conjuntos de datos que comparten este archivo de configuración.

   >[!NOTE]
   >
   >Adobe recomienda definir transformaciones para el procesamiento de registros en uno o varios [!DNL dataset include] archivos de procesamiento de registros. Para obtener más información, consulte [Log Processing Dataset Include Files (Incluir archivos](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-log-proc-dataset-inc-files/c-log-proc-dataset-inc-files.md#concept-999475a22519432e98844622ca95b6ab)).

* Puede agregar cualquiera de los parámetros descritos anteriormente al archivo [!DNL Log Processing.cfg] abriendo y editando el archivo en el Bloc de notas. Los cambios que realice y guarde aparecerán cuando vuelva a abrir el archivo en el área de trabajo de datos. Al agregar un parámetro nuevo, utilice la tecla Espacio (no la tecla Tab) para sangrar dos (2) espacios a la derecha del nivel de encabezado anterior.

   Cualquier error que se produzca durante la fase de procesamiento de registros del proceso de construcción de conjuntos de datos para un perfil de conjuntos de datos se muestra en el [!DNL Profiles] [!DNL Detailed Status] nodo de la interfaz en el área de trabajo de datos. Para obtener información sobre la [!DNL Detailed Status] interfaz, consulte la Guía *del usuario de*&#x200B;Área de trabajo de datos.

