---
description: Información importante a tener en cuenta al editar el archivo Transformation.cfg.
title: Consideraciones sobre el archivo de configuración de transformación
uuid: 1b64d023-966d-4f84-beb6-4f02b3504eea
exl-id: 7164ccb5-269c-4968-a3b4-1ff046a57f92
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '207'
ht-degree: 5%

---

# Consideraciones sobre el archivo de configuración de transformación{#considerations-for-the-transformation-configuration-file}

Información importante a tener en cuenta al editar el archivo Transformation.cfg.

* Cambiar cualquiera de los parámetros de este archivo requiere la retransformación de los datos.
* Si vuelve a procesar los datos, puede comprobar el parámetro [!DNL Transformation Progress] en [!DNL Processing Legend] de Data Workbench.

   Para obtener información sobre el reprocesamiento de los datos o el [!DNL Processing Legend,], consulte [Reprocesamiento y retransformación](../../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md).

* [!DNL CrossRows],  [!DNL ODBCLookup],  [!DNL Sessionize] y las  [!DNL AppendURI] transformaciones solo funcionan cuando se definen en un  [!DNL Transformation Dataset Configuration] archivo. Para obtener información sobre estas transformaciones, consulte [Transformaciones de datos](../../../home/c-dataset-const-proc/c-data-trans/c-abt-transf.md).

   >[!NOTE]
   >
   >Adobe recomienda definir transformaciones para la fase de transformación de la construcción del conjunto de datos en uno o más archivos [!DNL Transformation Dataset Include]. Para obtener más información, consulte [Transformation Dataset Include Files](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-trans-dataset-inc-files.md#concept-c64aa78ed9ce40b8a0f4932c82ff5ace).

* Puede agregar cualquiera de los parámetros descritos anteriormente al archivo [!DNL Transformation.cfg] abriendo y editando el archivo en el Bloc de notas. Los cambios que realice y guarde aparecerán cuando vuelva a abrir el archivo en Data Workbench. Al añadir un nuevo parámetro, utilice la tecla Space (no la tecla Tab) para sangrar dos espacios (2) a la derecha del nivel de encabezado anterior.

   Cualquier error que se produzca durante la fase de transformación del proceso de construcción del conjunto de datos para un perfil del conjunto de datos se muestra en el nodo [!DNL Profiles] de la interfaz [!DNL Detailed Status] en Data Workbench. Para obtener más información sobre la interfaz [!DNL Detailed Status], consulte la *Guía del usuario de Data Workbench*.
