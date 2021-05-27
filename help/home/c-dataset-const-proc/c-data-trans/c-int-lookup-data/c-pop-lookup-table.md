---
description: Si utiliza las transformaciones Categorize o FlatFileLookup , la tabla de búsqueda se carga en la memoria y se rellena desde un archivo plano cuya ubicación especifique al definir la transformación.
title: Rellenado de la tabla de búsqueda
uuid: a11f3902-8853-4d22-bbfd-b2a3d143cb7b
exl-id: e83d9feb-44fe-4fa1-b559-e1f5606637b5
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '280'
ht-degree: 2%

---

# Rellenado de la tabla de búsqueda{#populating-the-lookup-table}

Si utiliza las transformaciones Categorize o FlatFileLookup , la tabla de búsqueda se carga en la memoria y se rellena desde un archivo plano cuya ubicación especifique al definir la transformación.

El archivo plano que especifique debe cumplir los siguientes requisitos:

* Cada línea del archivo debe representar una fila de la tabla de búsqueda.
* Las columnas del archivo deben separarse con un delimitador ASCII. Puede utilizar cualquier carácter que no sea un carácter de fin de línea y que no aparezca en ningún lugar dentro de los datos del evento en sí. Al definir la transformación, se especifica qué carácter se ha utilizado para delimitar las columnas del archivo plano.

Si utiliza una transformación [!DNL ODBCLookup], la tabla de búsqueda se carga en la memoria y se rellena desde una tabla o vista de la base de datos [!DNL ODBC] que especifique. Al definir la transformación, también debe especificar el origen de datos, el nombre de usuario y la contraseña que debe utilizar el servidor de Data Workbench para establecer una conexión con la base de datos.

>[!NOTE]
>
>Las tablas de búsqueda se cargan cuando el servidor de Data Workbench comienza a construir el conjunto de datos por primera vez. Una vez establecidos, los archivos de búsqueda no deben cambiarse. Si cambia el archivo plano o la tabla [!DNL ODBC] que se utiliza para la fase de transformación, es necesario que vuelva a transformar todo el conjunto de datos. Si cambia un archivo plano que se utiliza durante la fase de procesamiento del registro, los nuevos datos de búsqueda se aplican a todos los registros nuevos que ingresan al conjunto de datos, pero los cambios no se aplican retroactivamente.
