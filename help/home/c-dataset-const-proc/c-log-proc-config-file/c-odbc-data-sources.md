---
description: El servidor de Data Workbench (InsightServer64.exe) puede leer datos de eventos de cualquier base de datos SQL (por ejemplo, Oracle o Microsoft SQL Server) que tenga un controlador compatible con ODBC 3.0.
title: Fuentes de datos ODBC
uuid: 5b37cd41-2d79-472c-8e6d-00ff894991a9
exl-id: b22b1e27-9b6c-4708-b45c-a9605807689a
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '1245'
ht-degree: 1%

---

# Fuentes de datos ODBC{#odbc-data-sources}

El servidor de Data Workbench (InsightServer64.exe) puede leer datos de eventos de cualquier base de datos SQL (por ejemplo, Oracle o Microsoft SQL Server) que tenga un controlador compatible con ODBC 3.0.

La compatibilidad ODBC del servidor de Data Workbench es similar a la compatibilidad existente para cargar datos de sensores o de archivos de registro generados por procesos externos. Sin embargo, hay algunas consideraciones y limitaciones adicionales:

* La compatibilidad ODBC del servidor de Data Workbench es compatible con las capacidades de agrupación en clúster. Los datos se distribuyen entre todos los servidores de procesamiento, y todo el procesamiento posterior (incluido el procesamiento de consultas) se beneficia totalmente de la agrupación en clúster.
* La compatibilidad con ODBC depende de controladores ODBC de terceros. Para que funcione la compatibilidad con ODBC, estos controladores deben configurarse en el equipo en el que se ejecuta el servidor de Data Workbench con herramientas externas a la plataforma de Adobe. Los equipos de Data Workbench no requieren ninguna configuración adicional.
* La tabla o vista desde la que se cargan los datos debe tener una columna de ID creciente. Para cualquier fila, el valor de esta columna (que puede ser una columna real de la tabla o cualquier expresión de columna SQL) no debe disminuir a medida que se inserten nuevas filas en la base de datos. Si se infringe esta restricción, se pierden datos. Para un rendimiento adecuado, se requiere un índice en esta columna o expresión de columna.

   >[!NOTE]
   >
   >Es posible que varias filas tengan el mismo valor en la columna [!DNL Increasing ID]. Una posibilidad es una columna de marca de tiempo con una precisión inferior a la perfecta.

* El servidor de Data Workbench no puede cargar columnas con datos largos (datos superiores a una longitud determinada según la aplicación de base de datos específica en uso).
* La recuperación de datos de una base de datos es más lenta que la lectura desde un archivo de disco. Los conjuntos de datos que cargan datos desde un origen ODBC tardan mucho más en procesarse (especialmente cuando se reprocesan) que los conjuntos de datos de tamaño equivalente cuyos datos proceden de sensores u otros archivos de disco.

Para obtener información sobre el reprocesamiento de los datos, consulte [Reprocesamiento y retransformación](../../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md).

**Para configurar Insight Server para ODBC[!DNL event data]**

La configuración del servidor de Data Workbench para cargar datos desde una base de datos SQL requiere que realice primero los pasos siguientes en orden:

1. Instale el software cliente de base de datos adecuado, incluido un controlador ODBC, en el equipo de servidor de Data Workbench en el que se procesa el conjunto de datos.

   >[!NOTE]
   >
   >Si está cargando datos de evento ODBC para su procesamiento en un clúster de servidores de Data Workbench, debe instalar el software cliente de base de datos en todos los servidores de procesamiento del clúster. Para obtener información sobre cómo especificar servidores de procesamiento en un clúster, consulte la *Guía de instalación y administración de productos de servidor*.

1. Configure una fuente de datos mediante el Administrador de fuentes de datos ODBC para Windows.

   Es importante tener en cuenta que el servidor de Data Workbench (InsightServer64.exe) se ejecuta como un servicio de Windows. Por lo tanto, la fuente de datos debe configurarse normalmente como DSN del sistema en lugar de como DSN del usuario para que el servidor de Data Workbench pueda utilizarla. Puede encontrar más información sobre este paso de configuración en la documentación del software de la base de datos.

Después de instalar el software cliente de la base de datos en el equipo de servidor adecuado del Data Workbench, puede configurar el conjunto de datos para que utilice el origen de datos ODBC editando los parámetros adecuados en el archivo de configuración [!DNL Log Processing] del perfil deseado.

## Parámetros {#section-15c0218d93364693a565f2609a12f73e}

