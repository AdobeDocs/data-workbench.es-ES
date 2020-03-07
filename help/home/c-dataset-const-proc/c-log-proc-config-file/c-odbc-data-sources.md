---
description: El servidor del área de trabajo de datos (InsightServer64.exe) puede leer datos de eventos de cualquier base de datos SQL (por ejemplo, Oracle o Microsoft SQL Server) que tenga un controlador compatible con ODBC 3.0.
solution: Analytics
title: Orígenes de datos ODBC
topic: Data workbench
uuid: 5b37cd41-2d79-472c-8e6d-00ff894991a9
translation-type: tm+mt
source-git-commit: 27600561841db3705f4eee6ff0aeb8890444bbc9

---


# Orígenes de datos ODBC{#odbc-data-sources}

El servidor del área de trabajo de datos (InsightServer64.exe) puede leer datos de eventos de cualquier base de datos SQL (por ejemplo, Oracle o Microsoft SQL Server) que tenga un controlador compatible con ODBC 3.0.

La compatibilidad ODBC del servidor del área de trabajo de datos es similar a la compatibilidad existente para cargar datos desde sensores o desde archivos de registro generados por procesos externos. Sin embargo, hay algunas consideraciones y limitaciones adicionales:

* La compatibilidad ODBC del servidor del área de trabajo de datos es compatible con las capacidades de agrupación en clúster. Los datos se distribuyen entre todos los servidores de procesamiento y todo el procesamiento posterior (incluido el procesamiento de consultas) se beneficia plenamente de la agrupación en clúster.
* La compatibilidad con ODBC depende de controladores ODBC de terceros. Para que la compatibilidad con ODBC funcione, estos controladores deben configurarse en el equipo en el que se ejecuta el servidor del área de trabajo de datos, mediante herramientas externas a la plataforma de Adobe. Los equipos del área de trabajo de datos no requieren ninguna configuración adicional.
* La tabla o vista desde la que se cargan los datos debe tener una columna de ID cada vez mayor. Para cualquier fila, el valor de esta columna (que puede ser una columna real en la tabla o cualquier expresión de columna SQL) no debe disminuir a medida que se inserten nuevas filas en la base de datos. Si se infringe esta restricción, se pierden los datos. Para un rendimiento adecuado, se requiere un índice en esta columna o expresión de columna.

   >[!NOTE]
   >
   >Es posible que varias filas tengan el mismo valor en la [!DNL Increasing ID] columna. Una posibilidad es una columna de marca de hora con una precisión inferior a la perfecta.

* El servidor del área de trabajo de datos no puede cargar columnas con datos largos (datos superiores a una longitud determinada según la aplicación de base de datos específica en uso).
* Recuperar datos de una base de datos es más lento que leerlos desde un archivo de disco. Los conjuntos de datos que cargan datos desde un origen ODBC tardan mucho más en procesarse (sobre todo cuando se reprocesan) que los conjuntos de datos de tamaño equivalente cuyos datos proceden de sensores u otros archivos de disco.

Para obtener información sobre el reprocesamiento de los datos, consulte [Reprocesamiento y retransformación](../../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md).

**Para configurar Insight Server para ODBC[!DNL event data]**

La configuración del servidor del área de trabajo de datos para cargar datos desde una base de datos SQL requiere que realice primero los siguientes pasos en orden:

1. Instale el software de cliente de base de datos adecuado, incluido un controlador ODBC, en el equipo de servidor del área de trabajo de datos en el que se procesa el conjunto de datos.

   >[!NOTE]
   >
   >Si está cargando datos de eventos ODBC para su procesamiento en un clúster de servidores del área de trabajo de datos, debe instalar el software de cliente de la base de datos en todos los servidores de procesamiento del clúster. Para obtener información sobre cómo especificar servidores de procesamiento en un clúster, consulte la Guía *de instalación y administración de productos de* servidor.

1. Configure una fuente de datos mediante el Administrador de fuentes de datos ODBC para Windows.

   Es importante tener en cuenta que el servidor del área de trabajo de datos (InsightServer64.exe) se ejecuta como un servicio de Windows. Por lo tanto, la fuente de datos normalmente debe configurarse como DSN del sistema en lugar de como DSN del usuario para que el servidor del área de trabajo de datos pueda utilizarla. Puede encontrar más información sobre este paso de configuración en la documentación del software de la base de datos.

Después de instalar el software de cliente de base de datos en el equipo de servidor del área de trabajo de datos correspondiente, puede configurar el conjunto de datos para que utilice el origen de datos ODBC editando los parámetros adecuados en el archivo de configuración del perfil deseado [!DNL Log Processing] .

## Parámetros {#section-15c0218d93364693a565f2609a12f73e}

Para los datos de bases de datos que utilizan el estándar ODBC (Conectividad abierta de bases de datos), están disponibles los siguientes parámetros:

