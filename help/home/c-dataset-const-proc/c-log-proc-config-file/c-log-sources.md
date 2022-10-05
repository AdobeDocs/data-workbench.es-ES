---
description: Los orígenes de registro son archivos que contienen los datos que se utilizarán para crear un conjunto de datos.
title: Fuentes de registro
uuid: ea21c3d7-9188-4ba8-bacd-052d678bd799
exl-id: 36e0799b-197d-4c59-84ae-7a4350584ab1
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '3664'
ht-degree: 1%

---

# Fuentes de registro{#log-sources}

{{eol}}

Los orígenes de registro son archivos que contienen los datos que se utilizarán para crear un conjunto de datos.

Los datos disponibles en las fuentes de registro se denominan datos de evento porque cada registro de datos representa un registro de transacción o una instancia única de un evento. El servidor de Data Workbench puede procesar fuentes de registro derivadas de datos recopilados por [!DNL Sensors] o extraído de otras fuentes de datos.

* **Datos recopilados por [!DNL Sensors]: ** Datos recopilados por [!DNL Sensors] desde HTTP y los servidores de aplicaciones se transmiten a los servidores de Data Workbench, que convierten los datos en registros muy comprimidos ( [!DNL .vsl]). Consulte [Archivos de sensor](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md#concept-b25f11c477b54032a15b6117b3bf9009).

* **Datos extraídos por el servidor de Insight:** El servidor de Data Workbench lee datos de evento contenidos en archivos planos, archivos XML o bases de datos compatibles con ODBC y utiliza sus descodificadores para extraer los elementos deseados de los datos. Estos datos de evento no tienen que residir en la memoria, pero los registros que contienen los datos deben incluir un ID de seguimiento. Consulte [Archivos de registro](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md#concept-3d4fb817c057447d90f166b1183b461e), [Fuentes de registro XML](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md#concept-c7b154e93748447b986e97f6ef688887)y [Fuentes de datos ODBC](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-odbc-data-sources.md#concept-5f2cf635081d44beab826ef5ec8cf4e3).

**Para agregar un origen de registro**

1. Apertura [!DNL Log Processing.cfg] en data workbench.
1. Clic con el botón derecho **[!UICONTROL Log Sources]** y haga clic en **[!UICONTROL Add New]**.

1. Seleccione una de las siguientes opciones:

   * **[!UICONTROL Sensor]**
   * **[!UICONTROL Log File]**
   * **[!UICONTROL XML Log Source]**
   * **[!UICONTROL ODBC Data Source]**

1. Los parámetros específicos utilizados para definir un conjunto de datos varían según el tipo de fuente de registro que se utilizará en el proceso de configuración del conjunto de datos. Especifique los parámetros tal como se indica en la sección correspondiente al origen de registro correspondiente:

   * [Archivos de sensor](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md#concept-b25f11c477b54032a15b6117b3bf9009)
   * [Archivos de registro](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md#concept-3d4fb817c057447d90f166b1183b461e)
   * [Fuentes de registro XML](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md#concept-c7b154e93748447b986e97f6ef688887)
   * [Fuentes de datos ODBC](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-odbc-data-sources.md#concept-5f2cf635081d44beab826ef5ec8cf4e3)

1. Una vez definido el origen de registro (y haya realizado cambios en otros parámetros) en la variable [!DNL Log Processing.cfg] guarde el archivo localmente y guárdelo en su perfil de conjunto de datos en el servidor de Data Workbench.

   >[!NOTE]
   >
   >Un servidor de Data Workbench [!DNL File Server Unit] puede recibir y almacenar [!DNL Sensor] archivos, archivos de registro y archivos XML, y servirlos en el servidor de Data Workbench [!DNL Data Processing Units] que construyen el conjunto de datos. Consulte [Configuración de una unidad de servidor de archivos de Insight Server](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-ins-svr-file-svr-unit.md#concept-995abff3fce34e439fb3f7f47191c80d).

   Puede abrir la configuración de cualquier fuente de registro desde un [!DNL Transformation Dependency Map]. Para obtener información sobre [!DNL Transformation Dependency Map], consulte [Herramientas de configuración de conjuntos de datos](../../../home/c-dataset-const-proc/c-dataset-config-tools/c-dataset-config-tools.md#concept-6e058b7691834cf79dcfd1573f78d4f5).

<!--
c_sensor_files.xml
-->

## Requisitos {#section-d5901a4872774ad5bd01a18db114f1f2}

Datos de eventos recopilados por [!DNL Sensors] desde HTTP y los servidores de aplicaciones se transmiten a los servidores de Data Workbench, que convierten los datos en registros muy comprimidos ( [!DNL .vsl]). La variable [!DNL .vsl] el formato de archivo lo gestiona el servidor de Data Workbench y cada archivo tiene un nombre con el formato :

AAAAMMDD-*SENSORID*.VSL

donde AAAAMMDD es la fecha del archivo, y *SENSORID* es el nombre (asignado por su organización) que indica qué [!DNL Sensor] recopiló y transmitió los datos al servidor de Data Workbench.

## Parámetros {#section-5c3f1e341c284486aeba3452057da7f3}

Para [!DNL Sensor] , están disponibles los siguientes parámetros:

<table id="table_F583B475600041AFA3B9399AE0592146"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parámetro </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Rutas de registro </td> 
   <td colname="col2"> <p>Los directorios donde la variable <span class="filepath"> .vsl</span> se almacenan. La ubicación predeterminada es el directorio Logs . Una ruta relativa hace referencia al directorio de instalación del servidor de Data Workbench. </p> <p>Puede utilizar caracteres comodín para especificar qué <span class="filepath"> .vsl</span> archivos para procesar: 
     <ul id="ul_AE144ED0FAB94FE8B32599A058659DE1"> 
      <li id="li_1E4E4CFD72C34B5EB71A3C59877950A9"> * coincide con cualquier número de caracteres </li> 
      <li id="li_4664400FC12E44B39B28438B85D20ED8"> ? hace coincidir un solo carácter </li> 
     </ul> </p> <p> Por ejemplo, la ruta de registro <span class="filepath"> Registros\*.vsl</span> coincide con cualquier archivo del directorio Logs que termina en <span class="filepath"> .vsl</span>. La ruta de registro <span class="filepath"> Logs\*-SENSOR?.vsl</span> hace coincidir archivos del directorio Logs con cualquier fecha (AAAAMMDD) y un solo carácter después de SENSOR, como en SENSOR1. </p> <p> Si desea buscar en todos los subdirectorios de la ruta especificada, debe establecer el parámetro Recursive en true. </p> <p> <p>Nota: Si los archivos se van a leer desde el servidor de Data Workbench <span class="wintitle"> Unidad de servidor de archivos</span>, debe introducir los URI correspondientes en el parámetro de rutas de registro . Por ejemplo, la variable <span class="filepath"> URI /Logs/*-*.vsl</span> coincide con any <span class="filepath"> .vsl</span> en el directorio Logs. Consulte <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-ins-svr-file-svr-unit.md#concept-995abff3fce34e439fb3f7f47191c80d"> Configuración de una unidad de servidor de archivos de Insight Server</a>. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Servidor de registro </td> 
   <td colname="col2">Información (dirección, nombre, puerto, etc.) necesaria para conectarse a un servidor de archivos. Si hay una entrada en el parámetro del servidor de registro, la variable <span class="wintitle"> Rutas de registro</span> se interpretan como URI. De lo contrario, se interpretan como rutas locales. Consulte <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-ins-svr-file-svr-unit.md#concept-995abff3fce34e439fb3f7f47191c80d"> Configuración de una unidad de servidor de archivos de Insight Server</a>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ID de origen de registro </td> 
   <td colname="col2"> <p>El valor de este parámetro puede ser cualquier cadena. Si se especifica un valor, este parámetro le permite diferenciar las entradas de registro de diferentes fuentes de registro para la identificación de la fuente o el procesamiento dirigido. El campo x-log-source-id se rellena con un valor que identifica el origen del registro para cada entrada de registro. Por ejemplo, si desea identificar entradas de registro de un <span class="wintitle"> Sensor</span> llamado VSensor01, puede escribir <span class="filepath"> de VSensor01</span>, y esa cadena se pasaría al campo x-log-source-id por cada entrada de registro de ese origen. </p> <p> Para obtener información sobre el campo x-log-source-id , consulte <a href="../../../home/c-dataset-const-proc/c-ev-data-rec-fields.md#concept-06bda4be1a4649a2905a4422e9e6c42f"> Campos de registro de datos de evento</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Recursivo </td> 
   <td colname="col2"> Verdadero o falso. Si se establece en true, todos los subdirectorios de cada ruta especificada en <span class="wintitle"> Rutas de registro</span> se buscan archivos que coincidan con el nombre de archivo o el patrón de comodín especificados. El valor predeterminado es false. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Usar horas de inicio/fin </td> 
   <td colname="col2"> <p>Verdadero o falso. Si se establece en true y se especifica la hora de inicio o la hora de finalización, todos los archivos de este origen de registro deben tener nombres de archivo que empiecen por fechas en formato ISO (AAAAMMDD). Se supone que cada archivo contiene datos de un día GMT (por ejemplo, el intervalo de tiempo que comienza a las 000 GMT de un día y termina a las 000 GMT del día siguiente). Si los archivos de fuentes de registro contienen datos que no corresponden a un día GMT, este parámetro debe establecerse en false para evitar resultados incorrectos. </p> <p> <p>Nota: De forma predeterminada, <span class="filepath"> .vsl </span>archivos que contienen datos recopilados por <span class="wintitle"> Sensor</span> cumpla automáticamente los requisitos de nomenclatura e intervalo de tiempo descritos anteriormente. Si establece este parámetro en true, el servidor de Data Workbench siempre procesa los datos de archivos cuyos nombres incluyen fechas ISO que se encuentran entre la hora de inicio y la hora de finalización especificadas. Si establece este parámetro en false, el servidor de Data Workbench lee todas las variables <span class="filepath"> .vsl</span> durante el procesamiento del registro para determinar qué archivos contienen datos dentro del intervalo de tiempo de inicio y de finalización. </p> </p> <p> Para obtener información sobre los parámetros Hora de inicio y Hora de finalización, consulte <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md#concept-41bd49bf6b64442d91c232ec67529a3d"> Filtros de datos</a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>No utilice los parámetros de configuración para [!DNL Sensor] fuentes de datos para determinar qué entradas de registro dentro de un archivo de registro deben incluirse en un conjunto de datos. En su lugar, configure el origen de datos para que apunte a todos los archivos de registro dentro de un directorio. A continuación, utilice los parámetros Hora de inicio y Hora de finalización de [!DNL Log Processing.cfg] para determinar qué entradas de registro deben utilizarse en la construcción del conjunto de datos. Consulte [Filtros de datos](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md#concept-41bd49bf6b64442d91c232ec67529a3d).

<!--
c_log_files.xml
-->

El archivo que contiene los datos de evento debe cumplir los siguientes requisitos:

* Cada registro de datos de evento del archivo debe estar representado por una línea.
* Los campos de un registro deben separarse, estén vacíos o no, con un delimitador ASCII. El servidor de Data Workbench no requiere que utilice un delimitador específico. Puede utilizar cualquier carácter que no sea un carácter de fin de línea y que no aparezca en ningún lugar dentro de los datos del evento en sí.
* Cada registro del archivo debe contener:

   * Un ID de seguimiento
   * Una marca de tiempo

* Para especificar las horas de inicio y finalización del procesamiento de datos, cada nombre de archivo debe ser del formulario:

   * [!DNL YYYYMMDD-SOURCE.log]

   donde *AAAAMMDD* es la hora media de Greenwich (GMT) del día de todos los datos del archivo, y *FUENTE* es una variable que identifica el origen de los datos contenidos en el archivo.

   >[!NOTE]
   >
   >Póngase en contacto con los servicios de consultoría de Adobe para obtener una revisión de los archivos de registro que planea incorporar al conjunto de datos.

## Parámetros {#section-83a861ac24954d54bbb9530e4d8bf23c}

Para los orígenes de registro de archivos de registro, están disponibles los parámetros de la siguiente tabla.

>[!NOTE]
>
>El procesamiento de las fuentes de registro de archivos de registro requiere parámetros adicionales que se definen en una [!DNL Log Processing Dataset Include] , que contiene un subconjunto de los parámetros incluidos en un [!DNL Log Processing.cfg] , así como parámetros especiales para definir descodificadores para extraer datos del archivo de registro. Para obtener información sobre la definición de descodificadores para las fuentes de registro de archivos de registro, consulte [Grupos de decodificadores de archivos de texto](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-log-proc-dataset-inc-files/c-text-file-dec-groups.md#concept-0db34988e17c41bfb1797f1d8e78aabd).

<table id="table_F33735B5B90A48B0B21FA02D9198CCA9"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parámetro </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Nombre </td> 
   <td colname="col2"> Identificador del origen del archivo de registro. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Rutas de registro </td> 
   <td colname="col2"> <p>Los directorios en los que se almacenan los archivos de registro. La ubicación predeterminada es el directorio Logs . Una ruta relativa hace referencia al directorio de instalación del servidor de Data Workbench. </p> <p> Puede utilizar caracteres comodín para especificar qué archivos de registro procesar: 
     <ul id="ul_1F02D26A08D846E2A3114E5C33F60ECF"> 
      <li id="li_ECAE1C03A1C448A1B86AE00B3A955708"> * coincide con cualquier número de caracteres. </li> 
      <li id="li_24FDB500C5934CAAA4124C435DF4B290"> ? hace coincidir un solo carácter. </li> 
     </ul> </p> <p> Por ejemplo, la ruta de registro <span class="filepath"> Registros\*.log</span> coincide con cualquier archivo del directorio Logs que termina en <span class="filepath"> .log</span>. </p> <p> Si desea buscar todos los subdirectorios de la ruta especificada, debe establecer el parámetro Recursive en true. </p> <p> Si los archivos se van a leer desde el servidor de Data Workbench <span class="wintitle"> Unidad de servidor de archivos</span>, debe introducir los URI correspondientes en el parámetro de rutas de registro . Por ejemplo, la variable <span class="filepath"> URI/Logs/*.log</span> coincide con any <span class="filepath"> .log</span> en el directorio Logs. Consulte <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-ins-svr-file-svr-unit.md#concept-995abff3fce34e439fb3f7f47191c80d"> Configuración de una unidad de servidor de archivos de Insight Server</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Servidor de registro </td> 
   <td colname="col2"> Información (dirección, nombre, puerto, etc.) necesaria para conectarse a un servidor de archivos. Si hay una entrada en el parámetro del servidor de registro, la variable <span class="wintitle"> Rutas de registro</span> se interpretan como URI. De lo contrario, se interpretan como rutas locales. Consulte <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-ins-svr-file-svr-unit.md#concept-995abff3fce34e439fb3f7f47191c80d"> Configuración de una unidad de servidor de archivos de Insight Server</a>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Comprimido </td> 
   <td colname="col2"> Verdadero o falso. Este valor debe establecerse en true si los archivos de registro que va a leer el servidor de Data Workbench son archivos gzip comprimidos. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Grupo del decodificador </td> 
   <td colname="col2"> Nombre del grupo de descodificadores de archivos de texto que se aplicará al origen de registro de archivos de registro. Este nombre debe coincidir exactamente con el nombre del grupo de descodificadores de archivos de texto correspondiente especificado en la variable <span class="wintitle"> Incluir conjunto de datos de procesamiento de registros</span> archivo. Consulte <a href="../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-log-proc-dataset-inc-files/c-text-file-dec-groups.md#concept-0db34988e17c41bfb1797f1d8e78aabd"> Grupos de decodificadores de archivos de texto</a>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ID de origen de registro </td> 
   <td colname="col2"> <p>El valor de este parámetro puede ser cualquier cadena. Si se especifica un valor, este parámetro le permite diferenciar las entradas de registro de diferentes fuentes de registro para la identificación de la fuente o el procesamiento dirigido. El campo x-log-source-id se rellena con un valor que identifica el origen del registro para cada entrada de registro. Por ejemplo, si desea identificar entradas de registro de un origen de archivos de registro denominado LogFile01, puede escribir <span class="filepath"> desde LogFile01</span>, y esa cadena se pasaría al campo x-log-source-id por cada entrada de registro de ese origen. </p> <p> Para obtener información sobre el campo x-log-source-id , consulte <a href="../../../home/c-dataset-const-proc/c-ev-data-rec-fields.md#concept-06bda4be1a4649a2905a4422e9e6c42f"> Campos de registro de datos de evento</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Patrón de máscara </td> 
   <td colname="col2"> <p>Expresión regular con un único subpatrón de captura que extrae un nombre coherente utilizado para identificar el origen de una serie de archivos de registro. Solo se tiene en cuenta el nombre del archivo. La ruta y la extensión no se consideran para la coincidencia de expresiones regulares. Si no especifica un <span class="wintitle"> patrón de máscara</span>, se genera automáticamente una máscara. </p> <p> Para los archivos <span class="filepath"> Registros\010105server1.log</span> y <span class="filepath"> Registros\010105server2.log</span>, el <span class="wintitle"> patrón de máscara</span> sería <code>[0-9]{6}(.*)</code>. Este patrón extrae la cadena "server1" o "server2" de los nombres de archivo anteriores. </p> <p> Consulte <a href="../../../home/c-dataset-const-proc/c-reg-exp.md#concept-070077baa419475094ef0469e92c5b9c"> Expresiones regulares</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Recursivo </td> 
   <td colname="col2"> Verdadero o falso. Si este parámetro se establece en true, todos los subdirectorios de cada ruta especificada en <span class="wintitle"> Rutas de registro</span> se buscan archivos que coincidan con el nombre de archivo o el patrón de comodín especificados. El valor predeterminado es false. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Rechazar archivo </td> 
   <td colname="col2"> Ruta y nombre de archivo del archivo que contiene las entradas de registro que no cumplen las condiciones del decodificador. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Usar horas de inicio/fin </td> 
   <td colname="col2"> <p>Verdadero o falso. Si este parámetro se establece en true y se especifica la hora de inicio o la hora de finalización, todos los archivos de este origen de registro deben tener nombres de archivo que empiecen por fechas en formato ISO (AAAAMMDD). Se supone que cada archivo contiene datos de un día GMT (por ejemplo, el intervalo de tiempo que comienza a las 000 GMT de un día y termina a las 000 GMT del día siguiente). Si los nombres de archivo de las fuentes de registro no comienzan con fechas ISO, o si los archivos contienen datos que no corresponden a un día GMT, este parámetro debe establecerse en false para evitar resultados incorrectos. </p> <p> <p>Nota: Si se cumplen los requisitos de nomenclatura y intervalo de tiempo descritos anteriormente para los archivos de registro y se establece este parámetro en true, el grupo de descodificadores de archivos de texto especificado limita los archivos leídos a aquellos cuyos nombres tengan fechas ISO que se encuentran entre la hora de inicio y la hora de finalización especificadas. Si establece este parámetro en false, el servidor de Data Workbench lee todos los archivos de registro durante el procesamiento del registro para determinar qué archivos contienen datos dentro del intervalo de tiempo de inicio y de finalización. </p> </p> <p> Para obtener información sobre los parámetros Hora de inicio y Hora de finalización, consulte <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md#concept-41bd49bf6b64442d91c232ec67529a3d"> Filtros de datos</a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

En este ejemplo, el conjunto de datos se construye a partir de dos tipos de fuentes de registro.

La fuente de registro 0 especifica los archivos de registro generados a partir de los datos de evento capturados por [!DNL Sensor]. Esta fuente de datos apunta a un directorio llamado Logs y a todos los archivos de ese directorio con un [!DNL .vsl] extensión de nombre de archivo.

El Origen de registro 1 señala a todos los archivos del directorio Registros con un [!DNL .txt] extensión de nombre de archivo. El grupo de descodificadores de este origen de registro se llama &quot;Registros de texto&quot;.

![](assets/cfg_LogProcessing_LogSources.png)

No debe eliminar ni mover archivos de registro una vez definidas las fuentes de datos de un conjunto de datos. Solo los archivos de registro recién creados deben agregarse al directorio para las fuentes de datos.

<!--
c_xml_log_sources.xml
-->

El archivo que contiene los datos de evento debe cumplir los siguientes requisitos:

* Los datos de evento deben incluirse en un archivo XML con el formato correcto y con las relaciones principales-secundarias adecuadas.
* Debe existir un grupo de decodificadores único para cada formato de archivo XML. Para obtener información sobre la construcción de un grupo de decodificadores, consulte [Grupos de decodificadores XML](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-log-proc-dataset-inc-files/c-xml-dec-grps.md#concept-5eda5ab253724674832f6951e2a0d1c3).
* Cada registro de visitante del archivo debe contener:

   * Un ID de seguimiento
   * Una marca de tiempo

* Para especificar las horas de inicio y finalización del procesamiento de datos, cada nombre de archivo debe ser del formulario

[!DNL YYYYMMDD-SOURCE.log]

donde *AAAAMMDD* es la hora media de Greenwich (GMT) del día de todos los datos del archivo, y *FUENTE* es una variable que identifica el origen de los datos contenidos en el archivo.

Para ver un ejemplo de un archivo XML que cumple estos requisitos, consulte [Grupos de decodificadores XML](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-log-proc-dataset-inc-files/c-xml-dec-grps.md#concept-5eda5ab253724674832f6951e2a0d1c3).

>[!NOTE]
>
>Póngase en contacto con los servicios de consultoría de Adobe para obtener una revisión de los archivos de registro XML que planea incorporar al conjunto de datos.

## Parámetros {#section-d07b96d7f6ad4affb9cc0a0bc1b88c4d}

Para los orígenes de registro XML, están disponibles los parámetros de la siguiente tabla.

>[!NOTE]
>
>El procesamiento de los orígenes de registro XML requiere parámetros adicionales que se definen en una [!DNL Log Processing Dataset Include] , que contiene un subconjunto de los parámetros incluidos en un [!DNL Log Processing.cfg] , así como parámetros especiales para definir descodificadores para extraer datos del archivo XML. Para obtener información sobre la definición de descodificadores para orígenes de registro XML, consulte [Grupos de decodificadores XML](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-log-proc-dataset-inc-files/c-xml-dec-grps.md#concept-5eda5ab253724674832f6951e2a0d1c3).

<table id="table_86B849F379CF4FEBA9294ACEF8F55184"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Campo </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Nombre </td> 
   <td colname="col2"> Identificador del origen de registro XML. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Rutas de registro </td> 
   <td colname="col2"> <p>Los directorios en los que se almacenan los orígenes de registro XML. La ubicación predeterminada es el directorio Logs . Una ruta relativa hace referencia al directorio de instalación del servidor de Data Workbench. </p> <p> Puede utilizar caracteres comodín para especificar qué orígenes de registro XML procesar: 
     <ul id="ul_0AE5D0ADE0F64CFAA856492A49239F58"> 
      <li id="li_4CBC0D1733F04258B3A55CC6FA714538 "> * coincide con cualquier número de caracteres </li> 
      <li id="li_81B597436A1241FF94E73C18A0ABBFA1"> ? hace coincidir un solo carácter </li> 
     </ul> </p> <p>Por ejemplo, la ruta de registro <span class="filepath"> Registros\*.xml</span> coincide con cualquier archivo del directorio Logs que termina en <span class="filepath"> .xml</span>. </p> <p> Si desea buscar todos los subdirectorios de la ruta especificada, debe configurar la variable <span class="wintitle"> Recursivo</span> field a true. </p> <p> <p>Nota: Si los archivos se van a leer desde el servidor de Data Workbench <span class="wintitle"> Unidad de servidor de archivos</span>, debe introducir los URI correspondientes en la variable <span class="wintitle"> Rutas de registro</span> campo . Por ejemplo, la variable <span class="filepath"> URI/Logs/*.xml</span> coincide con any <span class="filepath"> .xml</span> en el directorio Logs. Consulte <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-ins-svr-file-svr-unit.md#concept-995abff3fce34e439fb3f7f47191c80d"> Configuración de una unidad de servidor de archivos de Insight Server</a>. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Servidor de registro </td> 
   <td colname="col2"> Información (dirección, nombre, puerto, etc.) necesaria para conectarse a un servidor de archivos. Si hay una entrada en la variable <span class="wintitle"> Servidor de registro</span> , el campo <span class="wintitle"> Rutas de registro</span> se interpretan como URI. De lo contrario, se interpretan como rutas locales. Consulte <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-ins-svr-file-svr-unit.md#concept-995abff3fce34e439fb3f7f47191c80d"> Configuración de una unidad de servidor de archivos de Insight Server</a>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Comprimido </td> 
   <td colname="col2"> Verdadero o falso. Este valor debe establecerse en true si las fuentes de registro XML que lee el servidor de Data Workbench son archivos gzip comprimidos. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Grupo del decodificador </td> 
   <td colname="col2"> Nombre del grupo de decodificadores XML que se aplicará al origen de registro XML. Este nombre debe coincidir exactamente con el nombre del grupo de decodificadores XML correspondiente especificado en la variable <span class="wintitle"> Incluir conjunto de datos de procesamiento de registros</span> archivo. Consulte <a href="../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-log-proc-dataset-inc-files/c-xml-dec-grps.md#concept-5eda5ab253724674832f6951e2a0d1c3"> Grupos de decodificadores XML</a>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ID de origen de registro </td> 
   <td colname="col2"> <p>El valor de este campo puede ser cualquier cadena. Si se especifica un valor, este campo permite diferenciar las entradas de registro de diferentes fuentes de registro para la identificación de la fuente o el procesamiento dirigido. El campo x-log-source-id se rellena con un valor que identifica el origen del registro para cada entrada de registro. Por ejemplo, si desea identificar entradas de registro de un origen de archivos de registro denominado XMLFile01, puede escribir <span class="filepath"> de XMLFile01</span>, y esa cadena se pasaría al campo x-log-source-id por cada entrada de registro de ese origen. </p> <p> Para obtener información sobre el campo x-log-source-id , consulte <a href="../../../home/c-dataset-const-proc/c-ev-data-rec-fields.md#concept-06bda4be1a4649a2905a4422e9e6c42f"> Campos de registro de datos de evento</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Patrón de máscara </td> 
   <td colname="col2"> <p>Expresión regular con un único subpatrón de captura que extrae un nombre coherente utilizado para identificar el origen de una serie de archivos de registro. Solo se tiene en cuenta el nombre del archivo. La ruta y la extensión no se consideran para la coincidencia de expresiones regulares. Si no especifica un <span class="wintitle"> patrón de máscara</span>, se genera automáticamente una máscara. </p> <p> Para los archivos <span class="filepath"> Registros\010105server1.xml</span> y <span class="filepath"> Registros\010105server2.xml</span>, el patrón de máscara sería <code>[0-9]{6}(.*)</code>. Este patrón extrae la cadena "server1" o "server2" de los nombres de archivo anteriores. </p> <p> Consulte <a href="../../../home/c-dataset-const-proc/c-reg-exp.md#concept-070077baa419475094ef0469e92c5b9c"> Expresiones regulares</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Recursivo </td> 
   <td colname="col2"> Verdadero o falso. Si este parámetro se establece en true, todos los subdirectorios de cada ruta especificada en <span class="wintitle"> Rutas de registro</span> se buscan archivos que coincidan con el nombre de archivo o el patrón de comodín especificados. El valor predeterminado es false. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Rechazar archivo </td> 
   <td colname="col2"> Ruta y nombre de archivo del archivo que contiene las entradas de registro que no cumplen las condiciones del decodificador. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Usar horas de inicio/fin </td> 
   <td colname="col2"> <p>Verdadero o falso. Si este parámetro se establece en true y se especifica la hora de inicio o la hora de finalización, todos los archivos de este origen de registro deben tener nombres de archivo que empiecen por fechas en formato ISO (AAAAMMDD). Se supone que cada archivo contiene datos de un día GMT (por ejemplo, el intervalo de tiempo que comienza a las 000 GMT de un día y termina a las 000 GMT del día siguiente). Si los nombres de archivo de las fuentes de registro no comienzan con fechas ISO, o si los archivos contienen datos que no corresponden a un día GMT, este parámetro debe establecerse en false para evitar resultados incorrectos. </p> <p> <p>Nota: Si los requisitos de nomenclatura y intervalo de tiempo descritos anteriormente se cumplen para los archivos XML y se establece este parámetro en true, el grupo de descodificadores XML especificado limita los archivos leídos a aquellos cuyos nombres tengan fechas ISO que estén entre la hora de inicio y la hora de finalización especificadas. Si establece este parámetro en false, el servidor de Data Workbench lee todos los archivos XML durante el procesamiento del registro para determinar qué archivos contienen datos dentro del intervalo de tiempo de inicio y de finalización. </p> </p> <p> Para obtener información sobre los parámetros Hora de inicio y Hora de finalización, consulte <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md#concept-41bd49bf6b64442d91c232ec67529a3d"> Filtros de datos</a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>No debe eliminar ni mover orígenes de registro XML después de definir los orígenes de datos de un conjunto de datos. Solo los archivos XML recién creados deben agregarse al directorio para los orígenes de datos.

<!--
AVRO-log-file.xml
-->

La fuente de datos Avro proporciona una forma más eficaz de integrar datos en la Data Workbench:

<!-- <a id="section_45E3105B971C4220AE9CF573BEBF6080"></a> -->

* Avro proporciona un formato de fuente única para los datos de comercio y tráfico.
* La fuente Avro son datos comprimidos de varios fragmentos de origen proporcionados por día. Aprovisiona solo campos rellenados y proporciona funciones de supervisión y notificación, acceso a datos históricos y recuperación automática.
* El esquema, un diseño autodefinido de los archivos de registro de Avro, se incluye al principio de cada archivo.
* Se añaden nuevos campos con información de apoyo para introducir datos de Data Workbench sin necesidad de realizar ningún cambio en el decodificador. Se incluyen:

   * Evars: 1-250 (anteriormente 1-75)
   * Eventos personalizados: 1-1000 (frente a 1-100)
   * Acceso a variables de solución para datos móviles, sociales y de vídeo

>[!NOTE]
>
>Además, el uso de la fuente Avro permite el acceso inmediato a cualquier campo nuevo de la fuente sin apagarse, lo que permite actualizar los campos sin necesidad de horas de servicio.

La fuente de datos Avro se configura en archivos separados:

* Un **Archivo de registro de avro**: Este es el formato de registro de Avro generado desde el decodificador para dar formato al tráfico y a los datos de comercio.
* Un **Archivo de descodificador automático**: Este archivo permite asignar valores al nuevo formato Avro. Puede configurar el decodificador mediante el Asistente para decodificador automático.

## Asistente de decodificador automático {#section-9a824b4c3d5549e7952a7111232035b2}

Este asistente configura el archivo de registro del descodificador de Avro.

Para abrir, haga clic con el botón derecho en un espacio de trabajo y seleccione **Administrador** > **Asistentes** > **Asistente de decodificador automático**.

**Paso 1:** **Seleccionar un archivo de registro de avro**.

En este paso, puede seleccionar un archivo de origen para el esquema Avro. Se puede acceder a los esquemas desde un archivo de registro (.log) o desde un archivo de decodificador existente (.avro). Los esquemas se pueden extraer de cualquiera de los archivos.

| **Archivo de registro de avro ** | Haga clic en para abrir un archivo de registro (.log) para ver el esquema en la parte superior del archivo de registro y generar el archivo de decodificador. |
|---|---|
| **Archivo de decodificador automático** | Haga clic en para abrir y editar el esquema de un archivo de decodificador (.avro) existente. |

**Paso 2: Seleccionar campos de entrada**.

Seleccione los campos de entrada que se utilizarán en el conjunto de datos para pasar por el procesamiento de registros. Se muestran todos los campos del archivo, lo que le permite seleccionar los campos de la fuente.

>[!NOTE]
>
>A [!DNL x-product(Generates row)] se proporciona si se encuentra una matriz en los datos. Este campo genera nuevas filas para los datos anidados en una matriz como campos de entrada. Por ejemplo, si tiene una fila Visita individual con muchos valores de Producto en una matriz, entonces las filas se generarán en el archivo de entrada para cada producto.

| **Seleccionar valores predeterminados** | Seleccione los campos que desea identificar como un conjunto estándar de campos predeterminados . |
|---|---|
| **Seleccionar todo** | Seleccione todos los campos del archivo. |
| **Anular todas las selecciones** | Borre todos los campos del archivo. |

**Paso 3: Seleccione los campos que desea copiar para generar filas.**

Dado que se pueden crear filas nuevas a partir de valores anidados en una matriz, cada fila nueva creada debe tener un ID de seguimiento y una marca de tiempo. Este paso le permite seleccionar los campos que se copiarán en las filas del registro principal, como un ID de seguimiento y una marca de tiempo. También puede seleccionar otros valores que desee añadir a cada fila.

| **Seleccionar valores predeterminados** | Seleccione un conjunto estándar de campos predeterminados que requieran nuevos valores de columna agregados a cada fila, como un ID de seguimiento y una marca de tiempo. Por ejemplo, una [!DNL hit_source] field es un valor predeterminado que se debe agregar a cada nueva fila (se define como un valor predeterminado en la lista). Puede agregar otros valores de columna a cada fila según sea necesario. |
|---|---|
| **Seleccionar todo** | Seleccione todos los campos del archivo. |
| **Anular todas las selecciones** | Borre todos los campos del archivo. |

Utilice la variable **Buscar** para buscar valores en la lista.

**Paso 4: Especificar el nombre del decodificador**

Asigne un nombre al grupo de campos y guárdelo como un archivo decodificador. El nombre debe coincidir con el nombre del grupo Decoder especificado en el origen de registro.

**Paso 5: Guarde el archivo del decodificador.**

Se abrirá el menú de archivos para asignar un nombre al archivo del decodificador y guardarlo como un [!DNL .cfg] en el **Registros** carpeta.
