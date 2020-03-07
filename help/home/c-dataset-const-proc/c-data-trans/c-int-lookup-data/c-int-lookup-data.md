---
description: El área de trabajo de datos proporciona un conjunto de transformaciones que permite al servidor del área de trabajo de datos incorporar datos de búsqueda en el conjunto de datos.
solution: Analytics
title: Integración de datos de búsqueda
topic: Data workbench
uuid: 35fd48f7-c0c4-4a83-919d-c15902f27495
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Integración de datos de búsqueda{#integrating-lookup-data}

El área de trabajo de datos proporciona un conjunto de transformaciones que permite al servidor del área de trabajo de datos incorporar datos de búsqueda en el conjunto de datos.

Los datos de búsqueda son datos externos de bases de datos corporativas o archivos de búsqueda que se pueden combinar con datos de eventos para crear el conjunto de datos. En general, los datos de búsqueda se utilizan para aumentar los datos del evento a partir de los orígenes de registro. Conceptualmente, se puede pensar en utilizar los datos de búsqueda para rellenar los registros de datos de eventos con columnas de información adicionales.

Cuando se utilizan datos de búsqueda, los datos se cargan en una tabla de búsqueda residente en la memoria. Una columna de la tabla debe contener una clave común que también exista en los registros de datos del evento. Los datos de la propia tabla de búsqueda se pueden cargar desde un archivo plano o desde un origen de datos ODBC. Los datos de búsqueda se pueden incorporar al conjunto de datos durante la fase de procesamiento o transformación del registro del proceso de construcción del conjunto de datos.

Para incorporar datos de búsqueda, primero debe generar un archivo de búsqueda o tener la información necesaria para acceder a una base de datos SQL y luego definir una o más de las siguientes transformaciones en los archivos de configuración del conjunto de datos para el procesamiento y la transformación del registro.

**Para integrar datos de búsqueda en el conjunto de datos**

1. Genere el archivo de búsqueda. Consulte [Rellenado de la tabla](../../../../home/c-dataset-const-proc/c-data-trans/c-int-lookup-data/c-pop-lookup-table.md#concept-dd761338731a40e0997c33dfdabdcdf8)de búsqueda.
1. Defina uno de los siguientes tipos de transformaciones en el parámetro Transformations en el archivo de configuración del conjunto de datos correspondiente:

   * [!DNL Categorize]
   * [!DNL FlatFileLookup]
   * [!DNL ODBCLookup]

>[!NOTE]
>
>Tenga en cuenta que la [!DNL ODBCLookup] transformación solo funciona cuando se define en el [!DNL Transformation.cfg] archivo o en un [!DNL Transformation Dataset Include] archivo.

