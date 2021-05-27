---
description: Data Workbench proporciona un conjunto de transformaciones que permiten al servidor de Data Workbench incorporar datos de búsqueda en el conjunto de datos.
title: Integración de datos de búsqueda
uuid: 35fd48f7-c0c4-4a83-919d-c15902f27495
exl-id: 150d3aae-4431-488f-8f19-b522637ee935
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '262'
ht-degree: 2%

---

# Integración de datos de búsqueda{#integrating-lookup-data}

Data Workbench proporciona un conjunto de transformaciones que permiten al servidor de Data Workbench incorporar datos de búsqueda en el conjunto de datos.

Los datos de búsqueda son datos externos de bases de datos corporativas o archivos de búsqueda que se pueden combinar con datos de evento para crear el conjunto de datos. En general, los datos de búsqueda se utilizan para aumentar los datos de evento de las fuentes de registro. Conceptualmente, se puede pensar en usar datos de búsqueda para rellenar registros de datos de evento con columnas de información adicionales.

Cuando se utilizan datos de búsqueda, los datos se cargan en una tabla de búsqueda residente en memoria. Una columna de la tabla debe contener una clave común que también exista en los registros de datos de evento. Los datos de la propia tabla de búsqueda se pueden cargar desde un archivo plano o desde un origen de datos ODBC. Los datos de búsqueda se pueden incorporar al conjunto de datos durante la fase de procesamiento de registros o transformación del proceso de construcción del conjunto de datos.

Para incorporar datos de búsqueda, primero debe generar un archivo de búsqueda o tener la información necesaria para acceder a una base de datos SQL y luego definir una o más de las siguientes transformaciones en los archivos de configuración del conjunto de datos para el procesamiento y la transformación del registro.

**Para integrar los datos de búsqueda en el conjunto de datos**

1. Genere el archivo de búsqueda. Consulte [Rellenado de la tabla de búsqueda](../../../../home/c-dataset-const-proc/c-data-trans/c-int-lookup-data/c-pop-lookup-table.md#concept-dd761338731a40e0997c33dfdabdcdf8).
1. Defina uno de los siguientes tipos de transformaciones en el parámetro Transformations en el archivo de configuración del conjunto de datos correspondiente:

   * [!DNL Categorize]
   * [!DNL FlatFileLookup]
   * [!DNL ODBCLookup]

>[!NOTE]
>
>Tenga en cuenta que la transformación [!DNL ODBCLookup] solo funciona cuando se define en el archivo [!DNL Transformation.cfg] o en un archivo [!DNL Transformation Dataset Include].
