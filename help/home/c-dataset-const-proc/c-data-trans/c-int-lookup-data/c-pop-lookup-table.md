---
description: Si utiliza las transformaciones Categorize o FlatFileLookup, la tabla de búsqueda se carga en memoria y se rellena desde un archivo plano cuya ubicación se especifique al definir la transformación.
solution: Analytics
title: Rellenado de la tabla de búsqueda
topic: Data workbench
uuid: a11f3902-8853-4d22-bbfd-b2a3d143cb7b
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Rellenado de la tabla de búsqueda{#populating-the-lookup-table}

Si utiliza las transformaciones Categorize o FlatFileLookup, la tabla de búsqueda se carga en memoria y se rellena desde un archivo plano cuya ubicación se especifique al definir la transformación.

El archivo plano que especifique debe cumplir los siguientes requisitos:

* Cada línea del archivo debe representar una fila en la tabla de búsqueda.
* Las columnas del archivo deben separarse con un delimitador ASCII. Puede utilizar cualquier carácter que no sea un carácter de fin de línea y que no aparezca en ninguna parte de los datos del evento. Cuando se define la transformación, se especifica qué carácter se ha utilizado para delimitar las columnas del archivo sin formato.

Si utiliza una [!DNL ODBCLookup] transformación, la tabla de búsqueda se carga en la memoria y se completa desde una tabla o vista en una [!DNL ODBC] base de datos que especifique. Al definir la transformación, también debe especificar el origen de datos, el nombre de usuario y la contraseña que debe utilizar el servidor del área de trabajo de datos para establecer una conexión con la base de datos.

>[!NOTE]
>
>Las tablas de búsqueda se cargan cuando el servidor del área de trabajo de datos comienza por primera vez a construir el conjunto de datos. Una vez establecidos, los archivos de búsqueda no deben modificarse. Si cambia el archivo plano o la tabla que se utiliza para la fase de transformación, es necesario que vuelva a transformar todo el conjunto de datos. [!DNL ODBC] Si cambia un archivo plano que se utiliza durante la fase de procesamiento del registro, los nuevos datos de búsqueda se aplican a todos los registros nuevos que ingresan al conjunto de datos, pero los cambios no se aplican de forma retroactiva.

