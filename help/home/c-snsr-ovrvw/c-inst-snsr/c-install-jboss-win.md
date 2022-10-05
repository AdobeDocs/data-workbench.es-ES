---
description: Instrucciones detalladas para instalar y configurar Sensor para JBoss Server 4.0.5 o posterior que se ejecuta en Microsoft Windows Server 2000 o posterior.
title: JBoss Server en Windows Server 2000 o posterior
uuid: b0501749-9479-484b-8876-fe3001825f8d
exl-id: d9001bc4-f3ef-4d26-9190-807194d20ada
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '1190'
ht-degree: 1%

---

# JBoss Server en Windows Server 2000 o posterior{#jboss-server-on-windows-server-or-later}

{{eol}}

Instrucciones detalladas para instalar y configurar Sensor para JBoss Server 4.0.5 o posterior que se ejecuta en Microsoft Windows Server 2000 o posterior.

Los archivos de programa para Sensor están empaquetados en un archivo de instalación que usted obtiene del sitio de descarga de Adobe. Si todavía no tiene el archivo de instalación Sensor para su servidor web en particular, descárguelo (u obtenga el archivo de su representante de Adobe) antes de iniciar los siguientes procedimientos.

Las implementaciones J2EE compatibles incluyen:

* JBoss Server 4.0.5 o posterior que se ejecuta en Microsoft Windows Server 2000 o posterior.

Para instalar y configurar Sensor, debe realizar los siguientes pasos:

## Instalación de los archivos de programa {#section-2f3e85083b4f4aa989a85997330e86ae}

Procedimiento para extraer e instalar los archivos de programa del sensor.

1. En el servidor JBoss, cree un directorio en el que instalar los archivos de programa Sensor. Tenga en cuenta que la cola de disco reside en este directorio, por lo que asegúrese de que el dispositivo que elija tenga espacio suficiente para guardar una cola del tamaño que necesita.

   ```
   C:\VisualSensor
   ```

1. Extraiga el contenido del archivo de instalación en el directorio que acaba de crear. Durante este paso, Sensor instala los siguientes archivos:

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
>El paquete de instalación contiene un archivo de hoja de cálculo llamado [!DNL TestExperiment.xls]. Esta hoja de cálculo es una herramienta que los arquitectos utilizan para configurar un experimento controlado. El propio sensor no utiliza este archivo, por lo que no es necesario instalar el archivo en el equipo en el que se está ejecutando Sensor (aunque puede elegir hacerlo). En su lugar, puede que desee copiar el archivo en una ubicación en la que sus arquitectos puedan acceder a él o simplemente extraer el archivo del paquete de instalación según sea necesario. Para obtener más información sobre la experimentación controlada, consulte la Guía de experimentos controlados con perspectiva.

## Edición del archivo de configuración del sensor {#section-2e2f1875a5304cdfa2cbcd0680683cfd}

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

## Agregar el recopilador al servidor web {#section-c5b83ae4ebce430aa764f951e849b333}

Para los servidores JBoss, el recolector funciona como un filtro en el contenedor de servlets.

Para añadir el selector al servidor web, debe editar la variable [!DNL web.xml] como se describe a continuación y reinicie la aplicación web.

1. Con un editor de texto, abra el [!DNL web.xml] para el servidor web cuyos eventos captura Sensor.
1. Agregue lo siguiente `<filter>` y `<filter-mapping>` al archivo descriptor. Si no instaló txlogd.conf en el directorio /etc, debe introducir la ruta correcta a este archivo en la `<param-value>` elemento:

   ```
   <filter>
     <filter-name>VSCollectorFilter</filter-name> 
     <description></description> 
     <filter-class> 
         com.visualsciences.collector.VSCollectorFilter 
       </filter-class> 
     <init-param> 
       <param-name>configPath</param-name> 
       <param-value>C:/VisualSensor/txlogd.conf</param-value> 
     <description></description> 
     </init-param> 
   </filter> 
   
   <filter-mapping> 
     <filter-name>VSCollectorFilter</filter-name> 
     <url-pattern>/*</url-pattern> 
   </filter-mapping> 
   ```

   >[!NOTE]
   >
   >Estas líneas distinguen entre mayúsculas y minúsculas. Escriba exactamente como aparecen arriba.

1. Reinicie el proceso del servidor web (no tiene que reiniciar el equipo servidor completo, simplemente reinicie el proceso del servidor web). El recolector se carga con el servidor web y comienza a recopilar datos de evento y a escribirlos en la cola de disco.

## Modificación del script de inicio {#section-0dae181ef8884f10a57f6cfda8500969}

Antes de modificar el script de inicio, asegúrese de que la variable JAVA_HOME está definida en el entorno de Windows.

En el [!DNL run.bat] (por ejemplo, C:\jboss-4.0.5.GA\bin\run.bat), agregue las siguientes líneas cerca del final del archivo justo antes de las líneas de &quot;eco&quot; que preceden al comando de inicio del servidor JBoss:

```
set JBOSS_CLASSPATH=%JBOSS_CLASSPATH%;C:\jboss-4.0.5.GA\server\default\lib\javax.servlet.jar;C:\VisualSciences\J2EECollector.jar 
set JAVA_OPTS=%JAVA_OPTS% -Djava.library.path=C:\VisualSciences
```

## Captura de datos adicionales {#section-9483b663cbd0432daaca50c1089c7fca}

Puede capturar datos de medición adicionales de aplicaciones web basadas en J2EE utilizando la funcionalidad appendToLog() .

1. Agregue el siguiente código a la parte superior de la página .jsp desde la que desee capturar datos:

   ```
   <%@ page import="com.visualsciences.collector.VSCollector" %> 
   ```

1. Utilice el método appendToLog() del objeto recolector para anexar los pares nombre-valor deseados a la cadena de consulta de la página .jsp solicitada. El siguiente ejemplo añade &quot;A=1&quot; y &quot;B=2&quot; a la cadena de consulta de la página .jsp solicitada para la página /index.jsp:

   ```
   <html> 
   <body> 
     <h1>Hello World</h1> 
     <% 
       VSCollector collector = new VSCollector(request, response); 
       collector.appendToLog("A", "1"); 
       collector.appendToLog("B", "2"); 
     %> 
   </body> 
   </html> 
   ```

   El URI de solicitud resultante es /index.jsp?A=1&amp;B=2.

1. Repita este procedimiento para cada página .jsp desde la que desee capturar datos adicionales.
