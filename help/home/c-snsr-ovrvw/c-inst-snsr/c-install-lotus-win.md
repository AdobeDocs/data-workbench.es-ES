---
description: Instrucciones sobre cómo instalar y configurar Sensor para Lotus Sametime para Windows 3.1 o posterior que se ejecuta en Microsoft Windows Server 2000 o posterior.
title: Lotus Sametime en Windows Server 2000 o posterior
uuid: 5e24da54-7ef6-42cf-b693-cc4fd267af93
exl-id: 9292bfca-ad3b-436d-9d22-be67a61b8c05
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '1023'
ht-degree: 1%

---

# Lotus Sametime en Windows Server 2000 o posterior{#lotus-sametime-on-windows-server-or-later}

{{eol}}

Instrucciones sobre cómo instalar y configurar Sensor para Lotus Sametime para Windows 3.1 o posterior que se ejecuta en Microsoft Windows Server 2000 o posterior.

Los archivos de programa para Sensor están empaquetados en un archivo de instalación que usted obtiene del sitio de descarga de Adobe. Si todavía no tiene el archivo de instalación Sensor para su servidor web en particular, descárguelo (u obtenga el archivo de su representante de Adobe) antes de iniciar los siguientes procedimientos.

Para instalar y configurar Sensor, debe realizar los siguientes pasos de alto nivel:

## Instalación de los archivos de programa {#section-2f3e85083b4f4aa989a85997330e86ae}

Al ejecutar Sensor en Sametime, los archivos de programa y el archivo de la cola de discos deben residir en el mismo directorio.

Por lo tanto, antes de instalar los archivos de programa, debe determinar dónde desea mantener la cola de disco, ya que también es allí donde debe instalar los archivos de programa.

Utilice el siguiente procedimiento para extraer e instalar los archivos de programa para Sensor.

1. Detenga Lotus Domino Server y el servicio de Registro de Chat Sametime.
1. En el equipo Windows, en el directorio Lotus Domino, elimine o haga una copia de seguridad del archivo llamado StChatLog.dll.
1. Extraiga el contenido del archivo de instalación en el directorio Lotus Domino. Durante este paso, Sensor instala los siguientes archivos:

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
   <td colname="col2"> Mensajes del visualizador de eventos </td> 
  </tr> 
  <tr> 
   <td colname="col1"> stchatlog.dll </td> 
   <td colname="col2"> Módulo de recolector </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>TestExperiment.xls </p> </td> 
   <td colname="col2"> <p>Archivo de hoja de cálculo de Excel que los arquitectos pueden utilizar para configurar un experimento controlado </p> <p>El sensor no utiliza este archivo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> trust_ca_cert.pem </td> 
   <td colname="col2"> Certificado utilizado para validar el certificado digital que presenta Insight Server durante el proceso de conexión </td> 
  </tr> 
  <tr> 
   <td colname="col1"> TXLog.exe </td> 
   <td colname="col2"> El programa transmisor </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>txlogd.conf </p> </td> 
   <td colname="col2"> El archivo de configuración del sensor </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>El paquete de instalación contiene un archivo de hoja de cálculo denominado TestExperiment.xls. Esta hoja de cálculo es una herramienta que los arquitectos utilizan para configurar un experimento controlado. El propio sensor no utiliza este archivo, por lo que no es necesario instalar el archivo en el equipo en el que se está ejecutando Sensor (aunque puede elegir hacerlo). En su lugar, puede que desee copiar el archivo en una ubicación en la que sus arquitectos puedan acceder a él o simplemente extraer el archivo del paquete de instalación según sea necesario. Para obtener más información sobre la experimentación controlada, consulte la Guía de experimentos controlados con perspectiva.

## Habilitar el inicio de sesión en el mismo servidor {#section-2e2f1875a5304cdfa2cbcd0680683cfd}

Pasos que le permiten iniciar sesión en el servidor de Sametime.

1. Utilice el cliente administrador de Lotus Domino para conectarse al servidor de Lotus Domino que ejecuta Sametime.
1. En Lotus Domino Administrator, haga clic en la ficha Archivos y, a continuación, haga doble clic en Sametime Configuration - stconfig.nsf para abrir el archivo de configuración de Sametime.
1. En el archivo de configuración de la misma hora, abra el formulario Servicios de la comunidad y haga doble clic en cualquier lugar del formulario para entrar en el modo de edición.
1. Establezca el indicador de registro de chat en &quot;estricto&quot; y Capture Service Type en &quot;0x1000&quot;.
1. Guarde y cierre el formulario de Servicios de comunidad y, a continuación, cierre el archivo de Configuración de la misma hora.
1. Reinicie el servidor Sametime.

