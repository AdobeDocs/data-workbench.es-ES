---
description: Información sobre los parámetros txlogd.conf necesarios del sensor.
title: Parámetros necesarios
uuid: 187f4199-ec7f-4d5a-93eb-64a62d51ec7b
exl-id: 782e11e9-b11b-4003-9669-f31187208ec3
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '538'
ht-degree: 1%

---

# Parámetros necesarios{#required-parameters}

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
   <td colname="col2"> <p>Cadena de caracteres que identifica de forma exclusiva este <span class="wintitle"> sensor</span>. </p> <p> <span class="wintitle"> </span> Envía el SensorID a cada registro de evento que envía al servidor <span class="keyword">  </span> de Data Workbench. El SensorID permite distinguir los datos de evento de este servidor web de los datos de evento capturados por otros <span class="wintitle"> sensores</span>. </p> <p>Aunque un SensorID puede constar de cualquier cadena de caracteres, por convención, se utiliza el nombre del servidor web cuyos eventos captura el <span class="wintitle"> Sensor</span>. El uso del nombre del servidor como SensorID facilita la determinación del origen de un evento durante la fase de análisis. También garantiza que el SensorID sea único dentro de la implementación. </p> <p>Ejemplo: <span class="filepath"> SensorID web001a</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> DirecciónServidor </td> 
   <td colname="col2"> <p>La dirección del <span class="keyword"> servidor de Data Workbench</span> al que este <span class="wintitle"> sensor</span> envía datos de evento. </p> <p>Nota:  <p>Cuando se trabaja en un entorno agrupado, el <span class="wintitle"> Sensor</span> debe configurarse para acceder al servidor maestro <span class="keyword"> de Data Workbench</span> a fin de evitar problemas de sincronización. En Data Workbench, puede ver información sobre los <span class="keyword"> servidores de Data Workbench</span> de procesamiento del clúster mediante el elemento de menú Servidores relacionados del <span class="wintitle"> Administrador de servidores</span>. Para obtener más información sobre el <span class="wintitle"> Administrador de servidores</span>, consulte la <i><span class="keyword"> Guía del </span><span class="wintitle"> sensor</span></i> de la Data Workbench. </p> <p>Si el servidor web puede resolver nombres de servidor a través de DNS, puede especificar la dirección del servidor por su nombre. Si no es así, debe especificar la dirección IP numérica del servidor. </p> <p>Ejemplo: <span class="filepath"> ServerAddress 10.1.0.7</span> o </p> <p> <span class="filepath"> ServerAddress vserver01.mycompany.com</span> </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> SSL </td> 
   <td colname="col2"> <p>Indica si el <span class="wintitle"> sensor</span> se comunica con el <span class="keyword"> servidor de Data Workbench</span> mediante HTTP o HTTPS. Establézcalo en "on" para HTTPS o "off" para HTTP. </p> <p>Ejemplo: <span class="filepath"> SSL en</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ServerPort </td> 
   <td colname="col2"> <p>Puerto en el que el <span class="keyword"> servidor de Data Workbench</span> escucha datos de evento. </p> <p>Ejemplo: <span class="filepath"> ServerPort 443</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> CertName </td> 
   <td colname="col2"> <p>Requerido solo si el parámetro SSL está establecido en "on". </p> <p>El nombre común del <span class="keyword"> servidor de Data Workbench</span> al que este <span class="wintitle"> sensor</span> envía datos de evento. </p> <p>El valor que especifique debe coincidir exactamente con el nombre común que aparece en el certificado de licencia <span class="keyword"> data workbench server</span> . </p> <p>Ejemplo: <span class="filepath"> CertName vserver01.mycompany.com</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> CertPath </td> 
   <td colname="col2"> <p>Requerido solo si el parámetro SSL está establecido en "on". </p> <p>El directorio en el que se encuentra el archivo de autoridad de certificación (<span class="filepath"> trust_ca_cert.pem</span>) </p> <p>Ejemplos: </p> <p> <span class="filepath"> CertPath /usr/local/visualsensor</span> </p> <p> <span class="filepath"> CertPath C:\VisualSensor</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> QueueFile </td> 
   <td colname="col2"> <p>No es necesario para instalaciones de <span class="wintitle"> Sensor</span> en máquinas de servidor de Microsoft Windows 2000 o 2003 que ejecutan las versiones 5.x o 6.x del Servicio de información de Internet (IIS). </p> <p>Nombre completo del archivo de cola de disco. </p> <p>Aunque puede asignar cualquier nombre a este archivo, por convención, el archivo de cola se llama <span class="filepath"> VisualSensor.dat</span>. </p> <p>Para instalaciones del <span class="wintitle"> Sensor</span> en Unix, puede colocar este archivo en cualquier lugar. En Windows que ejecuta un servidor web Java, debe colocar este archivo en el mismo directorio que el transmisor. Para todos los demás servidores web, este archivo debe residir en el directorio /var/queue. </p> <p>Ejemplo: <span class="filepath"> Archivo de cola /var/queue/VisualSensor.dat</span> </p> <p> <p>Nota:  Asegúrese de que el dispositivo al que asigne este archivo tenga suficiente espacio libre para albergar una cola del tamaño que necesite. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> QueueSize </td> 
   <td colname="col2"> <p>Un entero que representa el tamaño del archivo de cola de disco en MB. </p> <p>Para instalaciones de <span class="wintitle"> Sensor</span> en Microsoft Windows, el archivo de cola en sí se crea en el mismo directorio que el transmisor y se llama <span class="filepath"> Diskq2000.log</span>. </p> <p>El siguiente ejemplo establece el tamaño de la cola en 200 MB: </p> <p>TamañoCola 200 </p> <p>El siguiente ejemplo establece el tamaño de la cola en 2 GB: </p> <p>TamañoCola 2000 </p> </td> 
  </tr> 
 </tbody> 
</table>
