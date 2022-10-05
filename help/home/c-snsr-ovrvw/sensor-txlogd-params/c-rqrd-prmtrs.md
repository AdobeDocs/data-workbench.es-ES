---
description: Información sobre los parámetros txlogd.conf necesarios del sensor.
title: Parámetros necesarios
uuid: 187f4199-ec7f-4d5a-93eb-64a62d51ec7b
exl-id: 782e11e9-b11b-4003-9669-f31187208ec3
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '538'
ht-degree: 1%

---

# Parámetros necesarios{#required-parameters}

{{eol}}

Información sobre los parámetros txlogd.conf necesarios del sensor.

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
   <td colname="col2"> <p>Una cadena de caracteres que la identifica de forma exclusiva <span class="wintitle"> Sensor</span>. </p> <p> <span class="wintitle"> Sensor</span> adjunta el SensorID a cada registro de evento que envía a la variable <span class="keyword"> servidor de data workbench</span>. El SensorID permite distinguir los datos de evento de este servidor web de los datos de evento capturados por otros <span class="wintitle"> Sensores</span>. </p> <p>Aunque un SensorID puede constar de cualquier cadena de caracteres, por convención, el nombre del servidor web cuyos eventos pertenecen a <span class="wintitle"> Sensor</span> se utiliza la captura. El uso del nombre del servidor como SensorID facilita la determinación del origen de un evento durante la fase de análisis. También garantiza que el SensorID sea único dentro de la implementación. </p> <p>Ejemplo: <span class="filepath"> SensorID web001a</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> DirecciónServidor </td> 
   <td colname="col2"> <p>La dirección del <span class="keyword"> servidor de data workbench</span> a los que <span class="wintitle"> Sensor</span> envía datos de evento. </p> <p>Nota:  <p>Cuando se trabaja en un entorno agrupado, <span class="wintitle"> Sensor</span> debe configurarse para acceder al maestro <span class="keyword"> servidor de data workbench</span> para evitar problemas de sincronización. En Data Workbench, puede ver información sobre el procesamiento <span class="keyword"> servidores de data workbench</span> en el clúster utilizando el elemento de menú Servidores relacionados en la <span class="wintitle"> Administrador de servidores</span>. Para obtener más información sobre la variable <span class="wintitle"> Administrador de servidores</span>, consulte la <i><span class="keyword"> Data Workbench</span><span class="wintitle"> Sensor</span> Guía</i>. </p> <p>Si el servidor web puede resolver nombres de servidor a través de DNS, puede especificar la dirección del servidor por su nombre. Si no es así, debe especificar la dirección IP numérica del servidor. </p> <p>Ejemplo: <span class="filepath"> ServerAddress 10.1.0.7</span> o </p> <p> <span class="filepath"> ServerAddress vserver01.mycompany.com</span> </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> SSL </td> 
   <td colname="col2"> <p>Si <span class="wintitle"> Sensor</span> se comunica con <span class="keyword"> servidor de data workbench</span> uso de HTTP o HTTPS. Establézcalo en "on" para HTTPS o "off" para HTTP. </p> <p>Ejemplo: <span class="filepath"> SSL en</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ServerPort </td> 
   <td colname="col2"> <p>El puerto en el que <span class="keyword"> servidor de data workbench</span> escucha datos de eventos. </p> <p>Ejemplo: <span class="filepath"> ServerPort 443</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> CertName </td> 
   <td colname="col2"> <p>Requerido solo si el parámetro SSL está establecido en "on". </p> <p>El nombre común de la variable <span class="keyword"> servidor de data workbench</span> a los que <span class="wintitle"> Sensor</span> envía datos de evento. </p> <p>El valor que especifique debe coincidir exactamente con el nombre común que aparece en la variable <span class="keyword"> servidor de data workbench</span> certificado de licencia. </p> <p>Ejemplo: <span class="filepath"> CertName vserver01.mycompany.com</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> CertPath </td> 
   <td colname="col2"> <p>Requerido solo si el parámetro SSL está establecido en "on". </p> <p>El directorio en el que la autoridad de certificación (<span class="filepath"> trust_ca_cert.pem</span>). </p> <p>Ejemplos: </p> <p> <span class="filepath"> CertPath /usr/local/visualsensor</span> </p> <p> <span class="filepath"> CertPath C:\VisualSensor</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> QueueFile </td> 
   <td colname="col2"> <p>No se necesita para <span class="wintitle"> Sensor</span> instalaciones en equipos de servidor Microsoft Windows 2000 o 2003 que ejecuten las versiones 5.x o 6.x del Servicio de información de Internet (IIS). </p> <p>Nombre completo del archivo de cola de disco. </p> <p>Aunque puede asignar cualquier nombre a este archivo, por convención, se nombra el archivo de cola <span class="filepath"> VisualSensor.dat</span>. </p> <p>Para <span class="wintitle"> Sensor</span> en Unix, puede colocar este archivo en cualquier lugar. En Windows que ejecuta un servidor web Java, debe colocar este archivo en el mismo directorio que el transmisor. Para todos los demás servidores web, este archivo debe residir en el directorio /var/queue. </p> <p>Ejemplo: <span class="filepath"> Archivo de cola /var/queue/VisualSensor.dat</span> </p> <p> <p>Nota: Asegúrese de que el dispositivo al que asigne este archivo tenga suficiente espacio libre para albergar una cola del tamaño que necesite. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> QueueSize </td> 
   <td colname="col2"> <p>Un entero que representa el tamaño del archivo de cola de disco en MB. </p> <p>Para <span class="wintitle"> Sensor</span> instalaciones en Microsoft Windows, el archivo de cola en sí se crea en el mismo directorio que el transmisor y se denomina <span class="filepath"> Diskq2000.log</span>. </p> <p>El siguiente ejemplo establece el tamaño de la cola en 200 MB: </p> <p>TamañoCola 200 </p> <p>El siguiente ejemplo establece el tamaño de la cola en 2 GB: </p> <p>TamañoCola 2000 </p> </td> 
  </tr> 
 </tbody> 
</table>
