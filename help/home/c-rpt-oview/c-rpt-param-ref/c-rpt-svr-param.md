---
description: Información sobre los parámetros de Report Server.cfg.
title: Parámetros de Report Server.cfg
uuid: 506f30f7-c8c6-4580-8423-7da8d00b0d57
exl-id: 339e4219-ff4d-4df6-b45a-7144927a843b
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '1683'
ht-degree: 1%

---

# Parámetros de Report Server.cfg{#report-server-cfg-parameters}

{{eol}}

Información sobre los parámetros de Report Server.cfg.

El ejemplo [!DNL Report Server.cfg] mostrado en [Configuración de la conexión con el servidor de Insight](../../../home/c-rpt-oview/c-inst-rpt/t-config-conn-ins-svr.md#task-a3ca949c43244782b658fb4437fd724c) contiene solo los parámetros incluidos en la variable [!DNL Report Server.cfg] de forma predeterminada.

Si se pone en contacto con el servidor de licencias de Adobe a través de un servidor proxy, debe agregar el vector de licencias y sus parámetros al [!DNL Report Server.cfg]. A continuación se muestra un ejemplo de este vector y sus parámetros que puede utilizar un modelo para el vector de licencias:

```
Licensing = serverInfo:  
Proxy Address = string: ProxyIPAddress 
Proxy Password = string: ProxyPassword 
Proxy Port = int: ProxyPort 
Proxy User Name = string: ProxyUserName 
```

La tabla siguiente proporciona descripciones de la variable [!DNL Report Server.cfg] parámetros de archivo:

<table id="table_9DA4A3124A9D444CBB4CBFF6FA279A42"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parámetro </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Extensión de Excel </td> 
   <td colname="col2"> <p>Las extensiones de Excel compatibles son: </p> <p>Extensión de Excel = cadena: <span class="filepath"> .xlsx </span> </p> <p>Extensión de Excel = cadena: <span class="filepath"> .xls </span> (predeterminado) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Fuentes </td> 
   <td colname="col2"> <p>Opcional. Vector que enumera las fuentes que <span class="keyword"> Servidor de informes </span> debe utilizarse para procesar caracteres especiales unicode basados en UTF8. El número de fuentes de la lista es ilimitado. </p> <p>La primera fuente siempre debe ser la consola Lucida Sans. Si este parámetro no está incluido en la variable <span class="filepath"> Report Server.cfg </span> archivo, <span class="keyword"> Servidor de informes </span> utiliza solo la consola Lucida Sans para mostrar el texto. </p> <p> <span class="keyword"> Servidor de informes </span> utiliza la primera fuente de la lista para procesar todos los caracteres hasta que encuentre un carácter que no pueda procesar. A continuación, utiliza la segunda fuente de la lista para representar ese carácter. Si esa fuente no representa el carácter, <span class="keyword"> Servidor de informes </span> utiliza la tercera fuente de la lista para representar ese carácter, etc., hasta que llega al final de la lista de fuentes. Si la fuente correcta no aparece en la lista del vector, <span class="keyword"> Servidor de informes </span> muestra el valor hexadecimal del carácter. </p> <p> <p>Nota: No realice cambios en este parámetro mientras <span class="keyword"> Servidor de informes </span> se está ejecutando. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Gamma </td> 
   <td colname="col2"> <p> <span class="wintitle"> Gamma </span> configurar para <span class="filepath"> .png </span> salida del archivo. El valor predeterminado es 1.6. </p> <p> <p>Nota: Adobe no recomienda cambiar este valor. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Licencias </td> 
   <td colname="col2"> <p>Opcional. Solo es necesario modificar los parámetros de este vector si se pone en contacto con el servidor de licencias de Adobe a través de un servidor proxy. </p> <p>Identificador de sección para los parámetros que se establecen para ponerse en contacto con el servidor de licencias de Adobe a través de un servidor proxy. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Dirección proxy </td> 
   <td colname="col2"> La dirección de un servidor proxy que <span class="keyword"> Servidor de informes </span> debe utilizar para acceder al servidor de licencias de Adobe. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Contraseña de proxy </td> 
   <td colname="col2"> Opcional. La contraseña asociada a la variable <span class="wintitle"> Nombre de usuario proxy </span>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Puerto proxy </td> 
   <td colname="col2"> Puerto del servidor proxy. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Nombre de usuario proxy </td> 
   <td colname="col2"> Opcional. El nombre de usuario utilizado para acceder al servidor proxy. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Ubicación de red </td> 
   <td colname="col2"> La ubicación de red que <span class="keyword"> Servidor de informes </span> utiliza para resolver el nombre común del servidor en una dirección IP. Las ubicaciones de red se definen en el archivo de dirección ubicado en el directorio Direcciones del equipo de servidor de Data Workbench. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Servidores </td> 
   <td colname="col2"> <p>Identificador de sección para parámetros que se establecen para configurar qué máquinas del servidor de Data Workbench <span class="keyword"> Servidor de informes </span> debe conectarse para generar informes. Esto incluye un número que indica cuántos elementos están enumerados en este vector. </p> <p>Para cada servidor, agregue una entrada serverInfo y complete los parámetros según sea necesario. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Dirección </td> 
   <td colname="col2"> Dirección IP del equipo del servidor de Data Workbench al que <span class="keyword"> Servidor de informes </span> debe conectarse para generar informes. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Nombre </td> 
   <td colname="col2"> El nombre que <span class="keyword"> Servidor de informes </span> utiliza internamente para identificar el servidor de Data Workbench. Se trata simplemente de una etiqueta interna, por lo que puede utilizar cualquier nombre que desee. Para mantener la coherencia, le sugerimos que utilice el nombre común que aparece en el certificado digital del servidor. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Puerto </td> 
   <td colname="col2"> Puerto a través del cual <span class="keyword"> Servidor de informes </span> se comunica con el servidor de Data Workbench. Para conexiones seguras, este valor suele ser 443. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Dirección proxy </td> 
   <td colname="col2"> La dirección de un servidor proxy que <span class="keyword"> Servidor de informes </span> debe utilizar para acceder al servidor de Data Workbench. Este parámetro solo es necesario cuando se requiere un servidor proxy para conectarse a los equipos servidor. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Contraseña de proxy </td> 
   <td colname="col2"> La contraseña del servidor proxy. Este parámetro solo es necesario cuando se requiere un servidor proxy para conectarse a los equipos de servidor de Data Workbench. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Puerto proxy </td> 
   <td colname="col2"> Puerto del servidor proxy. El valor predeterminado es 8080. Este parámetro solo es necesario cuando se requiere un servidor proxy para conectarse a los equipos de servidor de Data Workbench. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Nombre de usuario proxy </td> 
   <td colname="col2"> El nombre de usuario del servidor proxy. Este parámetro solo es necesario cuando se requiere un servidor proxy para conectarse a los equipos de servidor de Data Workbench. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Certificado de cliente SSL </td> 
   <td colname="col2"> Nombre del archivo de certificado SSL para la variable <span class="keyword"> Servidor de informes </span> máquina. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Nombre común del servidor SSL </td> 
   <td colname="col2"> <span class="wintitle"> Nombre común del servidor </span> aparece en el certificado digital del servidor de Data Workbench. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Usar SSL </td> 
   <td colname="col2"> Indica si SSL se utiliza para la comunicación segura entre el servidor de Data Workbench y <span class="keyword"> Servidor de informes </span>. Las opciones son true o false. El valor predeterminado es true. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Límite de memoria de resultados (KB) </td> 
   <td colname="col2"> <p>Cantidad de memoria (en KB) que desea que esté disponible para informes y alertas. El valor predeterminado es 50000. </p> <p>Al ejecutar informes, <span class="keyword"> Servidor de informes </span> comprueba primero este valor y, a continuación, comprueba el valor en el parámetro Tamaño máximo de fracción . Por ejemplo, si establece este parámetro en 50 000 y el tamaño máximo de la fracción en 50, <span class="keyword"> Servidor de informes </span> ejecuta solo 50 espacios de trabajo a la vez, aunque haya espacio disponible para ejecutar más espacios de trabajo. </p> <p> <p>Nota: Este límite nunca debe superar el valor establecido en el parámetro de límite de memoria de consulta del servidor de Data Workbench y, idealmente, debe establecerse un valor un poco inferior al valor establecido en <span class="wintitle"> Límite de memoria de consulta </span> para proporcionar cierta libertad a otros usuarios que puedan estar ejecutando informes al mismo tiempo. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Tamaño máximo de fracción </td> 
   <td colname="col2"> El número máximo de espacios de trabajo de informes que <span class="keyword"> Servidor de informes </span> se puede ejecutar al mismo tiempo. El valor predeterminado es 50. Para obtener más información sobre cómo <span class="keyword"> Servidor de informes </span> utiliza esta configuración, consulte la <span class="wintitle"> Límite de memoria de resultados (KB) </span> descripción del parámetro. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Actualizar software </td> 
   <td colname="col2"> <p>Indica si se permite <span class="keyword"> del servidor de informes </span> software que actualizará el servidor de Data Workbench. Las opciones son true o false. El valor predeterminado es true. </p> <p>A continuación se muestra un ejemplo de este parámetro que puede utilizar un modelo: </p> <p> <code> Update&amp;nbsp;Software&amp;nbsp;=&amp;nbsp;bool:&amp;nbsp;false </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Uso de la renderización de hardware de OpenGL </td> 
   <td colname="col2"> <p>Controla si <span class="keyword"> Servidor de informes </span> utiliza la renderización de hardware (como la tarjeta gráfica del equipo) para generar la salida del informe. Las opciones son true o false. El valor predeterminado es true. </p> <p>Este parámetro debe establecerse en false solo cuando tenga problemas con la tarjeta gráfica. Cuando se establece en false, <span class="keyword"> Servidor de informes </span> no intenta utilizar la renderización de hardware y utiliza la renderización de software de forma predeterminada. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Creación de informes </td> 
   <td colname="col2"> Identificador de sección de los parámetros que se establecen para configurar la creación de informes. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Intervalo de mensaje de finalización </td> 
   <td colname="col2"> <p>Frecuencia (en segundos) con la que <span class="keyword"> Servidor de informes </span> imprime los mensajes de estado de finalización cuando se ejecutan consultas durante la generación de informes o alertas. El valor predeterminado es 120 segundos. </p> <p>Ejemplo: Las consultas de Workspace están completadas al 62,145672 %. </p> <p>Los mensajes de finalización se escriben en la variable <span class="filepath"> reportserver.log </span> y se sincronizan con el servidor. Esta configuración controla el <span class="filepath"> status.txt </span> archivos que se envían de un lado a otro para cada conjunto de informes, de modo que el porcentaje completado se pueda mostrar con miniaturas. Los mensajes se envían cada vez que se completa un conjunto de informes o cuando se alcanza el intervalo, lo que suceda primero. Si establece este valor más alto, no afectará a la velocidad a la que ve el informe generado en la interfaz del cliente por las miniaturas, pero sí a la cantidad de mensajes intermedios que ve. Si se especifica un valor bajo, el sistema puede invertir una gran cantidad de tiempo en sincronizar datos, ya que los datos se sincronizan con <span class="keyword"> Servidor de informes </span> servidor al perfil, en todas las DPU y a todos los clientes conectados cada vez a <span class="filepath"> status.txt </span> cambios en los mensajes. </p> <p>El sistema siempre envía un <span class="filepath"> status.txt </span> cuando se completa un conjunto de informes, independientemente de la configuración de este parámetro de configuración. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Perfiles </td> 
   <td colname="col2"> <p>Número que indica la cantidad de elementos enumerados en este vector. Para cada perfil para el que se van a crear informes, agregue una variable <span class="wintitle"> ReportProfile </span> en el vector Profiles y complete los parámetros Server y Profile . </p> <p> <span class="wintitle"> Servidor </span> - El nombre que <span class="keyword"> Servidor de informes </span> utiliza internamente para identificar el servidor de Data Workbench. Este nombre debe ser el nombre común del servidor que aparece en el certificado SSL del servidor de Data Workbench. </p> <p> <span class="wintitle"> Perfil </span> - Nombre del perfil para el que se van a crear los informes. Este nombre debe coincidir con el perfil con nombre del equipo de servidor de Data Workbench. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Servidor SMTP para errores </td> 
   <td colname="col2"> <p>La dirección del servidor SMTP desde el que desea enviar <span class="wintitle"> Servidor de informes </span> errores por correo electrónico. </p> <p>Ejemplo: <span class="filepath"> mail.mycompany.com </span> </p> <p>Se requiere un servidor SMTP para utilizar las capacidades descritas. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Contraseña del servidor SMTP para errores </td> 
   <td colname="col2"> <p>La contraseña para iniciar sesión en el servidor SMTP. Este parámetro es opcional a menos que sea necesario iniciar sesión para enviar correo. </p> <p>Se requiere un servidor SMTP para utilizar las capacidades descritas. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Servidor SMTP para enviar errores desde </td> 
   <td colname="col2"> La dirección de correo electrónico desde la que desea enviar <span class="wintitle"> Servidor de informes </span> errores. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Servidor SMTP para enviar a errores </td> 
   <td colname="col2"> <p>Las direcciones de correo electrónico a las que se envían las alertas. </p> <p>Ejemplo: <span class="filepath"> adm1@company.com,adm2@company.com </span> </p> <p>Se requiere un servidor SMTP para utilizar las capacidades descritas. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Servidor SMTP para nombre de usuario con errores </td> 
   <td colname="col2"> <p>El nombre de usuario para iniciar sesión en el servidor SMTP. Este parámetro es opcional a menos que sea necesario iniciar sesión para enviar correo. </p> <p>Se requiere un servidor SMTP para utilizar las capacidades descritas. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Intervalo de estado </td> 
   <td colname="col2"> <p>Frecuencia (en segundos) con la que <span class="wintitle"> Servidor de informes </span> genera y envía información de estado al servidor de Data Workbench para que se muestre en <span class="wintitle"> Estado detallado </span>. </p> <p>El valor predeterminado es 120 segundos. No se recomienda establecer este valor en un valor pequeño, como dos minutos, porque una cola de informes puede tardar horas en ejecutarse. En ese caso, puede considerar la posibilidad de configurar 600 a 1200 segundos. </p> <p>Para obtener más información, consulte <span class="wintitle"> Estado detallado </span>, consulte el capítulo Interfaces administrativas del <a href="https://experienceleague.adobe.com/docs/data-workbench/using/client/admin-ui/c-admin-intrf.html" format="http" scope="external"> Guía del usuario de Insight </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Intervalo de actualización </td> 
   <td colname="col2"> <p>Frecuencia (en minutos) con la que <span class="keyword"> Servidor de informes </span> supervisa todos los perfiles enumerados en el vector Perfiles para ver los nuevos informes y alertas. El valor predeterminado es de 10 minutos. </p> <p>El tiempo que especifique se divide entre todos los perfiles enumerados. Por ejemplo, si el intervalo se establece en 10 minutos y supervisa dos perfiles, cada perfil se supervisa durante 5 minutos. Si se supervisa un perfil cuando se guarda un informe o una alerta nuevos o modificados en el perfil, el informe o la alerta están disponibles inmediatamente para su generación. </p> <p>Si la variable <span class="wintitle"> Intervalo de actualización </span> está configurado para supervisar más de un perfil, es importante que este ajuste sea lo suficientemente alto como para cargar todos los perfiles en el tiempo configurado. En sistemas con muchas dimensiones grandes configuradas, por ejemplo, en los que puede tardar varios minutos en recuperar la conexión de datos inicial con todos los nombres de elementos, esta configuración debe ser lo suficientemente larga como para que se produzca esa sincronización completa. De lo contrario, el sistema genera un error de sincronización de perfiles. </p> </td> 
  </tr> 
 </tbody> 
</table>
