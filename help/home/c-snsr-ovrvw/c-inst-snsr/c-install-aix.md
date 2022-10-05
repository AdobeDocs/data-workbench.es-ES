---
description: Instrucciones sobre cómo instalar y configurar el servidor HTTP de IBM en IBM AIX 5.1 o posterior que se ejecute en Microsoft Windows Server 2000 o posterior.
title: Servidor HTTP IBM en AIX 5.1 o posterior
uuid: d4a37ab2-514a-4afb-905b-420159c4ef0a
exl-id: 1d0c3aa9-de2d-45c0-b52d-b6e3fd4fd453
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '1764'
ht-degree: 1%

---

# Servidor HTTP IBM en AIX 5.1 o posterior{#ibm-http-server-on-aix-or-later}

{{eol}}

Instrucciones sobre cómo instalar y configurar el servidor HTTP de IBM en IBM AIX 5.1 o posterior que se ejecute en Microsoft Windows Server 2000 o posterior.

Los archivos de programa para Sensor están empaquetados en un archivo de instalación que usted obtiene del sitio de descarga de Adobe. Si todavía no tiene el archivo de instalación Sensor para su servidor web en particular, descárguelo (u obtenga el archivo de su representante de Adobe) antes de iniciar los siguientes procedimientos.

Para instalar y configurar Sensor, debe realizar los siguientes pasos de alto nivel:

## Instalación de los archivos de programa {#section-2f3e85083b4f4aa989a85997330e86ae}

En su servidor IBM AIX, cree un directorio en el que instalar los archivos de programa Sensor. Tenga en cuenta que la cola de discos también reside en este directorio, por lo que asegúrese de que el dispositivo que elija tenga espacio suficiente para guardar una cola del tamaño que necesita.

1. Inicie sesión como usuario raíz o como usuario con autoridad raíz.
1. Descomprima y descomprima el archivo de instalación utilizando el siguiente comando:

   ```
   tar -zxf installationFilename
   ```

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

<table id="table_F4A46DBDE0874133B616235C32B6D9F8"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Archivo </th> 
   <th colname="col2" class="entry"> Permisos predeterminados </th> 
   <th colname="col3" class="entry"> chmod, comando </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> libvisual_sciences.so </td> 
   <td colname="col2"> rwx —x —x </td> 
   <td colname="col3"> <p>chmod 711 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> J2EECollector.jar </td> 
   <td colname="col2"> rw- rw- </td> 
   <td colname="col3"> chmod 664 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> txlogd </td> 
   <td colname="col2"> rwx —x —x </td> 
   <td colname="col3"> chmod 711 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> txlogd.conf </td> 
   <td colname="col2"> rw- rw- </td> 
   <td colname="col3"> chmod 664 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> trust_ca_cert.pem </td> 
   <td colname="col2"> rw- rw- </td> 
   <td colname="col3"> chmod 664 </td> 
  </tr> 
 </tbody> 
</table>

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

## Agregar el recopilador a la aplicación web {#section-c5b83ae4ebce430aa764f951e849b333}

Para los servidores WebSphere, el recolector funciona como un filtro en el contenedor servlet.

Para agregar el selector a la aplicación web, abra el archivo web.xml del servidor web cuyos eventos captura Sensor.

Si Sensor está capturando datos de varios servidores web en el equipo servidor, debe realizar el siguiente procedimiento para cada servidor web.

1. Con un editor de texto, abra el archivo httpd.conf del servidor web cuyos eventos captura Sensor.
1. Agregue lo siguiente `<filter>` y `<filter-mapping>` al archivo descriptor. Si no instaló txlogd.conf en el directorio /etc, debe introducir la ruta correcta a este archivo en la `<param-value>` elemento.

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

1. Reinicie la aplicación web. El recolector se carga con la aplicación y comienza a recopilar datos de evento y a escribirlos en la cola de disco.

## Declarar la ubicación del recopilador y los archivos de objeto compartido {#section-b9c298fa645f4670b2503647d967846f}

Edite el script de inicio de Websphere para declarar la ubicación de los archivos J2EECollector.jar y libvisual_sciences.so .

1. Abra el archivo setupCmdLine.sh en el directorio Websphere /bin.
1. Después de la línea que define la variable $WAS_CLASSPATH, agregue la línea siguiente:

   ```
   WAS_CLASSPATH="$WAS_CLASSPATH":"$WAS_HOME"/lib/J2EECollector.jar
   ```

1. Después del bloque de mayúsculas y minúsculas que define la variable $WAS_LIBPATH, agregue la línea siguiente:

   ```
   WAS_LIBPATH="$WAS_LIBPATH":/usr/local/visual_sciences
   ```

1. Guarde el archivo setupCmdLine.sh .

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

## Captura de datos adicionales {#section-bb1c2bccba9b4bc0b52abdbb4f9d42d7}

Los sensores de todas las plataformas pueden recopilar cualquiera de los datos disponibles en los encabezados de solicitud y respuesta HTTP.

Los sensores de la plataforma J2EE proporcionan un mecanismo para recopilar datos que no están disponibles en otras plataformas. El recolector para la plataforma J2EE (recolector J2EE) se encuentra en la capa de la aplicación, lo que le permite recopilar datos confidenciales que solo están disponibles para la aplicación y que no deben exponerse mediante el etiquetado de páginas o en los encabezados.

>[!NOTE]
>
>Aunque las etiquetas de página y la modificación del encabezado pueden ocultar los datos, siguen estando disponibles para quienes examinan el código fuente de una página o miran los encabezados con las herramientas del complemento del navegador.

Por ejemplo, el recolector J2EE se puede utilizar para capturar datos de costo por clic (CPC) para vínculos mostrados en una página, información confidencial de socios en una página y muchos otros puntos de datos. El entorno J2EE le facilita la modificación de su WEBAPP para capturar estos datos personalizados con nuestra clase recopiladora.

Cuando un sensor para la plataforma J2EE recibe una solicitud, invoca una clase de recolector que importa la función appendToLog . La función appendToLog adjunta a la solicitud inicial los parámetros de cadena de consulta especificados en la función appendToLog. Esto da como resultado el URI de la solicitud inicial que contiene pares de nombre-valor de cadena de consulta adicionales que corresponden a los nombres y valores de los datos que se están capturando. Por ejemplo, CPC=20 se anexaría a la solicitud inicial cuando el valor de una ubicación de publicidad o vínculo de pulsación en particular sea de 20 centavos. Insight Server procesa estos valores en el conjunto de datos para su análisis. Una ventaja adicional de esta metodología de recopilación es que permite la recopilación de datos adicionales sin crear entradas de registro adicionales, ya que se pueden crear mediante metodologías de etiquetado de páginas.

Para obtener más información sobre el procesamiento, consulte la Guía de configuración de conjuntos de datos.

Para capturar datos adicionales de una página:

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
