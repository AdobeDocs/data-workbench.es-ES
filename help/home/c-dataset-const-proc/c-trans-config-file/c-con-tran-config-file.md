---
description: Información importante a tener en cuenta al editar el archivo Transformation.cfg.
title: Consideraciones sobre el archivo de configuración de transformación
uuid: 1b64d023-966d-4f84-beb6-4f02b3504eea
exl-id: 7164ccb5-269c-4968-a3b4-1ff046a57f92
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '207'
ht-degree: 5%

---

# Consideraciones sobre el archivo de configuración de transformación{#considerations-for-the-transformation-configuration-file}

{{eol}}

Información importante a tener en cuenta al editar el archivo Transformation.cfg.

* Cambiar cualquiera de los parámetros de este archivo requiere la retransformación de los datos.
* Si vuelve a procesar los datos, puede comprobar la variable [!DNL Transformation Progress] en el [!DNL Processing Legend].

   Para obtener información sobre el reprocesamiento de los datos o el [!DNL Processing Legend,] see [Reprocesamiento y retransformación](../../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md).

* [!DNL CrossRows], [!DNL ODBCLookup], [!DNL Sessionize]y [!DNL AppendURI] las transformaciones solo funcionan cuando se definen en una [!DNL Transformation Dataset Configuration] archivo. Para obtener información sobre estas transformaciones, consulte [Transformaciones de datos](../../../home/c-dataset-const-proc/c-data-trans/c-abt-transf.md).

   >[!NOTE]
   >
   >Adobe recomienda definir transformaciones para la fase de transformación de la construcción de conjuntos de datos en uno o más [!DNL Transformation Dataset Include] archivos. Para obtener más información, consulte [Archivos de inclusión de conjunto de datos de transformación](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-trans-dataset-inc-files.md#concept-c64aa78ed9ce40b8a0f4932c82ff5ace).

* Puede agregar cualquiera de los parámetros descritos anteriormente al [!DNL Transformation.cfg] abriendo y editando el archivo en el Bloc de notas. Los cambios que realice y guarde aparecerán cuando vuelva a abrir el archivo en Data Workbench. Al añadir un nuevo parámetro, utilice la tecla Space (no la tecla Tab) para sangrar dos espacios (2) a la derecha del nivel de encabezado anterior.

   Todos los errores que se producen durante la fase de transformación del proceso de construcción del conjunto de datos para un perfil del conjunto de datos se muestran en la [!DNL Profiles] nodo de la variable [!DNL Detailed Status] en Data Workbench. Para obtener información sobre la variable [!DNL Detailed Status] , consulte la *Guía del usuario de Data Workbench*.
