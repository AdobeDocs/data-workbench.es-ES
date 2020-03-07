---
description: Información importante que debe tenerse en cuenta al editar el archivo Transformation.cfg.
solution: Analytics
title: Consideraciones para el archivo de configuración de transformación
topic: Data workbench
uuid: 1b64d023-966d-4f84-beb6-4f02b3504eea
translation-type: tm+mt
source-git-commit: 27600561841db3705f4eee6ff0aeb8890444bbc9

---


# Consideraciones para el archivo de configuración de transformación{#considerations-for-the-transformation-configuration-file}

Información importante que debe tenerse en cuenta al editar el archivo Transformation.cfg.

* Cambiar cualquiera de los parámetros de este archivo requiere la retransformación de los datos.
* Si vuelve a procesar los datos, puede comprobar el [!DNL Transformation Progress] parámetro en el informe del área de trabajo de datos [!DNL Processing Legend].

   Para obtener información sobre el reprocesamiento de datos o [!DNL Processing Legend,] consulte [Reprocesamiento y retransformación](../../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md).

* [!DNL CrossRows], [!DNL ODBCLookup], [!DNL Sessionize]y [!DNL AppendURI] las transformaciones solo funcionan cuando se definen en un [!DNL Transformation Dataset Configuration] archivo. Para obtener información sobre estas transformaciones, consulte Transformaciones [de datos](../../../home/c-dataset-const-proc/c-data-trans/c-abt-transf.md).

   >[!NOTE]
   >
   >Adobe recomienda definir transformaciones para la fase de transformación de la construcción de conjuntos de datos en uno o varios [!DNL Transformation Dataset Include] archivos. Para obtener más información, consulte [Transformation Dataset Include Files](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-trans-dataset-inc-files.md#concept-c64aa78ed9ce40b8a0f4932c82ff5ace)(Transformación de conjuntos de datos incluir archivos).

* Puede agregar cualquiera de los parámetros descritos anteriormente al archivo [!DNL Transformation.cfg] abriendo y editando el archivo en el Bloc de notas. Los cambios que realice y guarde aparecerán cuando vuelva a abrir el archivo en el área de trabajo de datos. Al agregar un parámetro nuevo, utilice la tecla Espacio (no la tecla Tab) para sangrar dos (2) espacios a la derecha del nivel de encabezado anterior.

   Cualquier error que se produzca durante la fase de transformación del proceso de construcción del conjunto de datos para un perfil de conjunto de datos se muestra en el [!DNL Profiles] nodo de la interfaz en el área de trabajo de datos [!DNL Detailed Status] . Para obtener información sobre la [!DNL Detailed Status] interfaz, consulte la Guía *del usuario de*&#x200B;Área de trabajo de datos.

