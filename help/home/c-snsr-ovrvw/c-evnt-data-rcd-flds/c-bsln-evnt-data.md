---
description: Información sobre los campos de registro de datos de evento de línea de base registrados por Sensor.
title: Campos de registro de datos de evento de línea de base
uuid: aa36d332-089c-4ae2-98e2-a93d2fa023b7
exl-id: ad3d8806-863a-4871-a35b-6680163f00ac
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '461'
ht-degree: 3%

---

# Campos de registro de datos de evento de línea de base{#baseline-event-data-record-fields}

Información sobre los campos de registro de datos de evento de línea de base registrados por Sensor.

<table id="table_E29606BB010E4DB48C463979B7BEC769"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Campo </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> c-ip </td> 
   <td colname="col2"> <p>La dirección IP del cliente tal como se incluye en la solicitud realizada al servidor. </p> <p>Ejemplo: 207.68.146.68 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> cs(cookie) </td> 
   <td colname="col2"> <p>Las cookies enviadas por el cliente con la solicitud. </p> <p>Ejemplo: v1st=42FDF66DE610CF36; ASPSESSIONIDQCATDAQC=GPIBKEIBFBFIPLOJMKCAAEPM; </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> cs(referrer) </td> 
   <td colname="col2"> <p>Cadena de referente HTTP que el cliente envía al servidor con la solicitud. </p> <p>Ejemplo: http://www.mysite.net/cgi-bin/websearch?qry </p> <p>Si utiliza etiquetas de página, cs(referrer) es la dirección URL completa del documento que contiene la imagen de etiqueta, incluidos HTTP o HTTP. </p> <p>Además, puede configurar los sensores Apache (1.3, 2.0 y 2.2) e IIS para capturar el puerto que se utiliza para la solicitud, lo que puede identificar las solicitudes HTTP y HTTPS. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> cs(user-agent) </td> 
   <td colname="col2"> <p>Cadena que envía el cliente con su solicitud al servidor que indica qué tipo de agente de usuario es el cliente. </p> <p>Ejemplo: Mozilla/5.0 (Windows; U; Windows NT 5.1; en-US; rv:1.7) Gecko/20040707 Firefox/0.9.2 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> cs-method </td> 
   <td colname="col2"> <p>Tipo de método de la solicitud HTTP </p> <p>Ejemplo: GET </p> <p>Referencia: http://www.w3.org/TR/2000/NOTE-shoplogfileformat-20001115/#field_method </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> cs-uri-query </td> 
   <td colname="col2"> <p>La parte de la cadena de consulta del URI (raíz + cadena de consulta = URI) </p> <p>Esto va precedido de un signo de interrogación (?) y pueden contener uno o más pares de nombre-valor separados por el símbolo &amp;. </p> <p>Ejemplo: page=homepage </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> cs-uri-stem </td> 
   <td colname="col2"> <p>La parte raíz de URI (stem + cadena de consulta = URI) </p> <p>El sistema es la ruta lógica o real al recurso solicitado en el servidor. </p> <p>Ejemplo: /index.asp </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> sc(tipo de contenido) </td> 
   <td colname="col2"> <p>Tipo de contenido del recurso que solicita el cliente según los informes del servidor. </p> <p>Ejemplos: text/html, image/png, image/gif, video/mpeg </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> sc-bytes </td> 
   <td colname="col2"> <p>Número de bytes de datos enviados desde el servidor al cliente en respuesta a la solicitud. </p> <p>Ejemplo: 4996 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> sc-status </td> 
   <td colname="col2"> <p>El código de estado devuelto al cliente por el servidor. </p> <p>Ejemplo: 200 </p> <p>Referencia: http://www.w3.org/Protocols/rfc2616/rfc2616-sec10.html </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> s-dns </td> 
   <td colname="col2"> <p>Nombre de dominio o dirección IP completa del host del recurso solicitado. </p> <p>Ejemplo: www.omniture.com </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> x-experimentar </td> 
   <td colname="col2"> <p>Lista de todos los nombres y grupos de experimentos controlados de los que es miembro el cliente en el momento de la solicitud. </p> <p>Ejemplo: Home_Exp.Group_1,Registration_Exp.Group_2 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> x-timestamp </td> 
   <td colname="col2"> <p>La fecha y hora (GMT) a las que el servidor recibió la solicitud. </p> <p>El tiempo se expresa como el número de 100 nanosegundos desde el 1 de enero de 1600. </p> <p>Ejemplo: 1277109893200000000 sería el valor de x-timestamp para 11:28:52.000000 el martes 13 de septiembre de 2005. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> x-trackingid </td> 
   <td colname="col2"> <p>El valor hexadecimal de 64 bits del identificador único del explorador que se encuentra en una cookie persistente establecida por un sensor <span class="wintitle"> </span> y proporcionado por el cliente con una solicitud a un servidor. </p> <p>Ejemplo: 42FDF66DE610CF36 </p> </td> 
  </tr> 
 </tbody> 
</table>

El [!DNL data workbench server] puede derivar una serie de variables desde los campos de registro de datos de evento de línea de base. Para obtener más información, consulte la *Guía de configuración del conjunto de datos*.
