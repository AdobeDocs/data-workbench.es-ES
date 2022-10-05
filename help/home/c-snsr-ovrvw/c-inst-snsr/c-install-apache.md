---
description: Instrucciones sobre cómo instalar y configurar Apache Server 2.0.40, 2.0.42 o posterior, Apache Server 2.2 o Apache Server 2.4 en Linux, Sun Solaris o FreeBSD.
title: Apache Server 2.0.40, 2.0.42 o posterior, y Apache Server 2.2 o 2.4 en Linux, Solaris o FreeBSD
uuid: 3703e2c1-5b8d-4def-b146-49e59d78a669
exl-id: d5b943be-e9ca-4601-88c7-bb2bfdc0d080
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '1546'
ht-degree: 2%

---

# Apache Server 2.0.40, 2.0.42 o posterior, y Apache Server 2.2 o 2.4 en Linux, Solaris o FreeBSD{#apache-server-or-later-and-apache-server-or-on-linux-solaris-or-freebsd}

{{eol}}

Instrucciones sobre cómo instalar y configurar Apache Server 2.0.40, 2.0.42 o posterior, Apache Server 2.2 o Apache Server 2.4 en Linux, Sun Solaris o FreeBSD.

Los archivos de programa para Sensor están empaquetados en un archivo de instalación que usted obtiene del sitio de descarga de Adobe. Si todavía no tiene el archivo de instalación Sensor para su servidor web en particular, descárguelo (u obtenga el archivo de su representante de Adobe) antes de iniciar los siguientes procedimientos.

Para instalar y configurar Sensor, debe realizar los siguientes pasos de alto nivel:

Se admiten los siguientes servidores Apache:

* Apache Server 2.0.40 que se ejecuta en RedHat Linux 7.x o posterior, o Sun Solaris SPARC 2.6 o posterior.
* Apache Server 2.0.40, 2.0.42 o posterior, Apache Server 2.2 o Apache Server 2.4 en Linux, Sun Solaris o FreeBSD
* Apache Server 2.0.42 o posterior que se ejecuta en RedHat Linux 7.x o posterior, Sun Solaris SPARC 2.6 o posterior, SUSE Linux 9.x o posterior, o FreeBSD 5.3.
* Apache Server 2.0.42 o posterior que se ejecuta en versiones de 64 bits de RedHat Linux ES 4 y ES 5.
* Apache Server 2.2 que se ejecuta en RedHat Linux 7.x o posterior o Sun Solaris SPARC 2.6 o posterior.
* Apache Server 2.4 que se ejecuta en RedHat Linux 7.x o posterior, o Sun Solaris x86_64 o FreeBSD

>[!NOTE]
>
>Aunque las instrucciones para instalar Sensores en servidores web que ejecutan Apache Server versiones 2.0.40, 2.0.42 o posteriores (32 y 64 bits) o 2.2 son las mismas (excepto cuando se indican en los procedimientos siguientes), los archivos de instalación de cada versión difieren. Antes de instalar el sensor, asegúrese de que ha recibido los archivos de instalación correctos para las versiones del servidor Apache y del sistema operativo que está ejecutando.

## Instalación de los archivos de programa {#section-2f3e85083b4f4aa989a85997330e86ae}

Procedimiento para extraer e instalar los archivos de programa del sensor.

1. Inicie sesión como usuario raíz o como usuario con autoridad raíz.
1. Descomprima y descomprima el archivo de instalación utilizando el siguiente comando:

   * En Linux:

      ```
      tar -zxf installationFilename
      ```

      ```
      unzip -d installationFilename.tar.gz 
       tar -xf installationFilename.tar
      ```

   * En Solaris:

1. Copie los archivos de programa no empaquetados en los directorios identificados en la siguiente tabla:

<table id="table_ABFF5F92271B4F3CB0AC68DAB6A5709F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Archivo </th> 
   <th colname="col2" class="entry"> Descripción </th> 
   <th colname="col3" class="entry"> Directorio de Target </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> mod_visual_sciences.so </td> 
   <td colname="col2"> Módulo de carga del recolector. </td> 
   <td colname="col3"> <i> IBMHttpServer/módulos</i> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>txlogd </p> </td> 
   <td colname="col2"> El programa del transmisor. </td> 
   <td colname="col3"> <p><i>/usr/local/bin</i> </p> <p><i>--OR--</i> </p> <p><i>/usr/local/sbin</i> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> txlogd.conf </td> 
   <td colname="col2"> El archivo de configuración del sensor. </td> 
   <td colname="col3"> <i>/etc</i> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> trust_ca_cert.pem </td> 
   <td colname="col2"> Certificado utilizado para validar el certificado digital que presenta Insight Server durante el proceso de conexión </td> 
   <td colname="col3"> <i>/usr/local/visual_sciences</i> </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>El paquete de instalación contiene un archivo de hoja de cálculo denominado TestExperiment.xls. Esta hoja de cálculo es una herramienta que los arquitectos utilizan para configurar un experimento controlado. El propio sensor no utiliza este archivo, por lo que no es necesario instalar el archivo en el equipo en el que se está ejecutando Sensor (aunque puede elegir hacerlo). En su lugar, puede que desee copiar el archivo en una ubicación en la que sus arquitectos puedan acceder a él o simplemente extraer el archivo del paquete de instalación según sea necesario. Para obtener más información sobre la experimentación controlada, consulte la Guía de experimentos controlados con perspectiva.

