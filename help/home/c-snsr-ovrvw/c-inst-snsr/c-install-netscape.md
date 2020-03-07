---
description: Instrucciones para instalar y configurar Sensor en la familia de servidores Web que evolucionaron desde el servidor Web Netscape Enterprise original que se ejecuta en equipos Linux o Solaris. Incluye Netscape Enterprise, iPlanet, Sun ONE y Sun Java System Servers en Linux o Solaris.
title: Netscape Enterprise en Linux o Solaris
uuid: 47ea614c-d45c-4ab4-a8fe-ed9227da4582
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Netscape Enterprise en Linux o Solaris{#netscape-enteprise-on-linux-or-solaris}

Instrucciones para instalar y configurar Sensor en la familia de servidores Web que evolucionaron desde el servidor Web Netscape Enterprise original que se ejecuta en equipos Linux o Solaris. Incluye Netscape Enterprise, iPlanet, Sun ONE y Sun Java System Servers en Linux o Solaris.

Los archivos de programa para Sensor se empaquetan en un archivo de instalación que se obtiene del sitio de descarga de Adobe. Si aún no dispone del archivo de instalación de Sensor para su servidor web en particular, descárguelo (o consiga el archivo a su representante de Adobe) antes de comenzar los siguientes procedimientos.

Sensor admite los siguientes servidores que se ejecutan en RedHat Linux 7.x o posterior o Sun Solaris SPARC 2.6 o posterior:

* Netscape Enterprise Server 3.6 o posterior
* iPlanet Web Server 4.0 o posterior

Sensor admite estos servidores que se ejecutan en RedHat Linux 7.x o posterior o Sun Solaris 8.x o posterior:

* Sun ONE Web Server 6.0 o posterior
* Sun Java System Web Server 6.1 o posterior

El sensor admite estos servidores que se ejecutan en Sun Solaris x86 9 o posterior:

* Sun Java System Web Server 6.1 o posterior

>[!NOTE]
>
>El archivo de instalación de esta familia de servidores web se muestra como &quot;Sensor Netscape Solaris&quot; o &quot;Sensor Netscape LINUX&quot; en el sitio de descarga de Adobe.

Para instalar y configurar Sensor, debe realizar los siguientes pasos:

## Instalación de los archivos de programa {#section-2f3e85083b4f4aa989a85997330e86ae}

Procedimiento para extraer e instalar los archivos de programa para Sensor.

1. Inicie sesión como usuario raíz o como usuario con autoridad raíz.
1. Descomprima y descomprima el archivo de instalación con el siguiente comando:

   ```
   gunzip installationFilename.tar.gz 
   
       tar -xf installationFilename.tar
   ```

1. Copie los archivos de programa sin empaquetar en los directorios identificados en la siguiente tabla:

<table id="table_ABFF5F92271B4F3CB0AC68DAB6A5709F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Archivo </th> 
   <th colname="col2" class="entry"> Descripción </th> 
   <th colname="col3" class="entry"> Directorio de objetivos </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> aol_visual_sciences.so </td> 
   <td colname="col2"> Módulo de carga del selector. </td> 
   <td colname="col3"> <i>/usr/local/aolserver/visual_sciences</i> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>txlogd </p> </td> 
   <td colname="col2"> El programa de transmisores. </td> 
   <td colname="col3"> <p><i>/usr/local/bin</i> </p> <p><i>--OR--</i> </p> <p><i>/usr/local/sbin</i> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> txlogd.conf </td> 
   <td colname="col2"> El archivo de configuración del sensor. </td> 
   <td colname="col3"> <i>/etc</i> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> trust_ca_cert.pem </td> 
   <td colname="col2"> Certificado utilizado para validar el certificado digital que Insight Server presenta durante el proceso de conexión </td> 
   <td colname="col3"> <i>/usr/local/visual_sciences</i> </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>El paquete de instalación contiene un archivo de hoja de cálculo llamado TestExperiment.xls. Esta hoja de cálculo es una herramienta que los arquitectos utilizan para configurar un experimento controlado. El sensor mismo no utiliza este archivo, por lo que no es necesario instalar el archivo en el equipo en el que se está ejecutando Sensor (aunque puede elegir hacerlo). En su lugar, puede que desee copiar el archivo en una ubicación en la que los arquitectos puedan acceder a él o simplemente extraer el archivo del paquete de instalación según sea necesario. Para obtener más información sobre la experimentación controlada, consulte la Guía de experimentos controlados con perspectiva.

**Permisos en los archivos de programa**

>[!NOTE]
>
>Los permisos incorrectos en los archivos de programa ocasionan la mayoría de los problemas que se producen al instalar Sensor. Asegúrese de establecer los permisos exactamente como se indica en esta sección.
>
>De forma predeterminada, los archivos de programa del archivo tar tienen los siguientes permisos. Según la configuración del sistema, esta configuración se puede modificar (sin máscara) al extraer los archivos. Para restablecer los permisos a la configuración predeterminada recomendada, utilice los comandos chmod siguientes. Compruebe que los directorios en los que ha instalado los archivos permiten al menos este nivel de acceso.

| Archivo | Permisos predeterminados | chmod, comando |
|---|---|---|
| mod_visual_sciences.so | rwx r-x r-x | chmod 775 |
| txlogd | rwx —x —x | chmod 711 |
| txlogd.conf | rw- r— r— | chmod 664 |
| trust_ca_cert.pem | rw- r— r— | chmod 664 |

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

1. Si el directorio en el que reside la cola de discos no existe, créelo. Asegúrese de que el directorio proporciona acceso de lectura/escritura al archivo tanto al módulo del selector como al programa del transmisor.

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

## Agregar el recopilador al servidor AOL {#section-c5b83ae4ebce430aa764f951e849b333}

Para AOLServer, el selector es un objeto compartido dinámico que se carga en el proceso del servidor web.

Para agregar el selector al servidor AOL, debe editar el archivo de configuración del servidor como se describe a continuación y reiniciar el servidor AOL. Normalmente, el archivo de configuración del servidor se denomina nsd.tcl y se encuentra en el directorio en el que está instalado AOL Server.

1. Abra el archivo de configuración en un editor de texto y busque la siguiente sección:

   ```
   ns_section "ns/server/${servername}/modules" 
   ```

1. Agregue la siguiente línea. (Agregar como una sola instrucción. Omitir ajuste de palabras que se muestra a continuación).

   ```
   ns_param aol_visual_sciences /usr/local/aolserver/visual_sciences/aol_visual_sciences.so 
   ```

1. Cree una nueva sección como se indica a continuación.

   ```
   ns_section "ns/server/${servername}/module/aol_visual_sciences"
   ```

1. A esta nueva sección, agregue la línea:

   ```
   ns_param    VisualSciencesConfig    /etc/txlogd.conf
   ```

   >[!NOTE]
   >
   >Estas líneas distinguen entre mayúsculas y minúsculas. Escriba exactamente como aparecen arriba.

1. Reinicie el servidor AOL. El recopilador se carga y empezará a recopilar datos de eventos y a escribirlos en la cola de discos.

## Comprobación del sensor {#section-0dae181ef8884f10a57f6cfda8500969}

Compruebe que el recopilador está recopilando datos de eventos y que el transmisor los está transmitiendo al servidor de Insight de destino.

>[!NOTE]
>
>Para verificar que el transmisor puede enviar correctamente datos de eventos al servidor de Insight, asegúrese de que el servidor de Insight de destino está instalado y en ejecución antes de comenzar la siguiente prueba.

1. Si el transmisor no se está ejecutando, reinícielo con el siguiente comando:

   ```
   /usr/local/bin/txlogd -i -f /etc/txlogd.conf 
   ```

1. Abra un navegador (en cualquier equipo) y solicite una página del servidor web en el que se está ejecutando Sensor (asegúrese de seleccionar una página que esté monitorizando Sensor).
1. Después de emitir la solicitud, compruebe en la consola del transmisor si hay mensajes que indiquen que está enviando datos de eventos al servidor de Insight de destino.
1. Si el sensor no transmite datos correctamente, compruebe que:

   * Se está ejecutando el servidor de Insight de destino.
   * Los parámetros ServerAddress y ServerPort se establecen correctamente en txtlogd.conf. Si especificó ServerAddress con un nombre de servidor, intente utilizar su dirección IP numérica en su lugar.
   * El valor del parámetro CertName coincide exactamente con el nombre común que aparece en el certificado digital del servidor de Insight de destino.

## Agregar el transmisor al script de inicio del sistema {#section-19a38f27c9f44adf88f8910f5ed483a3}

Información sobre la carga automática del transmisor en la secuencia de comandos de inicio del sistema.

Para asegurarse de que el transmisor se carga automáticamente cuando se reinicia el equipo del servidor Web, agregue el siguiente comando (que inicia el transmisor) a la secuencia de comandos de inicio del sistema:

```
/usr/local/bin/txlogd -f /etc/txlogd.conf
```

Este comando inicia el transmisor como un demonio. Los mensajes de funcionamiento y error que genera el transmisor se escriben en [!DNL syslog].

La configuración predeterminada de Solaris es 60. En base a las pruebas realizadas con Sensor, que utiliza tres semáforos para cada instancia, Adobe recomienda usar 1024 como configuración. Este número es lo suficientemente alto como para que Sensor funcione junto con cualquier otra aplicación del servidor que requiera semáforos, pero que no afecte al rendimiento. Para apoyar esta recomendación, tenga en cuenta que Adrian Cockcroft declaró lo siguiente en su libro Sun Performance and Tuning (Prentice Hall, octubre de 1994): &quot;Las bases de datos tienden a utilizar muchos ajustes de memoria compartida y semáforo. No afectan al rendimiento; mientras sean lo suficientemente grandes, los programas se ejecutarán&quot;.
