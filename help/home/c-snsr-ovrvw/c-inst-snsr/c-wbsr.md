---
description: Instrucciones detalladas para instalar y configurar Sensor para WebSphere 5.x con AIX 5.1 o posterior.
solution: Insight
title: WebSphere en AIX
uuid: a5a3fd79-a7f0-4861-adca-8da3a185d0df
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# WebSphere en AIX{#websphere-on-aix}

Instrucciones detalladas para instalar y configurar Sensor para WebSphere 5.x con AIX 5.1 o posterior.

Los archivos de programa para [!DNL Sensor] se empaquetan en un archivo de instalación que se obtiene del sitio de descarga de Adobe. Si aún no dispone del archivo de [!DNL Sensor] instalación de su servidor web en particular, descárguelo (o bien, descárguelo de su representante de Adobe) antes de iniciar los procedimientos siguientes.

>[!NOTE]
>
>El [!DNL Sensor] para servidores WebSphere no admite experimentación controlada. Para obtener información sobre la experimentación controlada, consulte la Guía de experimentos controlados *de Área de trabajo de datos.*

## Instalación de los archivos de programa {#section-86f69127278c41bc90b97b68bb40bc6e}

Procedimiento para extraer e instalar los archivos de programa para Sensorto en el equipo servidor.

1. Inicie sesión como usuario raíz o como usuario con autoridad raíz.
1. Descomprima y descomprima el archivo de instalación con el siguiente comando:

   ```
   gunzip installationFilename.tar.gz 
   tar -xf installationFilename.tar
   ```

1. Copie los archivos de programa sin empaquetar en los directorios identificados en la siguiente tabla:

<table id="table_0E3B403071EF44AFBF0DD673EFEBBFE5"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Archivo </th> 
   <th colname="col2" class="entry"> Descripción </th> 
   <th colname="col3" class="entry"> Directorio de objetivos </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> libvisual_sciences.so </td> 
   <td colname="col2"> El módulo de carga del selector </td> 
   <td colname="col3"> /usr/local/visual_sciences </td> 
  </tr> 
  <tr> 
   <td colname="col1"> J2EECollector.jar </td> 
   <td colname="col2"> Bibliotecas de módulos de carga de recopiladores </td> 
   <td colname="col3"> Directorio WebSphere /lib </td> 
  </tr> 
  <tr> 
   <td colname="col1"> txlogd </td> 
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

De forma predeterminada, los archivos de programa del archivo tar tienen los siguientes permisos. Según la configuración del sistema, esta configuración se puede modificar (sin máscara) al extraer los archivos.

Para restablecer los permisos a la configuración predeterminada recomendada, utilice los comandos chmod siguientes.

>[!NOTE]
>
>Compruebe que los directorios en los que ha instalado los archivos permiten al menos este nivel de acceso.

| Archivo | Permisos predeterminados | chmod, comando |
|---|---|---|
| libvisual_sciences.so | rwx —x —x | chmod 711 |
| J2EECollector.jar | rw- rw- r— | chmod 664 |
| txlogd | rwx —x —x | chmod 711 |
| txlogd.conf | rw- rw- r— | chmod 664 |
| trust_ca_cert.pem | rw- rw- r— | chmod 664 |

Si desea utilizar permisos distintos de los predeterminados recomendados, consulte la información de Permisos de archivos de Sensor UNIX para asegurarse de comprender cómo se utilizan estos archivos.

## Editar el archivo de configuración del sensor {#section-283c8a92fa8841c1b6034e5f834ef4e7}

El archivo txlogd.conf contiene los parámetros de configuración para Sensor.

Debe editar el archivo para especificar, entre otras cosas, el tamaño de la cola de discos, la dirección del servidor de Insight y el ID que se adjuntará a los datos generados por este sensor.

El archivo de configuración contiene parámetros opcionales y parámetros requeridos.

* Los parámetros requeridos son configuraciones que debe especificar al instalar Sensor. Sin esta configuración, Sensor no se ejecuta correctamente.
* Los parámetros opcionales son valores predeterminados para valores predefinidos (que se pueden modificar) o para activar funciones opcionales.

**Para editar el archivo de configuración**

1. Abra el archivo /etc/txlogd.conf en un editor de texto y defina los parámetros requeridos, así como los parámetros opcionales que desee.
1. Guarde y cierre el archivo.

## Iniciar el transmisor y crear la cola de disco {#section-63285a2328604f20a2cb31b3d5cb80e6}

Procedimiento para crear la cola de discos, después de configurar el archivo txlogd.conf.

1. Si el directorio en el que reside la cola de discos no existe, créelo. Asegúrese de que el directorio proporciona acceso de lectura/escritura al archivo tanto al módulo del selector como al programa del transmisor.

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

## Agregar el recopilador a la aplicación Web {#section-d17297b1193f4e3cb150fb41f754ef12}

Para los servidores WebSphere, el selector funciona como un filtro en el contenedor servlet.

Para agregar el selector a la aplicación web, agregue el filtro al descriptor de implementación web.xml de la aplicación web y reinicie la aplicación web.