## Edición del archivo de configuración del sensor {#section-de0eb4a646394b61abb6cd5a2b706de0}

El archivo txlogd.conf contiene los parámetros de configuración para Sensor.

Debe editar este archivo para especificar, entre otras cosas, el tamaño y la ubicación del archivo de cola de disco, la dirección del servidor de Insight y el ID que se adjuntará a los datos de evento producidos por este sensor.

El archivo de configuración contiene los parámetros necesarios y los parámetros opcionales.

* **Parámetros necesarios** son ajustes que debe especificar al instalar Sensor. Sin estos ajustes, el sensor no se ejecuta correctamente.
* **Parámetros opcionales** son configuraciones que se establecen de forma predeterminada en valores predefinidos (que puede modificar) o habilitar funciones opcionales.

**Para editar el archivo de configuración del sensor**

* Abra el `<Sensor directory>/txlogd.conf` en un editor de texto y establezca los parámetros necesarios, así como los parámetros opcionales que desee.
* Guarde y cierre el archivo.

## Inicie el transmisor y cree la cola de disco {#section-55630de65f264274aefd771da2002852}

Después de configurar el archivo txlogd.conf, puede iniciar el programa del transmisor, registrarlo como un servicio de Windows y crear la cola de discos.

1. En el menú Inicio de Windows, seleccione Accesorios > Símbolo del sistema.
1. En la ventana del símbolo del sistema, vaya al directorio en el que instaló Sensor y ejecute el siguiente comando:

   ```
   txlog /regserver
   ```

   Este comando inicia el transmisor, crea la cola de discos y registra Sensor como un servicio de Windows.

1. Para confirmar que el transmisor se está ejecutando correctamente, haga clic en Inicio > Panel de control de Campaign > Herramientas administrativas > Servicios.

   >[!NOTE]
   >
   >Esta secuencia de comandos puede variar en función de la versión de Windows que utilice.

   1. En la lista de servicios, localice la entrada para Sensor y confirme que su estado es Started y que su tipo de inicio es Automatic.
   1. Cierre el panel de control de Servicios.

1. Para comprobar si el transmisor ha experimentado algún error durante el inicio, haga clic en Inicio > Panel de control de Campaign > Herramientas administrativas > Visor de eventos para abrir el Visor de eventos.

   >[!NOTE]
   >
   >Esta secuencia de comandos puede variar en función de la versión de Windows que utilice.

   1. En el panel izquierdo de la ventana Visor de eventos, seleccione el registro Aplicaciones .
   1. En el panel derecho, busque eventos con &quot;Adobe&quot; en la columna Origen.
   1. Si encuentra un error de &quot;Adobe&quot;, haga doble clic en el error para mostrar la ventana Propiedades del evento. Esta ventana proporciona información detallada sobre el error.

1. Cuando termine de examinar el registro de aplicaciones, cierre el Visor de eventos.
1. Compruebe que el transmisor ha creado la cola de discos (Diskq2000.log) en el directorio donde instaló los archivos de programa Sensor y que es el tamaño especificado en el parámetro QueueSize del archivo txlogd.conf.

   Si la cola no se ha creado correctamente:

   1. Examine el archivo txtlogd.conf y verifique que el parámetro QueueSize esté configurado correctamente.
   1. Compruebe que el dispositivo en el que instaló el sensor tiene suficiente espacio disponible para guardar un archivo del tamaño especificado en el parámetro QueueSize.
   1. Con el panel de control de Servicios en Windows, detenga el transmisor.
   1. Elimine el archivo de cola.
   1. Vuelva a registrar Sensor como un servicio de Windows: en el menú Inicio de Windows, seleccione Accesorios > Símbolo del sistema. En la ventana del símbolo del sistema, vaya al directorio en el que instaló Sensor y ejecute el siguiente comando:

      ```
      txlog /regserver
      ```

      El transmisor está diseñado para funcionar continuamente. Si reinicia la máquina, el transmisor se reinicia automáticamente. Si necesita iniciar y detener el transmisor manualmente, puede hacerlo usando el panel de control de Servicios en Windows.

1. Reinicie Lotus Domino Server y el servicio de Registro de Chat Sametime.
