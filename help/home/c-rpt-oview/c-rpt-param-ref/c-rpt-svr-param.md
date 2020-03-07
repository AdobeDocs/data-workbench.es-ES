---
description: Información sobre los parámetros de Report Server.cfg.
solution: Analytics
title: Parámetros de Report Server.cfg
topic: Data workbench
uuid: 506f30f7-c8c6-4580-8423-7da8d00b0d57
translation-type: tm+mt
source-git-commit: 6443bdf8856ba51252685fa0c1ed65f831142956

---


# Parámetros de Report Server.cfg{#report-server-cfg-parameters}

Información sobre los parámetros de Report Server.cfg.

El ejemplo [!DNL Report Server.cfg] mostrado en [Configuración de la conexión con el servidor](../../../home/c-rpt-oview/c-inst-rpt/t-config-conn-ins-svr.md#task-a3ca949c43244782b658fb4437fd724c) de Insight contiene únicamente los parámetros incluidos en el [!DNL Report Server.cfg] archivo de forma predeterminada.

Si se pone en contacto con el servidor de licencias de Adobe a través de un servidor proxy, deberá agregar el vector de licencias y sus parámetros al [!DNL Report Server.cfg]. A continuación se muestra un ejemplo de este vector y sus parámetros que puede utilizar un modelo para el vector de licencias:

```
Licensing = serverInfo:  
Proxy Address = string: ProxyIPAddress 
Proxy Password = string: ProxyPassword 
Proxy Port = int: ProxyPort 
Proxy User Name = string: ProxyUserName 
```

En la tabla siguiente se describen los parámetros del [!DNL Report Server.cfg] archivo:

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
   <td colname="col2"> <p>Las extensiones de Excel admitidas son: </p> <p>Extensión de Excel = cadena: <span class="filepath"> .xlsx </span> </p> <p>Extensión de Excel = cadena: <span class="filepath"> .xls </span> (predeterminado) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Fuentes </td> 
   <td colname="col2"> <p>Opcional. Vector que enumera las fuentes que <span class="keyword"> el servidor de informes </span> debe utilizar para representar caracteres especiales unicode basados en UTF8. El número de fuentes de la lista es ilimitado. </p> <p>La primera fuente siempre debe ser la consola Lucida Sans. Si este parámetro no está incluido en el archivo <span class="filepath"> Report Server.cfg </span> , el servidor de informes <span class="keyword"> </span> utiliza solo la consola Lucida Sans para mostrar el texto. </p> <p> <span class="keyword"> El servidor de informes </span> utiliza la primera fuente de la lista para representar todos los caracteres hasta que encuentra un carácter que no puede representar. A continuación, utiliza la segunda fuente de la lista para representar ese carácter. Si esa fuente no representa el carácter, <span class="keyword"> el servidor de informes </span> utiliza la tercera fuente de la lista para representar ese carácter, etc., hasta que llegue al final de la lista de fuentes. Si la fuente correcta no aparece en el vector, <span class="keyword"> el servidor de informes </span> muestra el valor hexadecimal del carácter. </p> <p> <p>Nota:  No realice cambios en este parámetro mientras <span class="keyword"> Report Server </span> se esté ejecutando. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Gamma </td> 
   <td colname="col2"> <p> <span class="wintitle"> Configuración de gamma </span> para la salida del archivo <span class="filepath"> .png </span> . El valor predeterminado es 1.6. </p> <p> <p>Nota:  Adobe no recomienda cambiar este valor. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Licencias </td> 
   <td colname="col2"> <p>Opcional. Solo es necesario modificar los parámetros de este vector si se pone en contacto con el servidor de licencias de Adobe a través de un servidor proxy. </p> <p>Identificador de sección de los parámetros que se configuraron para comunicarse con el servidor de licencias de Adobe a través de un servidor proxy. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Dirección proxy </td> 
   <td colname="col2"> La dirección de un servidor proxy que <span class="keyword"> el servidor de informes </span> debe utilizar para acceder al servidor de licencias de Adobe. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Contraseña de proxy </td> 
   <td colname="col2"> Opcional. La contraseña asociada al nombre de usuario del <span class="wintitle"> proxy </span>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Puerto proxy </td> 
   <td colname="col2"> El puerto del servidor proxy. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Nombre de usuario proxy </td> 
   <td colname="col2"> Opcional. Nombre de usuario utilizado para acceder al servidor proxy. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Ubicación de red </td> 
   <td colname="col2"> Ubicación de red que <span class="keyword"> el servidor de informes </span> utiliza para resolver el nombre común del servidor en una dirección IP. Las ubicaciones de red se definen en el archivo de dirección ubicado en el directorio Direcciones del equipo del servidor del área de trabajo de datos. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Servidores </td> 
   <td colname="col2"> <p>Identificador de sección para los parámetros que se configuran para configurar los equipos de servidor del área de trabajo de datos <span class="keyword"> que el servidor de informes </span> debe conectar para generar informes. Esto incluye un número que indica cuántos elementos se muestran en este vector. </p> <p>Para cada servidor, agregue una entrada serverInfo y complete los parámetros según sea necesario. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Dirección </td> 
   <td colname="col2"> Dirección IP del equipo del servidor del área de trabajo de datos al que <span class="keyword"> el servidor de informes </span> debe conectarse para generar informes. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Nombre </td> 
   <td colname="col2"> Nombre que <span class="keyword"> el servidor de informes </span> utiliza internamente para identificar el servidor del área de trabajo de datos. Se trata simplemente de una etiqueta interna, por lo que puede utilizar cualquier nombre que desee. Para mantener la coherencia, le sugerimos que utilice el nombre común que aparece en el certificado digital del servidor. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Puerto </td> 
   <td colname="col2"> Puerto a través del cual <span class="keyword"> el servidor de informes </span> se comunica con el servidor del área de trabajo de datos. Para conexiones seguras, este valor suele ser 443. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Dirección proxy </td> 
   <td colname="col2"> La dirección de un servidor proxy que <span class="keyword"> el servidor de informes </span> debe utilizar para acceder al servidor del área de trabajo de datos. Este parámetro solo es necesario cuando se requiere un servidor proxy para conectarse a los equipos del servidor. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Contraseña de proxy </td> 
   <td colname="col2"> La contraseña del servidor proxy. Este parámetro solo es necesario cuando se requiere un servidor proxy para conectarse a los equipos de servidor del área de trabajo de datos. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Puerto proxy </td> 
   <td colname="col2"> El puerto del servidor proxy. El valor predeterminado es 8080. Este parámetro solo es necesario cuando se requiere un servidor proxy para conectarse a los equipos de servidor del área de trabajo de datos. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Nombre de usuario proxy </td> 
   <td colname="col2"> Nombre de usuario del servidor proxy. Este parámetro solo es necesario cuando se requiere un servidor proxy para conectarse a los equipos de servidor del área de trabajo de datos. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Certificado de cliente SSL </td> 
   <td colname="col2"> Nombre del archivo de certificado SSL para el equipo del <span class="keyword"> servidor de informes </span> . </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Nombre común del servidor SSL </td> 
   <td colname="col2"> <span class="wintitle"> Nombre común del servidor </span> en el certificado digital del servidor del área de trabajo de datos. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Usar SSL </td> 
   <td colname="col2"> Indica si SSL se utiliza para la comunicación segura entre el servidor del área de trabajo de datos y <span class="keyword"> el servidor de informes </span>. Las opciones son true o false. El valor predeterminado es true. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Límite de memoria de resultados (KB) </td> 
   <td colname="col2"> <p>Cantidad de memoria (en KB) que desea que esté disponible para informes y alertas. El valor predeterminado es 50000. </p> <p>Al ejecutar informes, <span class="keyword"> el servidor de informes </span> comprueba primero este valor y, a continuación, comprueba el valor en el parámetro Tamaño máximo de fracción. Por ejemplo, si establece este parámetro en 50.000 y el Tamaño máximo de fracción en 50, el servidor de informes <span class="keyword"> </span> ejecuta solo 50 espacios de trabajo a la vez, aunque haya espacio disponible para ejecutar más espacios de trabajo. </p> <p> <p>Nota:  Este límite nunca debe superar el valor establecido en el parámetro de límite de memoria de consulta del servidor del área de trabajo de datos y, idealmente, debe establecerse un valor un poco inferior al límite de memoria de <span class="wintitle"> consulta </span> para proporcionar cierta libertad a otros usuarios que estén ejecutando informes al mismo tiempo. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Tamaño máximo del sector </td> 
   <td colname="col2"> Número máximo de espacios de trabajo de informes que <span class="keyword"> el servidor de informes </span> puede ejecutar al mismo tiempo. El valor predeterminado es 50. Para obtener más información acerca de cómo <span class="keyword"> el servidor de informes </span> utiliza esta configuración, consulte la descripción del parámetro Límite de memoria de <span class="wintitle"> resultados (KB) </span> . </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Actualizar software </td> 
   <td colname="col2"> <p>Indica si se permite que el servidor del área de trabajo de datos actualice el software <span class="keyword"> de este servidor de informes </span> . Las opciones son true o false. El valor predeterminado es true. </p> <p>A continuación se muestra un ejemplo de este parámetro que puede utilizar un modelo: </p> <p> <code> Update&amp;nbsp;Software&amp;nbsp;=&amp;nbsp;bool:&amp;nbsp;false </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Usar procesamiento de hardware OpenGL </td> 
   <td colname="col2"> <p>Controla si <span class="keyword"> el servidor de informes </span> utiliza la representación de hardware (como la tarjeta gráfica del equipo) para generar la salida del informe. Las opciones son true o false. El valor predeterminado es true. </p> <p>Este parámetro debe establecerse en false solo cuando se produzcan problemas con la tarjeta gráfica. Cuando se establece en false, <span class="keyword"> el servidor de informes </span> no intenta utilizar el procesamiento por hardware y utiliza el procesamiento por software de forma predeterminada. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Creación de informes </td> 
   <td colname="col2"> Identificador de sección para los parámetros que se configuran para configurar los informes. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Intervalo de mensaje de finalización </td> 
   <td colname="col2"> <p>Frecuencia (en segundos) con la que <span class="keyword"> el servidor de informes </span> imprime los mensajes de estado de finalización cuando se ejecutan consultas durante la generación de informes o alertas. El valor predeterminado es 120 segundos. </p> <p>Ejemplo: Las consultas de espacio de trabajo se completan al 62,145672%. </p> <p>Los mensajes de finalización se escriben en <span class="filepath"> reportserver.log </span> y se sincronizan con el servidor. Esta configuración controla los archivos <span class="filepath"> status.txt </span> que se envían hacia adelante y hacia atrás para cada conjunto de informes, de modo que el porcentaje completado se pueda mostrar con miniaturas. Los mensajes se envían cada vez que se completa un conjunto de informes o cuando se alcanza el intervalo, lo que suceda primero. Si establece este valor más alto, no se afecta la velocidad a la que ve el informe generado en la interfaz del cliente por las miniaturas, pero sí se aplica la cantidad de mensajes intermedios que ve. Especificar un valor bajo puede hacer que el sistema invierta una gran cantidad de tiempo en sincronizar datos, ya que los datos se sincronizan desde el servidor de <span class="keyword"> informes </span> al perfil, en todos los DPU y en todos los clientes conectados cada vez que cambia un mensaje <span class="filepath"> status.txt </span> . </p> <p>El sistema siempre envía un archivo <span class="filepath"> status.txt </span> cuando se completa un conjunto de informes, independientemente de la configuración de este parámetro de configuración. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Perfiles </td> 
   <td colname="col2"> <p>Número que indica cuántos elementos se muestran en este vector. Para cada perfil para el que se van a crear informes, agregue una entrada <span class="wintitle"> de perfilInforme </span> en el vector Perfiles y complete los parámetros Servidor y Perfil. </p> <p> <span class="wintitle"> Servidor </span> : nombre que <span class="keyword"> el servidor de informes </span> utiliza internamente para identificar el servidor del área de trabajo de datos. Este nombre debe ser el nombre común del servidor que aparece en el certificado SSL del servidor del área de trabajo de datos. </p> <p> <span class="wintitle"> Perfil </span> : Nombre del perfil para el que se van a crear los informes. Este nombre debe coincidir con el perfil con nombre del equipo del servidor del área de trabajo de datos. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Servidor SMTP para errores </td> 
   <td colname="col2"> <p>La dirección del servidor SMTP desde el que desea enviar los errores del servidor de <span class="wintitle"> informes </span> por correo electrónico. </p> <p>Ejemplo: <span class="filepath"> mail.mycompany.com </span> </p> <p>Se requiere un servidor SMTP para utilizar las capacidades descritas. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Servidor SMTP para contraseña de errores </td> 
   <td colname="col2"> <p>La contraseña para iniciar sesión en el servidor SMTP. Este parámetro es opcional a menos que sea necesario iniciar sesión para enviar correo. </p> <p>Se requiere un servidor SMTP para utilizar las capacidades descritas. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Servidor SMTP para enviar errores </td> 
   <td colname="col2"> La dirección de correo electrónico desde la cual desea enviar los errores <span class="wintitle"> del servidor de informes </span> . </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Servidor SMTP para errores enviados a </td> 
   <td colname="col2"> <p>Las direcciones de correo electrónico a las que se envían las alertas. </p> <p>Ejemplo: <span class="filepath"> adm1@company.com,adm2@company.com </span> </p> <p>Se requiere un servidor SMTP para utilizar las capacidades descritas. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Servidor SMTP para nombre de usuario de errores </td> 
   <td colname="col2"> <p>Nombre de usuario para iniciar sesión en el servidor SMTP. Este parámetro es opcional a menos que sea necesario iniciar sesión para enviar correo. </p> <p>Se requiere un servidor SMTP para utilizar las capacidades descritas. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Intervalo de estado </td> 
   <td colname="col2"> <p>Frecuencia (en segundos) con la que <span class="wintitle"> el servidor de informes </span> genera y envía información de estado al servidor del área de trabajo de datos para que se muestre en estado <span class="wintitle"> detallado </span>. </p> <p>El valor predeterminado es 120 segundos. No se recomienda establecer este valor en un valor pequeño, como dos minutos, ya que una cola de informes puede tardar horas en ejecutarse. En ese caso, podría considerar un ajuste de 600 a 1200 segundos. </p> <p>Para obtener más información sobre <span class="wintitle"> el estado detallado </span>, consulte el capítulo Interfaces administrativas de la Guía del usuario de <a href="https://docs.adobe.com/content/help/en/data-workbench/using/client/admin-ui/c-admin-intrf.html" format="http" scope="external"> Insight </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Intervalo de actualización </td> 
   <td colname="col2"> <p>Frecuencia (en minutos) con la que <span class="keyword"> el servidor de informes </span> supervisa todos los perfiles enumerados en el vector Perfiles para nuevos informes y alertas. El valor predeterminado es 10 minutos. </p> <p>El tiempo que especifique se divide entre todos los perfiles enumerados. Por ejemplo, si el intervalo está establecido en 10 minutos y está monitoreando dos perfiles, cada perfil se monitorea durante 5 minutos. Si se está supervisando un perfil cuando se guarda un informe o una alerta nuevos o modificados en el perfil, el informe o la alerta estarán disponibles inmediatamente para la generación. </p> <p>Si el intervalo de <span class="wintitle"> actualización </span> está configurado para supervisar más de un perfil, es importante que este ajuste sea lo suficientemente alto como para cargar todos los perfiles en el tiempo configurado. En sistemas con muchas dimensiones grandes configuradas, por ejemplo, en los que puede tomar varios minutos recuperar la conexión de datos inicial con todos los nombres de elementos, esta configuración debe ser lo suficientemente larga como para que se produzca la sincronización completa. De lo contrario, el sistema emite un error de sincronización de perfiles. </p> </td> 
  </tr> 
 </tbody> 
</table>