1. Con un editor de texto, abra el archivo web.xml para el servidor web cuyos eventos captura Sensor.
1. Agregue los siguientes `<filter>` y `<filter-mapping>` elementos al archivo descriptor. Si no instaló txlogd.conf en el directorio /etc, debe introducir la ruta correcta a este archivo en el `<param-value>` elemento .

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

1. Reinicie la aplicación web. El recopilador se carga con la aplicación y empezará a recopilar datos de eventos y a escribirlos en la cola de discos.

## Declaración de la ubicación del recopilador y los archivos de objeto compartidos {#section-e641f08999d34a648aaee2111b69ca25}

Procedimiento para editar el script de inicio de Websphere para declarar la ubicación de los archivos J2EECollector.jar y libvisual_sciences.so.

1. Abra el archivo setupCmdLine.sh en el directorio Websphere /bin.
1. Después de la línea que define la variable $WAS_CLASSPATH, agregue la línea siguiente:

   ```
   WAS_CLASSPATH="$WAS_CLASSPATH":"$WAS_HOME"/lib/J2EECollector.jar
   ```

1. Después del bloque de mayúsculas y minúsculas que define la variable $WAS_LIBPATH, agregue la línea siguiente:

   ```
   WAS_LIBPATH="$WAS_LIBPATH":/usr/local/visual_sciences
   ```

1. Save the [!DNL setupCmdLine.sh] file.

## Comprobación del sensor {#section-07f2da5c4caa46bf9dd1cb4ae4b61af5}

Procedimiento para iniciar el transmisor y comprobar que puede conectarse correctamente al servidor de Insight y transmitir datos de eventos al mismo.

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
   * Los parámetros ServerAddress y ServerPort se establecen correctamente en txtlogd.conf. Si especificó ServerAddress con un nombre de servidor, intente utilizar su dirección IP numérica en su lugar.
   * El valor del parámetro CertName coincide exactamente con el nombre común que aparece en el certificado digital del servidor de Insight de destino.

## Agregar el transmisor a la secuencia de comandos de inicio del sistema {#section-23bb905100d04f018af93873dd4d5f68}

Información para garantizar que el transmisor se carga automáticamente cuando se reinicia el equipo del servidor web.

Agregue el siguiente comando (que inicia el transmisor) a la secuencia de comandos de inicio del sistema.

```
/usr/local/bin/txlogd -f /etc/txlogd.conf
```

Este comando inicia el transmisor como un demonio. Los mensajes de funcionamiento y error que genera el transmisor se escriben en syslog.

## Captura de datos adicionales {#section-d5ccf8ee50914a87938e0c17480757e6}

Los sensores de todas las plataformas pueden recopilar cualquiera de los datos disponibles en los encabezados de solicitud y respuesta HTTP.

Los sensores de la plataforma J2EE proporcionan un mecanismo para recopilar datos que no están disponibles en otras plataformas. El selector de la plataforma J2EE (recopilador J2EE) se encuentra en la capa de la aplicación, lo que le permite recopilar datos confidenciales que solo están disponibles para la aplicación y que no deben exponerse a través del etiquetado de páginas o en los encabezados.

>[!NOTE]
>
>Aunque las etiquetas de página y la modificación del encabezado pueden ocultar los datos, siguen estando disponibles para quienes examinen el código fuente de una página o vean los encabezados con las herramientas del complemento del explorador.

Por ejemplo, el recopilador J2EE puede utilizarse para capturar datos de costo por clic (CPC) para los vínculos mostrados en una página, información confidencial de un socio en una página y muchos otros puntos de datos. El entorno J2EE le facilita la modificación de su WEBAPP para capturar estos datos personalizados con nuestra clase de recopilador.

Cuando un sensor para la plataforma J2EE recibe una solicitud, invoca una clase de selector que importa la función appendToLog. La función appendToLog anexa a la solicitud inicial los parámetros de cadena de consulta especificados en la función appendToLog. Esto resulta en el URI de la solicitud inicial que contiene pares de valor-nombre de cadena de consulta adicionales que corresponden a los nombres y valores de los datos que se están capturando. Por ejemplo, CPC=20 se anexaría a la solicitud inicial cuando el valor de una colocación de publicidad o un vínculo de pulsación en particular sea de 20 centavos. Insight Server procesa estos valores en el conjunto de datos para su análisis. Una ventaja adicional de esta metodología de recopilación es que permite la recopilación de datos adicionales sin crear entradas de registro adicionales, ya que se pueden crear mediante metodologías de etiquetado de páginas.

Para obtener más información sobre el procesamiento, consulte la Guía *de configuración de* Dataset.

1. Agregue el siguiente código a la parte superior de la página .jsp desde la que desea capturar los datos:

   ```
   <%@ page import="com.visualsciences.collector.VSCollector" %>
   ```

1. Utilice el método appendToLog() del objeto de recopilación para anexar los pares nombre-valor deseados a la cadena de consulta de la página .jsp solicitada. El siguiente ejemplo anexa &quot;A=1&quot; y &quot;B=2&quot; a la cadena de consulta de la página .jsp solicitada para la página /index.jsp:

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

