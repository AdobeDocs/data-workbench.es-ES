---
description: Información sobre los campos de datos que el servidor del área de trabajo de datos puede procesar para construir un conjunto de datos.
solution: Analytics
title: Campos de registro de datos del evento
topic: Data workbench
uuid: b0232bfa-0a3b-4e3d-876e-6a15a3764eae
translation-type: tm+mt
source-git-commit: 27600561841db3705f4eee6ff0aeb8890444bbc9

---


# Campos de registro de datos del evento{#event-data-record-fields}

Información sobre los campos de datos que el servidor del área de trabajo de datos puede procesar para construir un conjunto de datos.

* [Acerca de los datos del evento](../../home/c-dataset-const-proc/c-ev-data-rec-fields.md#section-3a0705f8c1824017aa4effed9903efbe)
* [Campos de registro de datos del evento previsto](../../home/c-dataset-const-proc/c-ev-data-rec-fields.md#section-a882ed7aa6af41eeb45a55bf8c1ca3d7)
* [Campos derivados](../../home/c-dataset-const-proc/c-ev-data-rec-fields.md#section-b6c57ee2aa31469fbd5dab90e52bc677)

## Acerca de los datos del evento {#section-3a0705f8c1824017aa4effed9903efbe}

Los datos de eventos que se utilizan para generar un conjunto de datos residen en los archivos a los que se hace referencia como fuentes de registro. Los datos disponibles en las fuentes de registro se denominan datos de eventos porque cada registro de datos representa un registro de transacciones o una sola instancia de un evento con una marca de tiempo asociada.

Los datos de eventos de una fuente de registro se recopilan en tiempo real por [!DNL Sensors]. Los datos de eventos recopilados por [!DNL Sensors] HTTP y los servidores de aplicaciones se transmiten a los servidores del área de trabajo de datos, que convierten los datos en archivos de registro ( [!DNL .vsl]) comprimidos. El servidor del área de trabajo de datos lee los datos de eventos que residen en un archivo plano, un archivo XML o un origen de datos ODBC y proporciona los descodificadores que se definen para extraer un conjunto común de campos de datos de estos diferentes formatos.

Las siguientes secciones proporcionan información sobre los campos de datos (denominados campos de registro de datos de eventos o campos de entrada de registros) que el servidor del área de trabajo de datos recopila [!DNL Sensors] o lee y pone a disposición del servidor.

>[!NOTE]
>
>Los nombres de los campos generalmente siguen la convención de nombres para el formato de archivo de registro ampliado W3C. Muchos de los campos tienen prefijos que indican el origen de la información contenida en el campo:

* cs indica la comunicación del cliente con el servidor.
* sc indica la comunicación del servidor con el cliente.
* s indica información del servidor.
* c indica información del cliente.
* x indica la información que crea un producto de software de Adobe.

## Campos de registro de datos del evento previsto {#section-a882ed7aa6af41eeb45a55bf8c1ca3d7}

Los archivos de registro ( [!DNL .vsl]) contienen los campos de datos de eventos recopilados de los servidores por [!DNL Sensors] el servidor del área de trabajo de datos y utilizados por éste en el proceso de construcción del conjunto de datos. En la tabla siguiente se muestran los campos de un registro de datos de evento típico registrado por [!DNL Sensor]:

<table id="table_98E135FE4EAF44D6ADEB3C6C1C0BF6A4"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Campo </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> c-ip </td> 
   <td colname="col2"> <p>La dirección IP del cliente tal como se incluye en la solicitud realizada al servidor. </p> <p> Ejemplo: 207.68.146.68 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> cs(cookie) </td> 
   <td colname="col2"> <p>Las cookies enviadas por el cliente con la solicitud. </p> <p> Ejemplo: v1st=42FDF66DE610CF36; ASPSESSIONIDQCATDAQC=GPIBKEIBFBFIPLOJMKCAAEPM; </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> cs(referrer) </td> 
   <td colname="col2"> <p>La cadena de referente HTTP que el cliente envía al servidor con la solicitud. </p> <p> Ejemplo: <span class="filepath"> http://www.mysite.net/cgi-bin/websearch?qry </span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> cs(user-agent) </td> 
   <td colname="col2"> <p>La cadena enviada por el cliente con su solicitud al servidor que indica qué tipo de agente de usuario es el cliente. </p> <p> Ejemplo: Mozilla/5.0 (Windows; U; Windows NT 5.1; en-US; rv:1.7) Gecko/20040707 Firefox/0.9.2 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> cs-method </td> 
   <td colname="col2"> <p>El tipo de método de la solicitud HTTP. </p> <p> Ejemplo: OBTENER </p> <p> Referencia: <span class="filepath"> http://www.w3.org/TR/2000/NOTE-shoplogfileformat-20001115/#field_method </span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> cs-uri-query </td> 
   <td colname="col2"> <p>La porción de cadena de consulta de URI (raíz + cadena de consulta = URI). Esto va precedido de un signo de interrogación (?) y puede contener uno o más pares de nombre-valor separados por signos de interrogación (&amp;). </p> <p> Ejemplo: page=homepage </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> cs-uri-stem </td> 
   <td colname="col2"> <p>La parte raíz del URI (raíz + cadena de consulta = URI). La derivación es la ruta real o lógica al recurso solicitado en el servidor. </p> <p> Ejemplo: <span class="filepath"> /index.asp </span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> sc(content-type) </td> 
   <td colname="col2"> <p>El tipo de contenido del recurso que solicita el cliente según lo informado por el servidor. </p> <p> Ejemplos: text/html, image/png, image/gif, video/mpeg </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> sc-bytes </td> 
   <td colname="col2"> <p>Número de bytes de datos enviados desde el servidor al cliente en respuesta a la solicitud </p> <p> Ejemplo: 4996 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> sc-status </td> 
   <td colname="col2"> <p>Código de estado devuelto al cliente por el servidor. </p> <p> Ejemplo: 200 </p> <p> Referencia: <span class="filepath"> http://www.w3.org/Protocols/rfc2616/rfc2616-sec10.html </span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> s-dns </td> 
   <td colname="col2"> <p>El nombre de dominio completo o la dirección IP del host del recurso solicitado. </p> <p> Ejemplo: <span class="filepath"> www.adobe.com </span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> x-experience </td> 
   <td colname="col2"> <p>Lista de todos los nombres y grupos de experimentos controlados a los que pertenece el cliente en el momento de la solicitud. </p> <p> Ejemplo: VSHome_Exp.Group_1,VSRegregistration_Exp.Group_2 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> x-timestamp </td> 
   <td colname="col2"> <p>La fecha y hora (GMT) a las que el servidor recibió la solicitud. El tiempo se expresa como el número de 100 nanosegundos desde el 1 de enero de 1600. </p> <p> Ejemplo: 127710989320000000 sería el valor de x-timestamp para 11:28:52.0000000 el martes 13 de septiembre de 2005. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> x-trackingid </td> 
   <td colname="col2"> <p>El valor hexadecimal de 64 bits del identificador único del explorador que se encuentra en una cookie persistente, tal como lo establece un <span class="wintitle"> sensor </span> y lo proporciona el cliente con una solicitud a un servidor. </p> <p> Ejemplo: 42FDF66DE610CF36 </p> </td> 
  </tr> 
 </tbody> 
</table>

## Campos derivados {#section-b6c57ee2aa31469fbd5dab90e52bc677}

La tabla siguiente muestra ejemplos de campos que el servidor del área de trabajo de datos deriva de los campos del registro de datos de eventos de línea de base:

<table id="table_3B008F1314804A69AE69E8F94908F497"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Campo </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> cs(cookie)(name) </td> 
   <td colname="col2"> Valor de un par nombre-valor determinado dentro de una cookie. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> cs(referrer-domain) </td> 
   <td colname="col2"> <p>El nombre de dominio o la dirección IP del URI de referencia HTTP. </p> <p> <p>Nota:  Este campo es de sólo lectura. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> cs(referrer-host) </td> 
   <td colname="col2"> <p>Nombre de host completo del referente. </p> <p> Ejemplo: Si cs(referrer) es <span class="filepath"> http://my.domain.com/my/page </span>, cs(referrer-host) es <span class="filepath"> my.domain.com </span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> cs(referrer-query)(name) </td> 
   <td colname="col2"> <p>Valor de una cadena de consulta de referente. </p> <p> <p>Nota:  No se puede acceder a un valor de cadena de consulta de referente mediante el campo cs(referrer)(name). </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> cs-uri </td> 
   <td colname="col2"> <p>El URI completo (raíz + cadena de consulta = URI completo). </p> <p> Ejemplo: <span class="filepath"> /shopping/checkout.html?product1=8Track&amp;product2=casette&amp;product3=cd </span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> cs-uri-query(name) </td> 
   <td colname="col2"> <p>El valor asociado al nombre dado. Si existen varios valores para el nombre dado, este campo devuelve el último de esos valores. </p> Ejemplos: 
    <ul id="ul_47BBB2E3076A46629BFCDB2A460F700B"> 
     <li id="li_AC9BB29505A54AE4AFF49438530C9EA4"> Para el URI <span class="filepath"> /shopping/checkout.html?product1=8Track&amp;product2=casette&amp;product3=cd </span>, cs-uri-query(product3) devolverá cd. </li> 
     <li id="li_B036C1D0B25748E0A155DDC9B1B999CB"> Para el URI <span class="filepath"> /shopping/checkout.html?product1=8Track&amp;product1=casette </span>, <span class="wintitle"> cs-uri-query(product1) </span> devolverá la caseta. </li> 
    </ul> <p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ctime </td> 
   <td colname="col2"> x-timestamp expresada como segundos desde el 1 de enero de 1970. Este campo también se denomina x-unixtime. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> date </td> 
   <td colname="col2"> x-timestamp con el formato AAAA-MM-DD. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> time </td> 
   <td colname="col2"> x-timestamp en el formato HH:MM:SS. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> x-local-timestring </td> 
   <td colname="col2"> <p>x-timestamp convertida a la zona horaria local especificada en el archivo <span class="filepath"> Transformation.cfg </span> para el conjunto de datos. El formato es AAAA-MM-DD HH:MM:SS.mmm. </p> <p> <p>Nota:  También puede definir conversiones de tiempo como x-local-timestring en el <span class="filepath"> archivo Log Processing.cfg </span> . Para obtener más información, consulte <a href="../../home/c-dataset-const-proc/c-log-proc-config-file/c-abt-log-proc-config-file.md"> Archivo de configuración de procesamiento de registros </a>. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> x-log-source-id </td> 
   <td colname="col2"> <p>Identificador correspondiente al origen de registro de una entrada de registro en particular. Para que se registre el identificador, debe especificarlo en el campo ID de origen de <span class="wintitle"> registro </span> del archivo <span class="filepath"> Log Processing.cfg </span> al definir fuentes de datos <span class="wintitle"> Sensor </span>, archivo de registro o ODBC. Para obtener más información, consulte <a href="../../home/c-dataset-const-proc/c-log-proc-config-file/c-abt-log-proc-config-file.md"> Archivo de configuración de procesamiento de registros </a>. </p> <p> Ejemplo: de VSensor01. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> x-mask </td> 
   <td colname="col2"> Patrón de máscara de las fuentes de datos del <span class="wintitle"> sensor </span> (derivado de los nombres de archivo <span class="filepath"> .vsl </span> ). Para un archivo cuyo nombre tenga el formato <span class="filepath"> YYYYMDD-SENSORID.VSL </span>, x-mask es SENSORID. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> x-timestring </td> 
   <td colname="col2"> x-timestamp con el formato AAAA-MM-DD HH:MM:SS.mmm. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> x-unixtime </td> 
   <td colname="col2"> Hora decimal UNIX derivada de x-timestamp. </td> 
  </tr> 
 </tbody> 
</table>

[!DNL Sensor], cuando se utiliza en un servidor, puede recopilar campos de datos de eventos de cualquier solicitud HTTP válida o encabezado de respuesta o variable disponible para ella a través de la API del servidor. Para recopilar estos campos de datos, debe especificar los campos de encabezado o las variables que desee en el archivo de [!DNL txlogd.conf]configuración de [!DNL Sensor]. For more information, see the *Data Workbench[!DNL Sensor]Guide*.