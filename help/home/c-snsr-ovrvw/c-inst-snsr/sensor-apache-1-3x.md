---
description: Instrucciones detalladas para instalar y configurar Sensor para un Apache Server 1.3.x en RedHat Linux 7.x o posterior, SUSE Linux 9.x o posterior, Sun Solaris SPARC 2.6 o posterior, Sun Solaris x86 9 o posterior, FreeBSD 4 o posterior, o Mac OS X PowerPC.
title: Apache Server 1.3.x en Linux, Sun Solaris, FreeBSD o Mac OS X
uuid: bd46dd0f-fe36-4f8b-a87c-8ca7b64da609
exl-id: 087494fb-c8f0-457c-b3db-d9147a739998
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '1345'
ht-degree: 2%

---

# Apache Server 1.3.x en Linux, Sun Solaris, FreeBSD o Mac OS X{#apache-server-x-on-linux-sun-solaris-freebsd-or-mac-os-x}

{{eol}}

Instrucciones detalladas para instalar y configurar Sensor para un Apache Server 1.3.x en RedHat Linux 7.x o posterior, SUSE Linux 9.x o posterior, Sun Solaris SPARC 2.6 o posterior, Sun Solaris x86 9 o posterior, FreeBSD 4 o posterior, o Mac OS X PowerPC.

Los archivos de programa para Sensor están empaquetados en un archivo de instalación que usted obtiene del sitio de descarga de Adobe. Si todavía no tiene el archivo de instalación Sensor para su servidor web en particular, descárguelo (u obtenga el archivo de su representante de Adobe) antes de iniciar los siguientes procedimientos.

Para instalar y configurar Sensor, debe realizar los siguientes pasos de alto nivel:

## Instalación de los archivos de programa {#section-aae323e252394212bf4096d65fdd280c}

Instrucciones para extraer e instalar los archivos de programa para Sensor en el equipo servidor.

1. Inicie sesión como usuario raíz o como usuario con autoridad raíz.
1. Descomprima y descomprima el archivo de instalación utilizando el siguiente comando:

   * En Linux:

      ```
      tar -zxf installationFilename.tar.gz
      ```

   * En Solaris:

      ```
      unzip -d installationFilename.tar.gz 
       tar -xf installationFilename.tar
      ```

1. Copie los archivos de programa no empaquetados en los directorios identificados en la siguiente tabla:

<table id="table_A97CF630633C4543A742D96C302D1138"> 
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
   <td colname="col2"> El módulo de carga del recolector </td> 
   <td colname="col3"> apachePath/libexec </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>txlogd </p> </td> 
   <td colname="col2"> El programa transmisor </td> 
   <td colname="col3"> <p>/usr/local/bin </p> <p>--OR-- </p> <p>/usr/local/sbin </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> txlogd.conf </td> 
   <td colname="col2"> El archivo de configuración del sensor </td> 
   <td colname="col3"> /etc </td> 
  </tr> 
  <tr> 
   <td colname="col1"> trust_ca_cert.pem </td> 
   <td colname="col2"> Certificado utilizado para validar el certificado digital que presenta Insight Server durante el proceso de conexión </td> 
   <td colname="col3"> /usr/local/visual_sciences </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>El paquete de instalación contiene un archivo de hoja de cálculo denominado TestExperiment.xls. Esta hoja de cálculo es una herramienta que los arquitectos utilizan para configurar un experimento controlado. El propio sensor no utiliza este archivo, por lo que no es necesario instalar el archivo en el equipo en el que se está ejecutando Sensor (aunque puede elegir hacerlo). En su lugar, puede que desee copiar el archivo en una ubicación en la que sus arquitectos puedan acceder a él o simplemente extraer el archivo del paquete de instalación según sea necesario. Para obtener más información sobre la experimentación controlada, consulte la Guía de experimentos controlados con perspectiva.

**Permisos en los archivos de programa**

Los permisos incorrectos en los archivos de programa causan la mayoría de los problemas encontrados al instalar Sensor.

Asegúrese de establecer los permisos exactamente como se indica en esta sección.

De forma predeterminada, los archivos de programa del archivo tar tienen los siguientes permisos. Según la configuración del sistema, esta configuración se puede modificar (desenmascarar) al extraer los archivos. Para restablecer los permisos a la configuración predeterminada recomendada, utilice los comandos chmod que se indican a continuación. Compruebe que los directorios en los que ha instalado los archivos permiten al menos este nivel de acceso.

| Archivo | Permisos predeterminados | chmod, comando |
|---|---|---|
| mod_visual_sciences.so | rwx r-x r-x | chmod 755 |
| txlogd | rwx —x —x | chmod 711 |
| txlogd.conf | rw- rw- | chmod 664 |
| trust_ca_cert.pem | rw- rw- | chmod 664 |

## Edición del archivo de configuración del sensor {#section-3f22a1c91d7d43b6b4c30f1b7448b17f}

La variable [!DNL txlogd.conf] contiene los parámetros de configuración para Sensor.

Debe editar el archivo para especificar, entre otras cosas, el tamaño de la cola de disco, la dirección de Insight Server y el ID que se adjuntará a los datos producidos por este sensor.

El archivo de configuración contiene los parámetros necesarios y los parámetros opcionales.