**Permisos en los archivos de programa**

>[!NOTE]
>
>Los permisos incorrectos en los archivos de programa causan la mayoría de los problemas encontrados al instalar Sensor. Asegúrese de establecer los permisos exactamente como se indica en esta sección.
>
>De forma predeterminada, los archivos de programa del archivo tar tienen los siguientes permisos. Según la configuración del sistema, esta configuración se puede modificar (desenmascarar) al extraer los archivos. Para restablecer los permisos a la configuración predeterminada recomendada, utilice los comandos chmod que se indican a continuación. Compruebe que los directorios en los que ha instalado los archivos permiten al menos este nivel de acceso.

| Archivo | Permisos predeterminados | chmod, comando |
|---|---|---|
| mod_visual_sciences.so | rwx r-x r-x | chmod 775 |
| txlogd | rwx —x —x | chmod 711 |
| txlogd.conf | rw- r— r— | chmod 664 |
| trust_ca_cert.pem | rw- r— r— | chmod 664 |

## Habilitar el inicio de sesión en el mismo servidor {#section-2e2f1875a5304cdfa2cbcd0680683cfd}

Pasos que le permiten iniciar sesión en el servidor de Sametime.

1. Utilice el cliente administrador de Lotus Domino para conectarse al servidor de Lotus Domino que ejecuta Sametime.
1. En Lotus Domino Administrator, haga clic en la ficha Archivos y, a continuación, haga doble clic en Sametime Configuration - stconfig.nsf para abrir el archivo de configuración de Sametime.
1. En el archivo de configuración de la misma hora, abra el formulario Servicios de la comunidad y haga doble clic en cualquier lugar del formulario para entrar en el modo de edición.
1. Establezca el indicador de registro de chat en &quot;estricto&quot; y Capture Service Type en &quot;0x1000&quot;.
1. Guarde y cierre el formulario de Servicios de comunidad y, a continuación, cierre el archivo de Configuración de la misma hora.
1. Reinicie el servidor Sametime.

## Edición del archivo de configuración del sensor {#section-de0eb4a646394b61abb6cd5a2b706de0}

La variable [!DNL txlogd.conf] contiene los parámetros de configuración para Sensor.

Debe editar este archivo para especificar, entre otras cosas, el tamaño y la ubicación del archivo de cola de disco, la dirección del servidor de Insight y el ID que se adjuntará a los datos de evento producidos por este sensor.

El archivo de configuración contiene los parámetros necesarios y los parámetros opcionales.

* **Parámetros necesarios** son ajustes que debe especificar al instalar Sensor. Sin estos ajustes, el sensor no se ejecuta correctamente.
* **Parámetros opcionales** son configuraciones que se establecen de forma predeterminada en valores predefinidos (que puede modificar) o habilitar funciones opcionales.

**Para editar el archivo de configuración del sensor**

* Abra el [!DNL /etc/txlogd.conf] en un editor de texto y establezca los parámetros necesarios, así como los parámetros opcionales que desee.
* Guarde y cierre el archivo.

**Para editar el archivo de configuración del sensor**

1. Abra el [!DNL /etc/txlogd.conf] en un editor de texto y establezca los parámetros necesarios, así como los parámetros opcionales que desee.
1. Guarde y cierre el archivo.

## Inicie el transmisor y cree la cola de disco {#section-55630de65f264274aefd771da2002852}

Después de configurar el archivo txlogd.conf, puede iniciar el programa del transmisor, registrarlo como un servicio de Windows y crear la cola de discos.

1. Si el directorio en el que reside la cola de discos no existe, créelo. Asegúrese de que el directorio proporciona acceso de lectura/escritura al archivo tanto al módulo del recolector como al programa del transmisor.

   Para obtener más información sobre los permisos requeridos por los archivos de cola de disco, consulte Permisos de archivo UNIX de sensor.
