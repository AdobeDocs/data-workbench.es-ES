---
description: Instrucciones para instalar y configurar Sensor para Apache Server 1.3, Apache Server 2.0.42 o posterior, o Apache Server 2.2 que se ejecuta en Microsoft Windows Server 2000 o posterior.
title: Apache Server 1.3, 2, 2.2 o 2.4 en Windows Server 2000 o posterior
uuid: e159ed83-6004-4f65-a3b7-502cac1d0862
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Apache Server 1.3, 2, 2.2 o 2.4 en Windows Server 2000 o posterior{#apache-server-or-on-windows-server-or-later}

Instrucciones para instalar y configurar Sensor para Apache Server 1.3, Apache Server 2.0.42 o posterior, o Apache Server 2.2 que se ejecuta en Microsoft Windows Server 2000 o posterior.

Los archivos de programa para Sensor se empaquetan en un archivo de instalación que se obtiene del sitio de descarga de Adobe. Si aún no dispone del archivo de instalación de Sensor para su servidor web en particular, descárguelo (o consiga el archivo a su representante de Adobe) antes de comenzar los siguientes procedimientos.

* Apache Server 1.3
* Apache Server 2.0.42 o posterior
* Apache Server 2.2 se ejecuta en Microsoft Windows Server 2000 o posterior

## Instalación de los archivos de programa {#section-2f3e85083b4f4aa989a85997330e86ae}

Antes de instalar los archivos de programa, debe determinar dónde desea mantener la cola de discos, ya que allí también debe instalar los archivos de programa.Procedimiento para extraer e instalar los archivos de programa para Sensor.

Para instalar y configurar Sensor, debe realizar los siguientes pasos:

1. En el equipo Windows, cree un directorio en el que instalar los archivos de programa de Sensor. Tenga en cuenta que la cola de discos también reside en este directorio, por lo que asegúrese de que el dispositivo que elija tenga espacio suficiente para mantener una cola del tamaño que necesita.

   ```
   C:\VisualSensor
   ```

1. Extraiga el contenido del archivo de instalación en el directorio que acaba de crear. Durante este paso, Sensor instala los siguientes archivos:

<table id="table_ABFF5F92271B4F3CB0AC68DAB6A5709F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Archivo </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> EventMessages.dll </td> 
   <td colname="col2"> Mensajes del visor de eventos. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> mod_visual_sciences.dll </td> 
   <td colname="col2"> Módulo del selector. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>TestExperiment.xls </p> </td> 
   <td colname="col2"> <p>Archivo de hoja de cálculo de Excel que los arquitectos pueden utilizar para configurar un experimento controlado. El sensor no utiliza este archivo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> trust_ca_cert.pem </td> 
   <td colname="col2"> Certificado utilizado para validar el certificado digital que Insight Server presenta durante el proceso de conexión. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> TXLog.exe </td> 
   <td colname="col2"> El programa de transmisores </td> 
  </tr> 
  <tr> 
   <td colname="col1"> txlogd.conf </td> 
   <td colname="col2"> El archivo de configuración del sensor </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>El paquete de instalación contiene un archivo de hoja de cálculo llamado TestExperiment.xls. Esta hoja de cálculo es una herramienta que los arquitectos utilizan para configurar un experimento controlado. El sensor mismo no utiliza este archivo, por lo que no es necesario instalar el archivo en el equipo en el que se está ejecutando Sensor (aunque puede elegir hacerlo). En su lugar, puede que desee copiar el archivo en una ubicación en la que los arquitectos puedan acceder a él o simplemente extraer el archivo del paquete de instalación según sea necesario. Para obtener más información sobre la experimentación controlada, consulte la Guía de experimentos controlados con perspectiva.

## Editar el archivo de configuración del sensor {#section-2e2f1875a5304cdfa2cbcd0680683cfd}

El [!DNL txlogd.conf] archivo contiene los parámetros de configuración para Sensor.

Debe editar este archivo para especificar, entre otras cosas, el tamaño y la ubicación del archivo de cola de disco, la dirección del servidor de Insight y el ID que se adjuntará a los datos de evento producidos por este sensor.

El archivo de configuración contiene parámetros opcionales y parámetros requeridos.

* **Los parámetros** requeridos son configuraciones que debe especificar al instalar Sensor. Sin esta configuración, Sensor no se ejecuta correctamente.
* **Los parámetros** opcionales son valores predeterminados para valores predefinidos (que puede modificar) o para activar funciones opcionales.

**Para editar el archivo de configuración del sensor**

* Abra el [!DNL /etc/txlogd.conf] archivo en un editor de texto y defina los parámetros requeridos, así como los parámetros opcionales que desee.
* Guarde y cierre el archivo.

**Para editar el archivo de configuración del sensor**

1. Abra el [!DNL /etc/txlogd.conf] archivo en un editor de texto y defina los parámetros requeridos, así como los parámetros opcionales que desee.
1. Guarde y cierre el archivo.

## Iniciar el transmisor y crear la cola de disco {#section-55630de65f264274aefd771da2002852}

Después de configurar el archivo txlogd.conf, puede iniciar el programa del transmisor, registrarlo como un servicio de Windows y crear la cola de discos.

1. Si el directorio en el que reside la cola de discos no existe, créelo. Asegúrese de que el directorio proporciona acceso de lectura y escritura al archivo tanto al módulo del selector como al programa del transmisor.

   Para obtener más información sobre los permisos requeridos por los archivos de cola de discos, consulte Permisos de archivos de Sensor UNIX.
1. En el equipo en el que está instalado Sensor, ejecute el siguiente comando para iniciar el transmisor:

   ```
   /usr/local/bin/txlogd -ic -f /etc/txlogd.conf
   ```

   * La opción &quot;i&quot; de este comando inicia el transmisor en &quot;modo interactivo&quot;. Este modo muestra los mensajes del transmisor en la pantalla y también le permite interactuar con el transmisor mediante comandos de teclado.
   * La opción &quot;c&quot; indica al transmisor que cree la cola de discos.
   * La opción &quot;f&quot; especifica la ubicación del archivo de configuración.
   Para obtener información adicional sobre las opciones que puede utilizar al iniciar el transmisor, consulte Opciones de la línea de comandos del transmisor de sensores.

1. Compruebe que el transmisor ha creado la cola de discos en la ubicación especificada en el parámetro QueueFile y del tamaño especificado en el parámetro QueueSize.
1. Si la cola no se ha creado correctamente, escriba Ctrl+C para finalizar el transmisor y, a continuación, haga lo siguiente:

   1. Examine el archivo txtlogd.conf y verifique que los parámetros QueueFile y QueueSize estén configurados correctamente.
   1. Compruebe que el dispositivo al que está asignada la cola de discos está operativo y que tiene suficiente espacio disponible para guardar un archivo del tamaño especificado en el parámetro QueueSize.
   1. Realice las correcciones necesarias y repita este procedimiento.

## Agregar el recopilador al servidor Web {#section-c5b83ae4ebce430aa764f951e849b333}

Para los servidores Apache, el selector es un objeto compartido dinámico que se carga en el proceso del servidor web.

Para agregar el selector al servidor web, debe editar el [!DNL httpd.conf] archivo como se describe a continuación y reiniciar el servidor web.

>[!NOTE]
>
>Si Sensor está capturando datos para varios servidores Web en el equipo servidor, debe realizar el siguiente procedimiento para cada servidor Web.

1. Con un editor de texto, abra el [!DNL httpd.conf]archivo del servidor web cuyos eventos captura Sensor.
1. Agregue las dos líneas siguientes al final del archivo:

   ```
   LoadModule visual_sciences_module modules/mod_visual_sciences.so 
   VisualSciencesConfig /etc/txlogd.conf
   ```

   >[!NOTE]
   >
   >Estas líneas distinguen entre mayúsculas y minúsculas. Escriba exactamente como aparecen arriba.

1. Reinicie el proceso del servidor web (no tiene que reiniciar todo el equipo del servidor, simplemente reinicie el proceso del servidor web). El recopilador se carga con el servidor web y comienza a recopilar datos de eventos y a escribirlos en la cola de discos.

