---
description: Instrucciones detalladas para instalar y configurar Sensor para un servidor Apache 1.3.x en RedHat Linux 7.x o posterior, SUSE Linux 9.x o posterior, Sun Solaris SPARC 2.6 o posterior, Sun Solaris x86 9 o posterior, FreeBSD 4 o posterior, o Mac OS X PowerPC.
title: Apache Server 1.3.x en Linux, Sun Solaris, FreeBSD o Mac OS X
uuid: bd46dd0f-fe36-4f8b-a87c-8ca7b64da609
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Apache Server 1.3.x en Linux, Sun Solaris, FreeBSD o Mac OS X{#apache-server-x-on-linux-sun-solaris-freebsd-or-mac-os-x}

Instrucciones detalladas para instalar y configurar Sensor para un servidor Apache 1.3.x en RedHat Linux 7.x o posterior, SUSE Linux 9.x o posterior, Sun Solaris SPARC 2.6 o posterior, Sun Solaris x86 9 o posterior, FreeBSD 4 o posterior, o Mac OS X PowerPC.

Los archivos de programa para Sensor se empaquetan en un archivo de instalación que se obtiene del sitio de descarga de Adobe. Si aún no dispone del archivo de instalación de Sensor para su servidor web en particular, descárguelo (o consiga el archivo a su representante de Adobe) antes de comenzar los siguientes procedimientos.

Para instalar y configurar Sensor, debe realizar los siguientes pasos de alto nivel:

## Instalación de los archivos de programa {#section-aae323e252394212bf4096d65fdd280c}

Instrucciones para extraer e instalar los archivos de programa para Sensor en el equipo servidor.

1. Inicie sesión como usuario raíz o como usuario con autoridad raíz.
1. Descomprima y descomprima el archivo de instalación con el siguiente comando:

   * En Linux:

      ```
      tar -zxf installationFilename.tar.gz
      ```

   * En Solaris:

      ```
      unzip -d installationFilename.tar.gz 
       tar -xf installationFilename.tar
      ```

1. Copie los archivos de programa sin empaquetar en los directorios identificados en la siguiente tabla:

<table id="table_A97CF630633C4543A742D96C302D1138"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Archivo </th> 
   <th colname="col2" class="entry"> Descripción </th> 
   <th colname="col3" class="entry"> Directorio de objetivos </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> mod_visual_sciences.so </td> 
   <td colname="col2"> El módulo de carga del selector </td> 
   <td colname="col3"> apachePath/libexec </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>txlogd </p> </td> 
   <td colname="col2"> El programa de transmisores </td> 
   <td colname="col3"> <p>/usr/local/bin </p> <p>--OR-- </p> <p>/usr/local/sbin </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> txlogd.conf </td> 
   <td colname="col2"> El archivo de configuración del sensor </td> 
   <td colname="col3"> /etc </td> 
  </tr> 
  <tr> 
   <td colname="col1"> trust_ca_cert.pem </td> 
   <td colname="col2"> Certificado utilizado para validar el certificado digital que Insight Server presenta durante el proceso de conexión </td> 
   <td colname="col3"> /usr/local/visual_sciences </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>El paquete de instalación contiene un archivo de hoja de cálculo llamado TestExperiment.xls. Esta hoja de cálculo es una herramienta que los arquitectos utilizan para configurar un experimento controlado. El sensor mismo no utiliza este archivo, por lo que no es necesario instalar el archivo en el equipo en el que se está ejecutando Sensor (aunque puede elegir hacerlo). En su lugar, puede que desee copiar el archivo en una ubicación en la que los arquitectos puedan acceder a él o simplemente extraer el archivo del paquete de instalación según sea necesario. Para obtener más información sobre la experimentación controlada, consulte la Guía de experimentos controlados con perspectiva.

**Permisos en los archivos de programa**

Los permisos incorrectos en los archivos de programa ocasionan la mayoría de los problemas que se producen al instalar Sensor.

Asegúrese de establecer los permisos exactamente como se indica en esta sección.

De forma predeterminada, los archivos de programa del archivo tar tienen los siguientes permisos. Según la configuración del sistema, esta configuración se puede modificar (sin máscara) al extraer los archivos. Para restablecer los permisos a la configuración predeterminada recomendada, utilice los comandos chmod siguientes. Compruebe que los directorios en los que ha instalado los archivos permiten al menos este nivel de acceso.

| Archivo | Permisos predeterminados | chmod, comando |
|---|---|---|
| mod_visual_sciences.so | rwx r-x r-x | chmod 755 |
| txlogd | rwx —x —x | chmod 711 |
| txlogd.conf | rw- rw- r— | chmod 664 |
| trust_ca_cert.pem | rw- rw- r— | chmod 664 |

## Editar el archivo de configuración del sensor {#section-3f22a1c91d7d43b6b4c30f1b7448b17f}

El [!DNL txlogd.conf] archivo contiene los parámetros de configuración para Sensor.

Debe editar el archivo para especificar, entre otras cosas, el tamaño de la cola de discos, la dirección del servidor de Insight y el ID que se adjuntará a los datos generados por este sensor.

El archivo de configuración contiene parámetros opcionales y parámetros requeridos.

* Los parámetros requeridos son configuraciones que debe especificar al instalar Sensor. Sin esta configuración, Sensor no se ejecuta correctamente.
* Los parámetros opcionales son valores predeterminados para valores predefinidos (que se pueden modificar) o para activar funciones opcionales.

Para editar el archivo de configuración del sensor

1. Abra el archivo /etc/txlogd.conf en un editor de texto y defina los parámetros requeridos, así como los parámetros opcionales que desee.
1. Guarde y cierre el archivo.

## Iniciar el transmisor y crear la cola de disco {#section-a453d912ec3d47aa8e40ccacf527119d}

Instrucciones para crear la cola de discos después de configurar el archivo txlogd.conf.

1. Si el directorio en el que reside la cola de discos no existe, créelo. Asegúrese de que el directorio proporciona acceso de lectura y escritura al archivo tanto al módulo del selector como al programa del transmisor.
1. En el equipo en el que está instalado Sensor, ejecute el siguiente comando para iniciar el transmisor:

   ```
   /usr/local/bin/txlogd -ic -f /etc/txlogd.conf
   ```

   * La opción &quot;i&quot; de este comando inicia el transmisor en modo interactivo. Este modo muestra los mensajes del transmisor en la pantalla y también le permite interactuar con el transmisor mediante comandos de teclado.
   * La opción &quot;c&quot; indica al transmisor que cree la cola de discos.
   * La opción &quot;f&quot; especifica la ubicación del archivo de configuración.

1. Compruebe que el transmisor ha creado la cola de discos en la ubicación especificada en el parámetro QueueFile y del tamaño especificado en el parámetro QueueSize.
1. Si la cola no se ha creado correctamente, escriba Ctrl+C para finalizar el transmisor y, a continuación, haga lo siguiente:

   1. Examine el archivo txtlogd.conf y verifique que los parámetros QueueFile y QueueSize estén configurados correctamente.
   1. Compruebe que el dispositivo al que está asignada la cola de discos está operativo y que tiene suficiente espacio disponible para guardar un archivo del tamaño especificado en el parámetro QueueSize.
   1. Realice las correcciones necesarias y repita este procedimiento.

## Agregar el recopilador al servidor Web {#section-a7fb6425956f4f518ae3a7db091b33d2}

Para los servidores Apache, el selector es un objeto compartido dinámico que se carga en el proceso del servidor web.

Para agregar el selector al servidor web, debe editar el archivo httpd.conf como se describe a continuación y reiniciar el servidor web.

Si Sensor está capturando datos para varios servidores Web en el equipo servidor, debe realizar el siguiente procedimiento para cada servidor Web.

1. Con un editor de texto, abra el [!DNL httpd.conf] archivo del servidor web cuyos eventos captura Sensor.
1. Agregue las siguientes líneas al final del archivo:

   ```
   LoadModule  visual_sciences_module  libexec/mod_visual_sciences.so 
   VisualSciencesConfig  /etc/txlogd.conf 
   AddModule mod_visual_sciences.c
   ```

   >[!NOTE]
   >
   >Estas líneas distinguen entre mayúsculas y minúsculas. Escriba exactamente como aparecen arriba.

1. Reinicie el servidor web. El recopilador se carga con el servidor web y empezará a recopilar datos de eventos y a escribirlos en la cola de discos.

## Comprobación del sensor {#section-83d9f60b39a6474f9c76bee3e19b2575}

Inicie el transmisor y verifique que pueda conectarse correctamente al servidor de Insight y transmitir datos de eventos al mismo.

>[!NOTE]
>
>Para verificar que el transmisor puede enviar correctamente datos de eventos al servidor de Insight, asegúrese de que el servidor de Insight de destino está instalado y en ejecución antes de comenzar la siguiente prueba.

1. Si el transmisor no se está ejecutando, reinícielo con el siguiente comando:

   ```
   /usr/local/bin/txlogd -i -f /etc/txlogd.conf 
   ```

1. Abra un navegador (en cualquier equipo) y solicite una página del servidor web en el que se está ejecutando Sensor (asegúrese de seleccionar una página que esté monitorizando Sensor).
1. Después de emitir la solicitud, compruebe en la consola del transmisor si hay mensajes que indiquen que está enviando datos de eventos al servidor de Insight de destino.
1. Si Sensor no transmite datos correctamente, compruebe que:

   * Se está ejecutando el servidor de Insight de destino.
   * Los parámetros [!DNL ServerAddress] y [!DNL ServerPort] se configuran correctamente en [!DNL txtlogd.conf].

   * Si especificó [!DNL ServerAddress] con un nombre de servidor, intente utilizar su dirección IP numérica en su lugar. El valor del [!DNL CertName] parámetro coincide exactamente con el nombre común que aparece en el certificado digital del servidor de Insight de destino.

## Agregar el transmisor a la secuencia de comandos de inicio del sistema {#section-4e1ffa6e043941ab91411d91d596477a}

Información para garantizar que el transmisor se carga automáticamente cuando se reinicia el equipo del servidor web.

Agregue el siguiente comando (que inicia el transmisor) a la secuencia de comandos de inicio del sistema.

```
/usr/local/bin/txlogd -f /etc/txlogd.conf
```

Este comando inicia el transmisor como un demonio. Los mensajes de funcionamiento y error que genera el transmisor se escriben en syslog.

>[!NOTE]
>
>Algunos usuarios de Solaris pueden encontrar un error &quot;no se puede adquirir mutex&quot;. Para que Sensor funcione correctamente en estos sistemas, es necesario agregar o editar la siguiente línea en el archivo /etc/system: >
>
```>
>semsys:seminfo_semmnu=1024
>```>
>The default Solaris setting is 60. Based on tests conducted with Sensor, which uses three semaphores for each instance, Adobe recommends that you use 1024 as your setting. This number is high enough for Sensor to function along with any other applications on the server that may require semaphores, but does not affect performance. To support this recommendation, please note that Adrian Cockcroft stated the following in his book Sun Performance and Tuning (Prentice Hall, October 1994): “Databases tend to use lots of shared memory and semaphore settings. These do not affect performance; as long as they are big enough, the programs will run.”



