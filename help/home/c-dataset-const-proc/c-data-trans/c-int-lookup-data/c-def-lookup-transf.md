---
description: Información sobre las transformaciones que puede utilizar para incorporar datos de búsqueda en el conjunto de datos.
title: Definición de transformaciones de búsqueda
uuid: 4f7358b1-9e6a-4d03-b0c6-411e454fc11e
exl-id: 7b1504be-8669-4340-8400-e33f9663b602
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '2288'
ht-degree: 2%

---

# Definición de transformaciones de búsqueda{#defining-lookup-transformations}

{{eol}}

Información sobre las transformaciones que puede utilizar para incorporar datos de búsqueda en el conjunto de datos.

Tenga en cuenta que no todos los tipos se pueden usar durante ambas fases del proceso de construcción del conjunto de datos.

* [Categorizar](../../../../home/c-dataset-const-proc/c-data-trans/c-int-lookup-data/c-def-lookup-transf.md#section-8474376c14e54d14ae73749696ada468)
* [FlatFileLookup](../../../../home/c-dataset-const-proc/c-data-trans/c-int-lookup-data/c-def-lookup-transf.md#section-e09b2eeb96444a859b14f03cdaab31f2)
* [ODBCLookup](../../../../home/c-dataset-const-proc/c-data-trans/c-int-lookup-data/c-def-lookup-transf.md#section-4dcc3747e42e45c0a057e85f308a83cc)

## Categorizar {#section-8474376c14e54d14ae73749696ada468}

La variable [!DNL Categorize] la transformación utiliza una tabla de búsqueda de dos columnas compuesta por pares de patrón-cadena/valor. Durante esta transformación, el servidor de Data Workbench lee cada registro de datos de evento a su vez y compara el contenido de un campo designado del registro con cada una de las cadenas de patrón enumeradas en la primera columna de la tabla de búsqueda. Si el campo designado coincide con una de las cadenas de patrón, el servidor de Data Workbench escribe el valor (que se encuentra en la segunda columna) asociado a esa cadena de patrón en un campo de salida designado en el registro.

Las cadenas de la primera columna de la tabla de búsqueda pueden empezar con el carácter ^ o terminar en el carácter $ para forzar la coincidencia al principio y/o al final. Esta transformación no acepta expresiones regulares para definir condiciones de coincidencia en la primera columna. Si el valor de entrada es un vector de cadenas, cada cadena se ejecuta a través de la transformación y los resultados se añaden a un vector de cadena de salida.

A [!DNL Categorize] la transformación suele ser más fácil y rápida que el uso de un [!DNL Regular Expression] transformación para lograr lo mismo.

>[!NOTE]
>
>La prueba de subcadena utilizada en [!DNL Categorize] distingue entre mayúsculas y minúsculas a menos que se especifique lo contrario utilizando la variable [!DNL Case Sensitive] parámetro.

<table id="table_1773344FAAE34BD4919CC4414249FDEE"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parámetro </th> 
   <th colname="col2" class="entry"> Descripción </th> 
   <th colname="col3" class="entry"> Predeterminado </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Nombre </td> 
   <td colname="col2"> Nombre descriptivo de la transformación. Puede introducir cualquier nombre aquí. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Distinción entre mayúsculas y minúsculas </td> 
   <td colname="col2"> Verdadero o falso. Especifica si la prueba de subcadena distingue entre mayúsculas y minúsculas. </td> 
   <td colname="col3"> true </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Comentarios </td> 
   <td colname="col2"> Opcional. Notas sobre la transformación. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Condición </td> 
   <td colname="col2"> Condiciones en las que se aplica esta transformación. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Predeterminado </td> 
   <td colname="col2"> El valor predeterminado que se debe utilizar si la prueba de condición pasa y ninguna entrada en el archivo de categorización coincide con la entrada, o si el campo de entrada no está definido en la entrada de registro dada. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Delimitador </td> 
   <td colname="col2"> <p>Cadena que se utiliza para separar las columnas del archivo de búsqueda. Debe tener un solo carácter de longitud. </p> <p> Si mantiene pulsada la tecla Ctrl y hace clic con el botón derecho en el parámetro Delimitador, se muestra una <span class="wintitle"> Insertar</span> aparece. Este menú contiene una lista de caracteres especiales que a menudo se utilizan como delimitadores. </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Valores múltiples </td> 
   <td colname="col2"> Verdadero o falso. Si el valor es true, cuando varias filas del archivo coinciden con la entrada, cada una de ellas tiene como resultado que se añada un valor al vector de salida de cadenas. Si es false, solo se utiliza en la salida la primera fila que coincida en el archivo. En este último caso, si la entrada es un vector, la salida es también un vector de longitud equivalente. Si la entrada es una cadena simple, el resultado también es una cadena simple. </td> 
   <td colname="col3"> false </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Archivo </td> 
   <td colname="col2"> Ruta y nombre de archivo del archivo de categorización. Las rutas relativas son con respecto al directorio de instalación del servidor de Data Workbench. Este archivo se encuentra generalmente en el directorio de búsquedas dentro del directorio de instalación del servidor de Data Workbench. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Entrada </td> 
   <td colname="col2"> El archivo de categorización coincide con sus subcadenas con el valor de este campo para identificar la fila coincidente del archivo. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Output </td> 
   <td colname="col2"> Nombre del campo asociado al resultado. </td> 
   <td colname="col3"> </td> 
  </tr> 
 </tbody> 
</table>

**Consideraciones para la categorización**

* Cambios en los archivos de búsqueda en [!DNL Categorize] transformaciones definidas en la variable [!DNL Transformation.cfg] o en un [!DNL Transformation Dataset Include] requiere la retransformación del conjunto de datos. Buscar archivos [!DNL Categorize] transformaciones definidas en la variable [!DNL Log Processing.cfg] archivo o [!DNL Log Processing Dataset Include] no están sujetos a esta limitación. Para obtener información sobre cómo reprocesar los datos, consulte [Reprocesamiento y retransformación](../../../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md).

* [!DNL Categorize] transformaciones definidas en la variable [!DNL Log Processing.cfg] archivo o [!DNL Log Processing Dataset Include] vuelva a cargar los archivos de búsqueda cada vez que cambien los archivos de búsqueda. Los cambios no se aplican de forma retroactiva, pero se aplican a todos los datos de registro leídos después de que se produzca el cambio.

Este ejemplo ilustra el uso de la variable [!DNL Categorize] transformación para integrar los datos de búsqueda con los datos de evento recopilados del tráfico del sitio web. Supongamos que un sitio web en particular tiene secciones comerciales y que existe el requisito de poder ver y realizar comparaciones en función del flujo de tráfico y el valor generados por las diferentes secciones. Puede crear un archivo de búsqueda que enumere las subcadenas utilizadas para identificar estas diferentes secciones.

El archivo de búsqueda [!DNL Lookups\custommap.txt] contiene la siguiente tabla:

| /productos/ | Productos |
|---|---|
| ^/deportes/ | Deportes |
| ^/noticias/ | Noticias |
| ... | ... |

Este archivo de categorización asigna todo lo que contenga la cadena &quot;/products/&quot; al valor &quot;Products&quot;, cualquier cosa que empiece por &quot;/sport/&quot; al valor &quot;Sports&quot; y cualquier cosa que empiece por &quot;/news/&quot; al valor &quot;News&quot;. La siguiente transformación de categorización utiliza el valor del campo cs-uri-stem como la cadena en la que se busca una subcadena coincidente. El resultado de la transformación se coloca en el campo x-custommap .

![](assets/cfg_TransformationType_Categorize.png)

Suponiendo que el parámetro Multiple Values esté establecido en false, el ejemplo produciría los siguientes valores para x-custommap dados los valores listados para cs-uri-stem.

| [!DNL cs-uri-stem] | [!DNL x-custommap] |
|---|---|
| [!DNL /sports/news/today.php] | Deportes |
| [!DNL /sports/products/buy.php] | Productos |
| [!DNL /news/headlines.php] | Noticias |
| [!DNL /news/products/subscribe.php] | Productos |

El resultado se basa en el orden de las subcadenas del archivo de búsqueda. Por ejemplo, la función cs-uri-stem [!DNL /sports/products/buy.php] devuelve &quot;Productos&quot;. Aunque el sistema de URI empieza por &quot;/sport/&quot;, la cadena &quot;/products/&quot; aparece antes de &quot;/sport/&quot; en el archivo de búsqueda. Si el parámetro Multiple Values se estableciera en true, habría un valor adicional para x-custommap, ya que el último ejemplo coincidiría con dos filas en la tabla de consulta: Productos y Noticias.

## FlatFileLookup {#section-e09b2eeb96444a859b14f03cdaab31f2}

La variable [!DNL FlatFileLookup] la transformación utiliza una tabla de búsqueda compuesta por cualquier número de columnas y filas (aunque recuerde que reside en la memoria). Durante este tipo de transformación, el servidor de Data Workbench lee cada registro de datos de evento a su vez y compara el contenido de un campo designado del registro con cada uno de los valores de una columna designada de la tabla de búsqueda. Si hay una coincidencia, el servidor de Data Workbench escribe uno o más valores de la fila correspondiente de la tabla de búsqueda en uno o más campos de salida designados en el registro de datos de evento.

La tabla de búsqueda utilizada durante esta transformación se rellena desde un archivo plano cuya ubicación especifique al definir la transformación.

<table id="table_772B8ABF3B44493F99069010DDB5F77A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parámetro </th> 
   <th colname="col2" class="entry"> Descripción </th> 
   <th colname="col3" class="entry"> Predeterminado </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Nombre </td> 
   <td colname="col2"> Nombre descriptivo de la transformación. Puede introducir cualquier nombre aquí. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Comentarios </td> 
   <td colname="col2"> Opcional. Notas sobre la transformación. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Condición </td> 
   <td colname="col2"> Condiciones en las que se aplica esta transformación. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Predeterminado </td> 
   <td colname="col2"> El valor predeterminado que se debe utilizar si se cumple la condición y si ninguna entrada del archivo de búsqueda coincide con la entrada. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Delimitador </td> 
   <td colname="col2"> <p>Cadena que se utiliza para separar las columnas del archivo de búsqueda. Debe tener un solo carácter de longitud. </p> <p> Si mantiene pulsada la tecla Ctrl y hace clic con el botón derecho en el parámetro Delimitador, se muestra una <span class="wintitle"> Insertar</span> aparece. Este menú contiene una lista de caracteres especiales que a menudo se utilizan como delimitadores. </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Archivo </td> 
   <td colname="col2"> Ruta y nombre de archivo del archivo de búsqueda. Las rutas relativas son con respecto al directorio de instalación del servidor de Data Workbench. Este archivo se encuentra generalmente en el directorio de búsquedas dentro del directorio de instalación del servidor de Data Workbench. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Fila de encabezado </td> 
   <td colname="col2"> Verdadero o falso. Indica que la primera fila de la tabla es una fila de encabezado que se va a ignorar en el procesamiento. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Entrada </td> 
   <td colname="col2"> <span class="wintitle"> Nombre de columna</span> es el nombre de la columna que se usa para hacer coincidir la entrada con las filas del archivo. Si Fila de encabezado es verdadera, puede ser el nombre de una columna del archivo de búsqueda. De lo contrario, debe ser el número de columna de base cero con el que se debe hacer coincidir. <span class="wintitle"> Nombre del campo</span> es el nombre del campo utilizado para localizar la fila en el archivo de búsqueda. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Valores múltiples </td> 
   <td colname="col2"> <p>Verdadero o falso. Determina si se debe devolver un valor único (una fila que coincida) o varios valores (uno por cada fila que coincida). </p> <p> <p>Nota: If <span class="wintitle"> Valores múltiples</span> se establece en false, debe asegurarse de que no haya varias coincidencias. Cuando se producen varias coincidencias, no hay garantía de que se devuelva una coincidencia. </p> </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Salidas </td> 
   <td colname="col2"> <p>Un vector de objetos de columna (resultados) en el que cada objeto está definido por los nombres de columna y campo. </p> <p> <span class="wintitle"> Nombre de columna</span> es la columna de la que se obtiene el valor de salida. If <span class="wintitle"> Fila de encabezado</span> tiene el valor true, puede ser el nombre de una columna del archivo de búsqueda. De lo contrario, debe ser el número de columna de base cero con el que se debe hacer coincidir. </p> <p> <span class="wintitle"> Nombre del campo</span> es el nombre del campo utilizado para capturar el resultado. Tenga en cuenta que esto puede ser un vector de resultados, uno para cada fila identificada en caso de que el parámetro Multiple Values sea verdadero. </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
 </tbody> 
</table>

**Consideraciones para[!DNL FlatFileLookup]**

* La coincidencia del campo de entrada con el archivo de búsqueda siempre distingue entre mayúsculas y minúsculas.
* Cambios en los archivos de búsqueda en [!DNL FlatFileLookup] transformaciones definidas en la variable [!DNL Transformation.cfg] archivo o [!DNL Transformation Dataset Include] los archivos requieren la retransformación del conjunto de datos. Buscar archivos [!DNL FlatFileLookup] transformaciones definidas en la variable [!DNL Log Processing.cfg] archivo o [!DNL Log Processing Dataset Include] los archivos no están sujetos a esta limitación. Para obtener información sobre cómo reprocesar los datos, consulte [Reprocesamiento y retransformación](../../../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md).

* [!DNL FlatFileLookup] transformaciones en la variable [!DNL Log Processing.cfg] archivo o [!DNL Log Processing Dataset Include] los archivos de búsqueda vuelven a cargar los archivos de búsqueda cada vez que cambian los archivos de búsqueda. Los cambios no se aplican de forma retroactiva, pero se aplican a todos los datos de registro leídos después de que se produzca el cambio.

Este ejemplo ilustra el uso de la variable [!DNL FlatFileLookup] transformación para integrar los datos de búsqueda con los datos de evento recopilados del tráfico del sitio web. Supongamos que desea aislar a los socios de sitios web que dirigen el tráfico al sitio web y transformar sus ID de socio en nombres más descriptivos. A continuación, puede utilizar nombres descriptivos para crear dimensiones y visualizaciones extendidas que se asemejen más claramente a la relación comercial que a la relación sitio a sitio utilizada para el tráfico de enrutamiento.

La transformación de ejemplo busca en el campo cs(referrer-query) el par nombre-valor de PartnerID y, si se encuentra, el archivo de búsqueda [!DNL Lookups\partners.txt] se usa para comparar el valor de PartnerID con los valores de la variable [!DNL Partner] de la tabla. Si se encuentra una fila, el campo de salida x-partner-name recibe el nombre del [!DNL PrintName] de la fila identificada.

![](assets/cfg_TransformationType_FlatFileLookup.png)

Si la tabla de búsqueda contiene la siguiente información:

| ID | Socio | Inicio | PrintName |
|---|---|---|---|
| 1 | P154 | 21 de agosto de 1999 | Yahoo |
| 2 | P232 | 10 de julio de 2000 | Microsoft |
| 3 | P945 | 12 de enero de 2001 | Amazon |

Los siguientes ejemplos se transformarían de la siguiente manera:

* Si cs(referrer)(PartnerID) devuelve P232, el campo x-partner-name tendría el valor &quot;Microsoft&quot;.
* Si cs(referrer)(PartnerID) devuelve P100, el campo x-partner-name tendría el valor &quot;No Partner&quot;.
* Si cs(referrer)(PartnerID) no devuelve nada, el campo x-partner-name tendría el valor &quot;No Partner&quot; especificado por el parámetro Default .

## ODBCLookup {#section-4dcc3747e42e45c0a057e85f308a83cc}

La variable [!DNL ODBCLookup] la transformación funciona como una [!DNL FlatFileLookup] transformación. La única diferencia es que la tabla de búsqueda utilizada durante esta transformación se rellena desde una base de datos ODBC y no desde un archivo plano.

>[!NOTE]
>
>[!DNL ODBCLookup] las transformaciones solo se pueden ejecutar durante la fase de transformación del proceso de construcción del conjunto de datos. Cuando sea posible, Adobe recomienda usar la variable [!DNL FlatFileLookup] transformación en lugar de [!DNL ODBCLookup] transformación. [!DNL FlatFileLookup] las transformaciones son inherentemente más fiables porque no dependen de la disponibilidad de un sistema externo. Además, hay menos riesgo de que la tabla de búsqueda se modifique si reside en un archivo plano que controla localmente.

<table id="table_B903DB291BCC4F44B09D54300216D288"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parámetro </th> 
   <th colname="col2" class="entry"> Descripción </th> 
   <th colname="col3" class="entry"> Predeterminado </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Nombre </td> 
   <td colname="col2"> Nombre descriptivo de la transformación. Puede introducir cualquier nombre aquí. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Comentarios </td> 
   <td colname="col2"> Opcional. Notas sobre la transformación. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Condición </td> 
   <td colname="col2"> Condiciones en las que se aplica esta transformación. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Nombre de la fuente de datos </td> 
   <td colname="col2"> DSN, proporcionado por un administrador del equipo de servidor de Data Workbench en el que se procesa el conjunto de datos, que hace referencia a la base de datos desde la que se van a cargar los datos. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Contraseña de base de datos </td> 
   <td colname="col2">La contraseña que se utilizará al conectarse a la base de datos. Si se ha configurado una contraseña para el DSN en la variable <span class="wintitle"> Administrador de fuentes de datos</span>, esto puede dejarse en blanco. Cualquier contraseña proporcionada aquí anula la contraseña configurada para el DSN en la variable <span class="wintitle"> Administrador de fuentes de datos</span>. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ID de usuario de base de datos </td> 
   <td colname="col2">ID de usuario que se utilizará al conectarse a la base de datos. Si se ha configurado un ID de usuario para el DSN en la variable <span class="wintitle"> Administrador de fuentes de datos</span>, esto puede dejarse en blanco. Cualquier ID de usuario proporcionado aquí anula el ID de usuario configurado para el DSN en la variable <span class="wintitle"> Administrador de fuentes de datos</span>. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Predeterminado </td> 
   <td colname="col2"> El valor predeterminado que se debe utilizar si se cumple la condición y ninguna entrada del archivo de búsqueda coincide con la entrada. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Columna de entrada </td> 
   <td colname="col2"> <span class="wintitle"> Nombre de columna</span> es el nombre de columna o la expresión SQL para los datos que coinciden con los datos de entrada. <span class="wintitle"> Nombre del campo</span> es el nombre del campo que contiene los datos que se van a buscar. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Valores múltiples </td> 
   <td colname="col2"> <p>Verdadero o falso. Determina si se debe devolver un valor único (una fila que coincida) o varios valores (uno por cada fila que coincida). </p> <p> <p>Nota: If <span class="wintitle"> Valores múltiples</span> se establece en false, debe asegurarse de que no haya varias coincidencias. Cuando se producen varias coincidencias, no hay garantía de que se devuelva una coincidencia. </p> </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Columnas de salida </td> 
   <td colname="col2"> <p>Un vector de objetos de columna (resultados) donde cada objeto se define mediante nombres de columna y campo. </p> <p> <span class="wintitle"> Nombre de columna</span> es el nombre de la expresión SQL o de la columna desde la que se obtiene el valor de salida. <span class="wintitle"> Nombre del campo</span> es el nombre del campo utilizado para capturar el resultado. </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Identificador de tabla</span> </td> 
   <td colname="col2"> Expresión SQL que nombra la tabla o vista desde la que se van a cargar los datos. Un identificador de tabla típico es del formulario SCHEMA.TABLE. </td> 
   <td colname="col3"> </td> 
  </tr> 
 </tbody> 
</table>

* El Nombre De La Fuente De Datos, [!DNL Database User ID], [!DNL Database Password], y los parámetros del identificador de tabla son los mismos que los parámetros de los mismos nombres que se describen para los orígenes de datos ODBC. Consulte [Fuentes de datos ODBC](../../../../home/c-dataset-const-proc/c-log-proc-config-file/c-odbc-data-sources.md#concept-5f2cf635081d44beab826ef5ec8cf4e3).

* A diferencia de los orígenes de datos ODBC, [!DNL ODBCLookup] las transformaciones no requieren un aumento de la columna de ID. Consulte [Fuentes de datos ODBC](../../../../home/c-dataset-const-proc/c-log-proc-config-file/c-odbc-data-sources.md#concept-5f2cf635081d44beab826ef5ec8cf4e3). Esto se debe a que el contenido de la tabla de consulta no debe cambiar de ninguna manera mientras el conjunto de datos esté activo. Los cambios en una tabla o vista de búsqueda no se pueden detectar hasta que se produzca la retransformación. Para obtener información sobre cómo reprocesar los datos, consulte [Reprocesamiento y retransformación](../../../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md).

Supongamos que desea convertir registros DNS obsoletos a los registros actualizados. Ambos conjuntos de registros se almacenan en una base de datos SQL. Para realizar esta tarea, haría referencia a una tabla de búsqueda que se genera a partir de la base de datos y reemplazaría los registros DNS obsoletos.

Nuestra transformación de ejemplo busca en las entradas de registro el campo s-dns y, si se encuentra, se utiliza la tabla de búsqueda VISUAL.LOOKUP para comparar la entrada s-dns con las entradas del [!DNL OLDDNS] de la tabla. Si una fila está ubicada en la tabla, el campo de salida s-dns recibe la entrada de registro DNS actualizada desde el [!DNL NEWDNS] de la fila identificada.

![](assets/cfg_TransformationType_ODBCLookup.png)