1. En el equipo en el que está instalado Sensor, ejecute el siguiente comando para iniciar el transmisor:

   ```
   /usr/local/bin/txlogd -ic -f /etc/txlogd.conf
   ```

   * La opción &quot;i&quot; de este comando inicia el transmisor en &quot;modo interactivo&quot;. Este modo muestra los mensajes del transmisor en la pantalla y también le permite interactuar con el transmisor mediante comandos de teclado.
   * La opción &quot;c&quot; indica al transmisor que cree la cola de discos.
   * La opción &quot;f&quot; especifica la ubicación del archivo de configuración.

   Para obtener más información sobre las opciones que puede utilizar al iniciar el transmisor, consulte Opciones de la línea de comandos del transmisor de sensores.

1. Compruebe que el transmisor ha creado la cola de discos en la ubicación especificada en el parámetro QueueFile y del tamaño especificado en el parámetro QueueSize.
1. Si la cola no se ha creado correctamente, escriba Ctrl+C para finalizar el transmisor y haga lo siguiente:

   1. Examine el archivo txtlogd.conf y verifique que los parámetros QueueFile y QueueSize estén correctamente configurados.
   1. Compruebe que el dispositivo al que está asignada la cola de disco funciona y que tiene suficiente espacio disponible para guardar un archivo del tamaño especificado en el parámetro QueueSize.
   1. Realice las correcciones necesarias y repita este procedimiento.

## Agregar el recopilador al servidor web {#section-c5b83ae4ebce430aa764f951e849b333}

Para los servidores HTTP de IBM, el recopilador es un objeto compartido dinámico que se carga en el proceso del servidor web.

Para agregar el recolector al servidor web, debe editar el archivo httpd.conf como se describe a continuación y reiniciar el servidor web.

Si Sensor está capturando datos de varios servidores web en el equipo servidor, debe realizar el siguiente procedimiento para cada servidor web.

1. Con un editor de texto, abra el archivo httpd.conf del servidor web cuyos eventos captura Sensor.
1. Añada las dos líneas siguientes al final del archivo:

   ```
   LoadModule visual_sciences_module modules/mod_visual_sciences.so 
   VisualSciencesConfig /etc/txlogd.conf
   ```

   >[!NOTE]
   >
   >Estas líneas distinguen entre mayúsculas y minúsculas. Escriba exactamente como aparecen arriba.

1. Reinicie el proceso del servidor web (no tiene que reiniciar el equipo servidor completo, simplemente reinicie el proceso del servidor web). El recolector se carga con el servidor web y comienza a recopilar datos de evento y a escribirlos en la cola de disco.

## Comprobación del sensor {#section-0dae181ef8884f10a57f6cfda8500969}

Compruebe que el recolector recopila datos de evento y que el transmisor los está transmitiendo al servidor de Insight de destino.

>[!NOTE]
>
>Para verificar que el transmisor pueda enviar correctamente datos de evento al servidor de Insight, asegúrese de que el servidor de Insight de destino esté instalado y en ejecución antes de comenzar la siguiente prueba.

1. Si el transmisor aún no está en ejecución, reiniciarlo utilizando el siguiente comando:

   ```
   /usr/local/bin/txlogd -i -f /etc/txlogd.conf 
   ```

1. Abra un explorador (en cualquier equipo) y solicite una página del servidor web en el que se está ejecutando Sensor (asegúrese de seleccionar una página que el Sensor esté monitorizando).
1. Después de emitir la solicitud, compruebe si hay mensajes en la consola del transmisor que indiquen que está enviando datos de evento al servidor de Insight de destino.
1. Si el sensor no transmite los datos correctamente, compruebe que:

   * Se está ejecutando el destino Insight Server.
   * Los parámetros ServerAddress y ServerPort se establecen correctamente en txtlogd.conf. Si especificó ServerAddress con un nombre de servidor, intente usar su dirección IP numérica en su lugar.
   * El valor del parámetro CertName coincide exactamente con el nombre común que aparece en el certificado digital del servidor de Insight de destino.

## Agregar el transmisor al script de inicio del sistema {#section-19a38f27c9f44adf88f8910f5ed483a3}

Información sobre la carga automática del transmisor en el script de inicio del sistema.

Para asegurarse de que el transmisor se carga automáticamente cuando se reinicia el equipo del servidor web, agregue el siguiente comando (que inicia el transmisor) al script de inicio del sistema:

```
/usr/local/bin/txlogd -f /etc/txlogd.conf
```

Este comando inicia el transmisor como un demonio. Los mensajes de funcionamiento y de error que genera el transmisor se escriben en syslog.