<table id="table_606D8A90DA4A43C29F2C6130F8C753F8"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parámetro </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Nombre </td> 
   <td colname="col2"> Identificador del origen ODBC. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Nombre de la fuente de datos </td> 
   <td colname="col2"> Un DSN, proporcionado por un administrador del equipo del servidor del área de trabajo de datos en el que se procesa el conjunto de datos, que hace referencia a la base de datos desde la que se van a cargar los datos. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Contraseña de base de datos </td> 
   <td colname="col2"> La contraseña que se utilizará al conectarse a la base de datos. Si se ha configurado una contraseña para el DSN en el Administrador <span class="wintitle"></span>de fuentes de datos, esto puede dejarse en blanco. Cualquier contraseña proporcionada aquí anula la contraseña configurada para el DSN en el Administrador <span class="wintitle"> de fuentes de datos</span>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ID de usuario de base de datos </td> 
   <td colname="col2"> ID de usuario que se utilizará al conectarse a la base de datos. Si se ha configurado un ID de usuario para el DSN en el Administrador <span class="wintitle"></span>de fuentes de datos, esto puede dejarse en blanco. Cualquier ID de usuario proporcionado aquí anula el ID de usuario configurado para el DSN en el Administrador <span class="wintitle"></span>de fuentes de datos. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Campos </td> 
   <td colname="col2"> Un vector de objetos de columna que especifica una asignación de las columnas de datos de la base de datos a los campos de datos del motor de ejecución del servidor del área de trabajo de datos. Cada columna tiene entradas <span class="wintitle"> Nombre</span> de columna y Nombre <span class="wintitle"> de campo</span>. <span class="wintitle"> Nombre</span> de columna es una expresión de columna SQL que debe ser válida en el contexto de la tabla identificada por el identificador <span class="wintitle"> de</span> tabla descrito anteriormente. Puede ser un nombre de columna o cualquier expresión SQL basada en cualquier número de columnas de la tabla. Puede ser necesaria una función de formato para convertir valores de ciertos tipos de datos en cadenas de forma que no se pierda la precisión. Todos los datos se convierten implícitamente en cadenas mediante el método de formato predeterminado de la base de datos, lo que puede causar la pérdida de datos para algunos tipos de datos de columna (como los tipos de datos de fecha y hora) si no se utilizan expresiones de formato explícitas. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Aumento de la columna de ID </td> 
   <td colname="col2"> <p>Nombre de columna o expresión de columna SQL que cumple el criterio de que aumenta (o al menos no disminuye) a medida que se agregan nuevas filas. Es decir, si se agrega la fila B a la tabla en un momento posterior a la fila A, el valor de esta columna (o expresión de columna) en la fila B debe ser bueno (según el orden de clasificación nativo de la base de datos) que el valor correspondiente en la fila A. </p> <p> 
     <ul id="ul_EBF6AEE4746B41B3B5BB6CC74194DAED"> 
      <li id="li_A5C9BE52B01649DE9726ECEC68B99828"> El <span class="wintitle"> </span>nombre de columna de ID creciente puede ser el mismo que el nombre de una columna existente, pero no es necesario. </li> 
      <li id="li_CF69EAB4AFB14F4894F7A5CDCAF06947"> Se supone que esta expresión tiene un tipo de datos de caracteres SQL. Si la columna de ID de aumento real es de otro tipo de datos, este valor debe ser una expresión de columna para convertirla en una cadena. Dado que esto generalmente significa que las comparaciones son lexicográficas (carácter por carácter), es importante dar un formato al valor cuidadosamente. </li> 
      <li id="li_58977431962E48039C898CFC47C53323"> La expresión se utiliza en las cláusulas SQL ORDER BY y se compara con las cláusulas SQL WHERE. Es de vital importancia tener un índice creado en la expresión exacta de columna que se utiliza. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ID de origen de registro </td> 
   <td colname="col2"> <p>El valor de este parámetro puede ser cualquier cadena. Si se especifica un valor, este parámetro permite diferenciar las entradas de registro de diferentes fuentes de registro para la identificación de origen o el procesamiento dirigido. El campo x-log-source-id se rellena con un valor que identifica el origen del registro para cada entrada de registro. Por ejemplo, si desea identificar entradas de registro de un origen ODBC llamado ODBCSource01, puede escribir <span class="filepath"> desde ODBCSource01.</span> y esa cadena se pasaría al campo x-log-source-id por cada entrada de registro de esa fuente. </p> <p> Para obtener información sobre el campo x-log-source-id, consulte <a href="../../../home/c-dataset-const-proc/c-ev-data-rec-fields.md#concept-06bda4be1a4649a2905a4422e9e6c42f"> Campos</a>de registro de datos de eventos. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Ejecutar en el servidor </td> 
   <td colname="col2"> Valor de índice en el archivo <span class="filepath"> profile.cfg</span> del servidor de procesamiento que realiza las consultas ODBC para obtener datos de la base de datos. (El parámetro Servidores de procesamiento del archivo <span class="filepath"> profile.cfg</span> enumera todos los servidores de procesamiento del conjunto de datos y cada servidor tiene un valor de índice, siendo el primero 0.) El valor predeterminado es 0. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Identificador de tabla </td> 
   <td colname="col2"> Expresión SQL que asigna un nombre a la tabla o vista desde la que se van a cargar los datos. Un identificador de tabla típico tiene el formato SCHEMA.TABLE. </td> 
  </tr> 
 </tbody> 
</table>

Este ejemplo muestra la ventana de configuración en el área de trabajo de datos con un origen de datos ODBC. [!DNL Log Processing] Esta fuente de datos toma datos de una tabla llamada [!DNL VISUAL.VSL] en una base de datos con [!DNL Data Source Name] &quot;VSTestO&quot;. Cinco (5) objetos de columna ( [!DNL Fields]) asignan datos de las columnas de datos de la base de datos al servidor del área de trabajo de datos.

![](assets/cfg_LogProcessing_LogSources_ODBC.png)