* Los parámetros requeridos son configuraciones que debe especificar al instalar Sensor. Sin estos ajustes, el sensor no se ejecuta correctamente.
* Los parámetros opcionales son configuraciones que se establecen de forma predeterminada en valores predefinidos (que puede modificar) o que habilitan funciones opcionales.

Para editar el archivo de configuración del sensor

1. Abra el archivo /etc/txlogd.conf en un editor de texto y establezca los parámetros necesarios, así como los parámetros opcionales que desee.
1. Guarde y cierre el archivo.

## Inicie el transmisor y cree la cola de disco {#section-a453d912ec3d47aa8e40ccacf527119d}

Instrucciones para crear la cola de discos después de configurar el archivo txlogd.conf.

1. Si el directorio en el que reside la cola de discos no existe, créelo. Asegúrese de que el directorio proporciona acceso de lectura/escritura al archivo tanto al módulo del recolector como al programa del transmisor.
1. En el equipo en el que está instalado Sensor, ejecute el siguiente comando para iniciar el transmisor:

   ```
   /usr/local/bin/txlogd -ic -f /etc/txlogd.conf
   ```

   * La opción &quot;i&quot; de este comando inicia el transmisor en modo interactivo. Este modo muestra los mensajes del transmisor en la pantalla y también le permite interactuar con el transmisor mediante comandos de teclado.
   * La opción &quot;c&quot; indica al transmisor que cree la cola de discos.
   * La opción &quot;f&quot; especifica la ubicación del archivo de configuración.

1. Compruebe que el transmisor ha creado la cola de discos en la ubicación especificada en el parámetro QueueFile y del tamaño especificado en el parámetro QueueSize.
1. Si la cola no se ha creado correctamente, escriba Ctrl+C para finalizar el transmisor y haga lo siguiente:

   1. Examine el archivo txtlogd.conf y verifique que los parámetros QueueFile y QueueSize estén correctamente configurados.
   1. Compruebe que el dispositivo al que está asignada la cola de disco funciona y que tiene suficiente espacio disponible para guardar un archivo del tamaño especificado en el parámetro QueueSize.
   1. Realice las correcciones necesarias y repita este procedimiento.

## Agregar el recopilador al servidor web {#section-a7fb6425956f4f518ae3a7db091b33d2}

Para los servidores Apache, el recolector es un objeto compartido dinámico que se carga en el proceso del servidor web.

Para agregar el recolector al servidor web, debe editar el archivo httpd.conf como se describe a continuación y reiniciar el servidor web.

Si Sensor está capturando datos de varios servidores web en el equipo servidor, debe realizar el siguiente procedimiento para cada servidor web.

1. Con un editor de texto, abra el [!DNL httpd.conf] para el servidor web cuyos eventos captura Sensor.
1. Añada las siguientes líneas al final del archivo:

   ```
   LoadModule  visual_sciences_module  libexec/mod_visual_sciences.so 
   VisualSciencesConfig  /etc/txlogd.conf 
   AddModule mod_visual_sciences.c
   ```

   >[!NOTE]
   >
   >Estas líneas distinguen entre mayúsculas y minúsculas. Escriba exactamente como aparecen arriba.

1. Reinicie el servidor web. El recolector se carga con el servidor web y comienza a recopilar datos de evento y a escribirlos en la cola de disco.

## Comprobación del sensor {#section-83d9f60b39a6474f9c76bee3e19b2575}

Inicie el transmisor y verifique que se pueda conectar correctamente al servidor de Insight y le transmita datos de evento.

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
   * La variable [!DNL ServerAddress] y [!DNL ServerPort] los parámetros están correctamente configurados en [!DNL txtlogd.conf].

   * Si ha especificado [!DNL ServerAddress] con un nombre de servidor, intente usar su dirección IP numérica en su lugar. El valor de la variable [!DNL CertName] coincide exactamente con el nombre común que aparece en el certificado digital de destinatario de Insight Server.

## Agregar el transmisor al script de inicio del sistema {#section-4e1ffa6e043941ab91411d91d596477a}

Información para garantizar que el transmisor se cargue automáticamente cuando se reinicie el equipo del servidor web.

Agregue el siguiente comando (que inicia el transmisor) al script de inicio del sistema.

```
/usr/local/bin/txlogd -f /etc/txlogd.conf
```

Este comando inicia el transmisor como un demonio. Los mensajes de funcionamiento y de error que genera el transmisor se escriben en syslog.

>[!NOTE]
>
>Algunos usuarios de Solaris pueden encontrar el error &quot;no se puede adquirir mutex&quot;. Para que Sensor funcione correctamente en estos sistemas, es necesario añadir o editar la siguiente línea en el archivo /etc/system:
>
>
```
>semsys:seminfo_semmnu=1024
>```
>
>La configuración predeterminada de Solaris es 60. En función de las pruebas realizadas con Sensor, que utiliza tres semáforos para cada caso, Adobe recomienda usar 1024 como configuración. Este número es lo suficientemente alto como para que Sensor funcione junto con cualquier otra aplicación del servidor que pueda requerir semáforos, pero que no afecte al rendimiento. Para apoyar esta recomendación, tenga en cuenta que Adrian Cockcroft declaró lo siguiente en su libro Sun Performance and Tuning (Prentice Hall, octubre de 1994): &quot;Las bases de datos tienden a utilizar muchos ajustes de memoria compartida y de semáforo. No afectan al rendimiento; mientras sean lo suficientemente grandes, los programas se ejecutarán&quot;.
