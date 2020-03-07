---
description: El sensor adquiere todos los datos de medición que se transmiten en las solicitudes de página (solicitudes GET) realizadas a los servidores Web en los que se ha instalado.
solution: Analytics
title: Adquisición de datos de solicitud de página
topic: Data workbench
uuid: 06cf2b14-8d2c-483e-8a75-ce772798978f
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Adquisición de datos de solicitud de página{#acquiring-page-request-data}

El sensor adquiere todos los datos de medición que se transmiten en las solicitudes de página (solicitudes GET) realizadas a los servidores Web en los que se ha instalado.

[!DNL Sensor] adquiere estos datos de medición a través de la interfaz de programación de aplicaciones del servidor web, directamente desde la instancia o instancias del software del servidor web que se ejecuta en el servidor web. [!DNL Sensor] no accede a los archivos de registro generados por el servidor web. De hecho, después [!DNL Sensor] de que se haya instalado y probado el servidor del área de trabajo de datos, la función de registro nativo del servidor web se puede desactivar sin afectar a la recopilación de datos. En muchos casos, la desactivación del registro de archivos en los discos locales de los propios equipos de servidores Web mejora la capacidad de servicio de páginas de esos servidores Web debido a la cantidad relativamente grande de E/S en disco fijo necesaria para registrar esta información en el disco local del equipo de servidores Web.

[!DNL Sensor] recopila datos de medición y solicitud web directamente de cada proceso de servidor web y proceso de servidor web virtual (si corresponde) y escribe temporalmente los datos en un archivo de cola, una cola de memoria tolerante a errores con respaldo de disco fijo, en el equipo de servidor web. El servicio Sensor Transmitter (o daemon según la plataforma) recupera datos del archivo de cola y luego los comprime y cifra antes de transmitirlos al servidor del área de trabajo de datos para almacenamiento a largo plazo. Con [!DNL Sensor], los datos se acumulan en los equipos del servidor web en el archivo de cola solo si tiene un problema de red u otro que impida su transmisión. El archivo de cola permite un almacenamiento local eficiente de horas a días de datos de solicitud web para proteger los datos si un fallo de red o del sistema no permite que los datos se transmitan al servidor del área de trabajo de datos en tiempo real.

[!DNL Sensor] recopila datos de medición de cada proceso físico y lógico del servidor Web, los filtra por tipo de contenido, los comprime, los cifra y los transmite al servidor del área de trabajo de datos.

La siguiente tabla contiene los campos de información de registro adquiridos por [!DNL Sensor] cada solicitud GET que no se filtra según el archivo de [!DNL Sensor’s] configuración:

<table id="table_5F65474150EC41648B35D0B031FB9B15"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Nombre de W3C </th> 
   <th colname="col2" class="entry"> Datos recopilados </th> 
   <th colname="col3" class="entry"> Explicación </th> 
   <th colname="col4" class="entry"> Explicación </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> x-trackingid </td> 
   <td colname="col2"> Identificador de seguimiento (visitante único) </td> 
   <td colname="col3"> Identificador leído desde una cookie colocada en el explorador del usuario por <span class="wintitle"> Sensor </span> en la solicitud inicial del visitante </td> 
   <td colname="col4"> V1st=3C94007B4E01F9C2 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Fecha </p> <p>Fecha </p> </td> 
   <td colname="col2"> Marca de tiempo </td> 
   <td colname="col3"> Hora a la que el servidor procesó la solicitud (con una precisión de 100 ns; la precisión depende del entorno del servidor y de NTP) </td> 
   <td colname="col4"> 2002-11-21 17:21:45.123 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> sc(content-Type) </td> 
   <td colname="col2"> Tipo de contenido </td> 
   <td colname="col3"> Tipo de objeto devuelto por el servidor </td> 
   <td colname="col4"> text/html </td> 
  </tr> 
  <tr> 
   <td colname="col1"> sc-status </td> 
   <td colname="col2"> Código de estado de respuesta HTTP </td> 
   <td colname="col3"> Código numérico generado por el servidor que anota el estado de la respuesta del servidor HTTP </td> 
   <td colname="col4"> 404 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> cs-uri-stem </td> 
   <td colname="col2"> Identificador URI </td> 
   <td colname="col3"> La parte raíz del URI solicitado por el cliente </td> 
   <td colname="col4"> <span class="filepath"> pagedir/page.asp </span> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> c-ip </td> 
   <td colname="col2"> IP del cliente </td> 
   <td colname="col3"> Dirección IP del cliente solicitante </td> 
   <td colname="col4"> 127.0.0.1 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> s-dns </td> 
   <td colname="col2"> Nombre de dominio del servidor </td> 
   <td colname="col3"> Nombre de dominio del servidor web que procesa la solicitud </td> 
   <td colname="col4"> <span class="filepath"> www.domain.com </span> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> cs(referrer) </td> 
   <td colname="col2"> Dirección URL de referencia </td> 
   <td colname="col3"> Contenido del campo de referente HTTP enviado por el cliente </td> 
   <td colname="col4"> <span class="filepath"> http://www.referringsite.com </span> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> cs(user-agent) </td> 
   <td colname="col2"> Agente de usuario </td> 
   <td colname="col3"> Dispositivo utilizado para realizar una solicitud al servidor HTTP </td> 
   <td colname="col4"> Mozilla/4.0+(compatible;+MSIE+6.0; +Windows+NT+5.1) </td> 
  </tr> 
  <tr> 
   <td colname="col1"> cs(cookie) </td> 
   <td colname="col2"> Cookies de cliente del dominio </td> 
   <td colname="col3"> Contenido de todas las cookies del usuario para el sitio </td> 
   <td colname="col4"> <p>KL_TC1 1038058778312 </p> <p>KL972x1038058778312282052 </p> <p>KL_PVKL972 0 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> cs-uri-query </td> 
   <td colname="col2"> Cadena de consulta </td> 
   <td colname="col3"> La parte de cadena de consulta, si la hay, del URI solicitado por el cliente </td> 
   <td colname="col4"> PAGENAME=dynamic1&amp;link=3001 </td> 
  </tr> 
 </tbody> 
</table>