Para los datos de las bases de datos que utilizan el estándar ODBC (Open Database Connectivity, Conectividad abierta de bases de datos), están disponibles los siguientes parámetros:

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
   <td colname="col2"> DSN, proporcionado por un administrador del equipo de servidor de Data Workbench en el que se procesa el conjunto de datos, que hace referencia a la base de datos desde la que se van a cargar los datos. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Contraseña de base de datos </td> 
   <td colname="col2"> La contraseña que se utilizará al conectarse a la base de datos. Si se ha configurado una contraseña para el DSN en el <span class="wintitle"> Administrador de fuentes de datos</span>, esto puede dejarse en blanco. Cualquier contraseña proporcionada aquí anula la contraseña configurada para el DSN en el <span class="wintitle"> Administrador de fuentes de datos</span>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ID de usuario de base de datos </td> 
   <td colname="col2"> ID de usuario que se utilizará al conectarse a la base de datos. Si se ha configurado un ID de usuario para el DSN en el <span class="wintitle"> Administrador de fuentes de datos</span>, esto puede dejarse en blanco. Cualquier ID de usuario proporcionado aquí anula el ID de usuario configurado para el DSN en el <span class="wintitle"> Administrador de fuentes de datos</span>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Campos </td> 
   <td colname="col2"> Un vector de objetos de columna que especifica una asignación de columnas de datos de la base de datos a campos de datos del motor de ejecución del servidor de Data Workbench. Cada columna tiene entradas <span class="wintitle"> Nombre de columna</span> y <span class="wintitle"> Nombre de campo</span>. <span class="wintitle"> El </span> nombre de columna es una expresión de columna SQL que debe ser válida en el contexto de la tabla identificada por el identificador de  <span class="wintitle"> tabla </span> descrito anteriormente. Puede ser un nombre de columna o cualquier expresión SQL basado en cualquier número de columnas de la tabla. Puede ser necesaria una función de formato para convertir valores de ciertos tipos de datos en cadenas de forma que no se pierda la precisión. Todos los datos se convierten implícitamente en cadenas utilizando el método de formato predeterminado de la base de datos, que puede causar la pérdida de datos en algunos tipos de datos de columna (como los tipos de datos de fecha y hora) si no se utilizan expresiones de formato explícitas. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Aumento de la columna de ID </td> 
   <td colname="col2"> <p>Un nombre de columna o una expresión de columna SQL que cumple el criterio de que aumenta (o al menos no disminuye) a medida que se agregan nuevas filas. Es decir, si la Fila B se agrega a la tabla en un momento posterior al de la Fila A, el valor de esta columna (o expresión de columna) en la Fila B debe ser bueno (según el orden de clasificación nativo de la base de datos) que el valor correspondiente en la Fila A. </p> <p> 
     <ul id="ul_EBF6AEE4746B41B3B5BB6CC74194DAED"> 
      <li id="li_A5C9BE52B01649DE9726ECEC68B99828"> El nombre de la columna <span class="wintitle"> ID creciente </span>puede ser el mismo que el nombre de una columna existente, pero no es necesario. </li> 
      <li id="li_CF69EAB4AFB14F4894F7A5CDCAF06947"> Se supone que esta expresión tiene un tipo de datos de carácter SQL. Si la columna ID de aumento real es de algún otro tipo de datos, este valor debe ser una expresión de columna para convertirla en una cadena. Como esto generalmente significa que las comparaciones son lexicográficas (carácter por carácter), es importante dar un formato al valor cuidadosamente. </li> 
      <li id="li_58977431962E48039C898CFC47C53323"> La expresión se utiliza en las cláusulas SQL ORDER BY y se compara con las cláusulas SQL WHERE. Es de vital importancia tener un índice basado en la expresión de columna exacta que se utiliza. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ID de origen de registro </td> 
   <td colname="col2"> <p>El valor de este parámetro puede ser cualquier cadena. Si se especifica un valor, este parámetro le permite diferenciar las entradas de registro de diferentes fuentes de registro para la identificación de la fuente o el procesamiento dirigido. El campo x-log-source-id se rellena con un valor que identifica el origen del registro para cada entrada de registro. Por ejemplo, si desea identificar entradas de registro de un origen ODBC llamado ODBCSource01, puede escribir <span class="filepath"> desde ODBCSource01.</span> y esa cadena se pasaría al campo x-log-source-id para cada entrada de registro de ese origen. </p> <p> Para obtener información sobre el campo x-log-source-id, consulte <a href="../../../home/c-dataset-const-proc/c-ev-data-rec-fields.md#concept-06bda4be1a4649a2905a4422e9e6c42f"> Campos de registro de datos de evento</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Ejecutar en el servidor </td> 
   <td colname="col2"> Valor de índice en el archivo <span class="filepath"> profile.cfg</span> del servidor de procesamiento que realiza las consultas ODBC para obtener datos de la base de datos. (El parámetro Servidores de procesamiento del archivo <span class="filepath"> profile.cfg</span> enumera todos los servidores de procesamiento del conjunto de datos y cada servidor tiene un valor de índice, siendo el primero 0). El valor predeterminado es 0. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Identificador de tabla </td> 
   <td colname="col2"> Expresión SQL que nombra la tabla o vista desde la que se van a cargar los datos. Un identificador de tabla típico es del formulario SCHEMA.TABLE. </td> 
  </tr> 
 </tbody> 
</table>

Este ejemplo muestra la ventana de configuración [!DNL Log Processing] en Data Workbench con un origen de datos ODBC. Esta fuente de datos toma los datos de una tabla llamada [!DNL VISUAL.VSL] en una base de datos con [!DNL Data Source Name] &quot;VSTestO&quot;. Cinco (5) objetos de columna ( [!DNL Fields]) asignan datos de las columnas de datos de la base de datos al servidor de Data Workbench.

![](assets/cfg_LogProcessing_LogSources_ODBC.png)
