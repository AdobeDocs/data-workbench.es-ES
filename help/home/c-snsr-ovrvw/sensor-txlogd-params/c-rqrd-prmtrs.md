---
description: Información sobre los parámetros de Sensor txlogd.conf requeridos.
solution: Insight
title: Parámetros requeridos
uuid: 187f4199-ec7f-4d5a-93eb-64a62d51ec7b
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Required Parameters{#required-parameters}

Información sobre los parámetros de Sensor txlogd.conf requeridos.

<table id="table_69CFE10A3707403F9793137B128E706A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> En este parámetro... </th> 
   <th colname="col2" class="entry"> Especifique... </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> SensorID </td> 
   <td colname="col2"> <p>Una cadena de caracteres que identifica exclusivamente este <span class="wintitle"> sensor</span>. </p> <p> <span class="wintitle"> El sensor</span> conecta el SensorID a cada registro de eventos que envía al servidor <span class="keyword"></span>del área de trabajo de datos. El SensorID permite distinguir los datos de eventos de este servidor web de los datos de eventos capturados por otros <span class="wintitle"> Sensores</span>. </p> <p>Aunque un SensorID puede constar de cualquier cadena de caracteres, por convención se utiliza el nombre del servidor web cuyos eventos está capturando el <span class="wintitle"> Sensor</span> . El uso del nombre del servidor como SensorID facilita la determinación del origen de un evento durante la fase de análisis. También garantiza que el SensorID sea único dentro de la implementación. </p> <p>Ejemplo: Web001a de <span class="filepath"> SensorID</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ServerAddress </td> 
   <td colname="col2"> <p>Dirección del servidor <span class="keyword"> del área de trabajo de datos al que este</span> sensor <span class="wintitle"></span> envía datos de eventos. </p> <p>Nota:  <p>Al trabajar en un entorno agrupado, <span class="wintitle"> Sensor</span> debe configurarse para acceder al servidor <span class="keyword"></span> maestro del área de trabajo de datos a fin de evitar problemas de sincronización. En el Área de trabajo de datos puede ver información sobre los servidores <span class="keyword"> del área de trabajo de datos de procesamiento del clúster mediante el elemento de menú Servidores relacionados del Administrador</span> de <span class="wintitle"></span>servidores. Para obtener más información sobre el Administrador <span class="wintitle"> de</span>servidores, consulte la Guía <i><span class="keyword"> del sensor</span><span class="wintitle"> de Área de trabajo de datos</span></i>. </p> <p>Si el servidor web puede resolver nombres de servidor mediante DNS, puede especificar la dirección del servidor por nombre. Si no es así, debe especificar la dirección IP numérica del servidor. </p> <p>Ejemplo: <span class="filepath"> ServerAddress 10.1.0.7</span> o </p> <p> <span class="filepath"> ServerAddress vserver01.miempresa.com</span> </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> SSL </td> 
   <td colname="col2"> <p>Indica si <span class="wintitle"> Sensor</span> se comunica con <span class="keyword"> el servidor</span> del área de trabajo de datos mediante HTTP o HTTPS. Se configura como "activado" para HTTPS o "desactivado" para HTTP. </p> <p>Ejemplo: <span class="filepath"> SSL en</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ServerPort </td> 
   <td colname="col2"> <p>El puerto en el que el servidor <span class="keyword"></span> del área de trabajo de datos escucha datos de eventos. </p> <p>Ejemplo: <span class="filepath"> ServerPort 443</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> CertName </td> 
   <td colname="col2"> <p>Solo es necesario si el parámetro SSL está establecido en "on". </p> <p>Nombre común del servidor <span class="keyword"> del área de trabajo de datos al que este</span> sensor <span class="wintitle"></span> envía datos de eventos. </p> <p>El valor que especifique debe coincidir exactamente con el nombre común que aparece en el certificado de licencia del servidor <span class="keyword"></span> del área de trabajo de datos. </p> <p>Ejemplo: <span class="filepath"> CertName vserver01.miempresa.com</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> CertPath </td> 
   <td colname="col2"> <p>Solo es necesario si el parámetro SSL está establecido en "on". </p> <p>El directorio en el que se encuentra el archivo de autoridad de certificación (<span class="filepath"> trust_ca_cert.pem</span>) </p> <p>Ejemplos: </p> <p> <span class="filepath"> CertPath /usr/local/visualsensor</span> </p> <p> <span class="filepath"> CertPath C:\VisualSensor</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> QueueFile </td> 
   <td colname="col2"> <p>No es necesario para instalaciones de <span class="wintitle"> sensores</span> en equipos de servidor de Microsoft Windows 2000 o 2003 que ejecutan las versiones 5.x o 6.x del servicio de información de Internet (IIS). </p> <p>Nombre completo del archivo de cola de discos. </p> <p>Aunque puede asignar cualquier nombre a este archivo, por convención, el archivo de cola se denomina <span class="filepath"> VisualSensor.dat</span>. </p> <p>Para instalaciones <span class="wintitle"> de sensores</span> en Unix, puede colocar este archivo en cualquier lugar. En Windows que ejecuta un servidor web Java, debe colocar este archivo en el mismo directorio que el transmisor. Para todos los demás servidores web, este archivo debe residir en el directorio /var/queue. </p> <p>Ejemplo: Archivo <span class="filepath"> de cola /var/queue/VisualSensor.dat</span> </p> <p> <p>Nota:  Asegúrese de que el dispositivo al que asigna este archivo tiene suficiente espacio libre para alojar una cola del tamaño que necesita. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> QueueSize </td> 
   <td colname="col2"> <p>Un entero que representa el tamaño del archivo de cola de disco en MB. </p> <p>Para las instalaciones de <span class="wintitle"> Sensor</span> en Microsoft Windows, el archivo de cola mismo se crea en el mismo directorio que el transmisor y se denomina <span class="filepath"> Diskq2000.log</span>. </p> <p>El ejemplo siguiente establece el tamaño de la cola en 200 MB: </p> <p>QueueSize 200 </p> <p>El ejemplo siguiente establece el tamaño de la cola en 2 GB: </p> <p>QueueSize 2000 </p> </td> 
  </tr> 
 </tbody> 
</table>

