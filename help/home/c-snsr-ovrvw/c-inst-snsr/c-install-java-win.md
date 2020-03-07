---
description: Instrucciones para instalar y configurar Sensor para Sun Java System Application Server Standard Edition 7 que se ejecuta en Windows Server 2000 o posterior.
title: Sun Java Server en Windows Server 2000 o posterior
uuid: 43f3eee0-2633-4bda-af6c-6c15433dd539
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Sun Java Server en Windows Server 2000 o posterior{#sun-java-server-on-windows-server-or-later}

Instrucciones para instalar y configurar Sensor para Sun Java System Application Server Standard Edition 7 que se ejecuta en Windows Server 2000 o posterior.

Los archivos de programa para Sensor se empaquetan en un archivo de instalación que se obtiene del sitio de descarga de Adobe. Si aún no dispone del archivo de instalación de Sensor para su servidor web en particular, descárguelo (o consiga el archivo a su representante de Adobe) antes de comenzar los siguientes procedimientos.

Sensor admite los siguientes servidores que se ejecutan en RedHat Linux 7.x o posterior o Sun Solaris SPARC 2.6 o posterior:

Para instalar y configurar Sensor, debe realizar los siguientes pasos:

## Instalación de los archivos de programa {#section-2f3e85083b4f4aa989a85997330e86ae}

Procedimiento para extraer e instalar los archivos de programa para Sensor en el servidor.

1. En Netscape Enterprise, iPlanet, Sun ONE o Sun Java System Server, cree un directorio en el que instalar los archivos de programa de Sensor. Tenga en cuenta que la cola de discos reside en este directorio, por lo que asegúrese de que el dispositivo que elija tenga espacio suficiente para mantener una cola del tamaño que necesita.

   ```
   C:\VisualSensor
   ```

1. Extraiga el contenido del archivo de instalación en el directorio que acaba de crear. Durante este paso, Sensor instala los siguientes archivos:

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
   <td colname="col1"> saf_visual_sciences.dll </td> 
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

1. En el menú Inicio de Windows, seleccione Accesorios > Símbolo del sistema.
1. En la ventana del símbolo del sistema, navegue al directorio en el que instaló Sensor y ejecute el siguiente comando:

   ```
   txlog /regserver
   ```

   Este comando inicia el transmisor, crea la cola de discos y registra Sensor como un servicio de Windows.

1. Para confirmar que el transmisor se está ejecutando correctamente, haga clic en Inicio > Panel de control > Herramientas administrativas > Servicios. En la lista de servicios, busque la entrada para Sensor y confirme que su estado es Iniciado y que su tipo de inicio es Automático. A continuación, cierre el panel de control Servicios.
1. Para comprobar si el transmisor ha experimentado algún error durante el inicio, haga clic en Inicio > Panel de control > Herramientas administrativas > Visor de eventos para abrir el Visor de eventos.

   1. En el panel izquierdo de la ventana Visor de eventos, seleccione el registro de aplicaciones.
   1. En el panel derecho, busque eventos con &quot;Adobe&quot; en la columna Origen.
   1. Si encuentra un error de &quot;Adobe&quot;, haga doble clic en el error para mostrar la ventana Propiedades del evento. Esta ventana proporciona información detallada sobre el error.

1. Cuando termine de examinar el registro de aplicaciones, cierre el visor de eventos.
1. Compruebe que el transmisor ha creado la cola de discos (Diskq2000.log) en el directorio en el que instaló los archivos del programa Sensor y que es el tamaño especificado en el parámetro QueueSize en el archivo txlogd.conf.

   Si la cola no se ha creado correctamente:

   1. Examine el archivo txtlogd.conf y verifique que el parámetro QueueSize esté configurado correctamente.
   1. Compruebe que el dispositivo en el que instaló Sensor tiene suficiente espacio disponible para guardar un archivo del tamaño especificado en el parámetro QueueSize.
   1. Con el panel de control Servicios en Windows, detenga el transmisor.
   1. Elimine el archivo de cola.
   1. Volver a registrar Sensor como un servicio de Windows: en el menú Inicio de Windows, seleccione Accesorios > Símbolo del sistema. En la ventana del símbolo del sistema, navegue al directorio en el que instaló Sensor y ejecute el siguiente comando:

      ```
      txlog /regserver
      ```

El transmisor está diseñado para funcionar continuamente. Si reinicia la máquina, el transmisor se reinicia automáticamente. Si necesita iniciar y detener el transmisor manualmente, puede hacerlo mediante el panel de control Servicios de Windows.

## Modificación de la secuencia de comandos de inicio {#section-19a38f27c9f44adf88f8910f5ed483a3}

En el archivo init.conf (por ejemplo, C:\Sun\AppServer7\domains\domain1\server1\config\ init.conf), agregue las siguientes líneas al final del archivo:

```
Init fn="load-modules" shlib="C:/VisualSciences/saf_visual_sciences.dll" 
funcs="vys-cookie,vys-log,vys-init,vys-content-type" 
Init fn="vys-init" config-file="C:/VisualSciences/txlogd.conf"
```

En el archivo obj.conf (por ejemplo, C:\Sun\AppServer7\domains\domain1\server1\config\ server1-obj.conf), agregue las siguientes líneas directamente debajo de la línea &quot;<Object name="default">&quot; existente:

```
NameTrans fn="vys-cookie" 
ObjectType fn="vys-content-type" 
AddLog fn="vys-log"
```

