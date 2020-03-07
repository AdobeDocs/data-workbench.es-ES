---
description: Información sobre los parámetros de Report.cfg.
solution: Analytics
title: Parámetros de Report.cfg
topic: Data workbench
uuid: 7a20f4f6-99e6-401a-ba3c-c508881c0f0d
translation-type: tm+mt
source-git-commit: 2e4991206394ca0c463210990ea44dfb700341a5

---


# Parámetros de Report.cfg{#report-cfg-parameters}

Información sobre los parámetros de Report.cfg.

El ejemplo [!DNL Report.cfg] mostrado en [Configurar el conjunto](../../../home/c-rpt-oview/c-work-rpt-sets/t-create-rpt-set/t-config-rpt-set/t-config-rpt-set.md#task-cfb2fd0c28bc48c2acdd582fe0d670d0) de informes contiene únicamente los parámetros incluidos en el [!DNL Report.cfg] archivo de forma predeterminada. La siguiente tabla proporciona descripciones de todos los parámetros de [!DNL Report.cfg] archivo disponibles.

Si necesita agregar parámetros adicionales a un [!DNL Report.cfg] archivo, debe hacerlo con un editor de texto. Para ver los pasos a seguir, incluidos ejemplos de cómo definir cada entrada de parámetro, consulte [Edición de archivos Report.cfg](../../../home/c-rpt-oview/c-work-rpt-sets/c-edit-ex-rpt-files/c-edit-ex-rpt-files.md#concept-96fd57159f454defa09bd18655a12887)existentes.

>[!NOTE]
>
>Los parámetros de esta tabla se enumeran en orden alfabético. Al abrir el [!DNL Report.cfg] archivo en el Área de trabajo de datos, los vectores se muestran en orden alfabético, seguidos de parámetros individuales enumerados en orden alfabético.

<table id="table_F55E925EA34F43B6832788BB6878BB4A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parámetro </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Umbral de alerta </td> 
   <td colname="col2"> <p><i>Opcional</i>. Este parámetro se aplica solamente a los informes con indicadores de métricas. Número de indicadores de métricas que deben aparecer en la hoja de cálculo antes de enviar un informe de alertas. </p> <p>Si solo se está supervisando una métrica en la hoja de cálculo del indicador de métrica, establezca el umbral en 1. El informe se genera cuando la métrica de la hoja se evalúa en una flecha hacia arriba/abajo o en una X. Si hay más de una métrica monitoreada en el informe, puede seleccionar el número de indicadores de métricas que deben evaluarse en una flecha hacia arriba/hacia abajo o en una X antes de que se genere el informe. Por ejemplo: si se supervisan dos métricas: 
     <ul id="ul_A64E8A2306B14371A233D372B956F64D"> 
      <li id="li_2A3020ED350644A3954C36D3EB0B86D4">Si el umbral está establecido en 1, el informe se genera si alguna de las métricas de la hoja se evalúa en una flecha hacia arriba/hacia abajo o en una X. </li> 
      <li id="li_DA4EF4984880483DA48322D9D57B9240">Si el umbral está establecido en 2, ambas métricas deben evaluarse en una flecha hacia arriba/abajo o en una X antes de que se genere el informe. </li> 
     </ul> </p> <p>Para obtener más información sobre los indicadores de métricas, consulte la Guía del usuario <i>del área de trabajo de datos</i>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Permitir regeneración de informes </td> 
   <td colname="col2"> <p>Indica si <span class="keyword"> el servidor de informes </span> genera o regenera automáticamente determinados informes al crearlos o modificarlos. Las opciones son true o false. Si se establece en true, la creación o modificación de un espacio de trabajo de informe hace que <span class="keyword"> el servidor de informes </span> vuelva a generar ese informe para la ejecución más reciente. </p> <p> <p>Nota:  Si se cambia el <span class="filepath"> archivo Report.cfg </span> , el servidor de <span class="keyword"> informes </span> regenerará todos los informes controlados por ese <span class="filepath"> archivo Report.cfg </span> . </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Archivos adjuntos </td> 
   <td colname="col2"> <p><i>Opcional</i>. Identificador de sección para el nombre y el tipo de contenido de cualquier archivo adjunto que salga con informes distribuidos por correo electrónico, incluido el número de datos adjuntos. </p> <p>Para agregar un nuevo archivo adjunto: 
     <ol id="ol_CBDC1E95D34A4D08A862680127438433"> 
      <li id="li_784C48C540534F4CBB35BBDA6BC5F48E">Abra el <span class="filepath"> archivo Report.cfg </span> en Área de trabajo de datos. </li> 
      <li id="li_0709ADDDDF2E469FAB10761B46173136">Haga clic con el botón secundario del mouse (ratón) en <span class="uicontrol"> Datos adjuntos </span> y, a continuación, haga clic en <span class="uicontrol"> Agregar nuevo elemento secundario </span> &gt; <span class="uicontrol"> Datos adjuntos </span>. </li> 
     </ol> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Tipo de contenido </td> 
   <td colname="col2"> <p>Tipo de contenido del archivo que se va a adjuntar. </p> <p>Ejemplo: image/jpeg </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Nombre de archivo </td> 
   <td colname="col2"> <p>Ubicación y nombre del archivo que se adjuntará. </p> <p>Ejemplo: <span class="filepath"> c:\myimage.jpg </span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Conjunto de colores </td> 
   <td colname="col2"> Identifica la combinación de colores que se utilizará para los archivos <span class="filepath"> .png </span> . 0 es para un fondo negro; 1 es para un fondo blanco; y 2 es para una imagen en escala de grises. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Comando para ejecutar </td> 
   <td colname="col2"> <i>Opcional</i>. Un comando por lotes o un ejecutable que se ejecuta después de que se genere el conjunto de informes. Si se requiere el inicio del intérprete del shell de comandos, preceda el comando con cmd /c. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Plantilla de Excel predeterminada </td> 
   <td colname="col2"> <p><i>Opcional</i>. Nombre de archivo del archivo de plantilla de Excel genérico ( <span class="filepath"> .xls </span> o <span class="filepath"> .xlsx </span>) que desea utilizar al generar informes como archivos de Excel. Este parámetro admite rutas de archivo completas, como <span class="filepath"> c:\templates\mytemplate.xls </span>. </p> <p>Este archivo se utiliza para todos los informes de Excel a menos que se haya definido una plantilla específica para un informe en particular. Consulte <a href="../../../home/c-rpt-oview/c-work-rpt-sets/t-create-rpt-set/t-config-rpt-set/c-gen-rpts-ex-files.md#section-40ab11916f464b1a88214ab969da6751"> Uso de un archivo de plantilla </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Nombre de la dimensión </td> 
   <td colname="col2"> <i>Opcional</i>. Nombre de la dimensión para la que desea generar un informe de forma dinámica. Si introduce un nombre de dimensión en este parámetro, debe introducir un valor en el parámetro Archivo de búsqueda o en los parámetros Métrica N superior y Valor N superior. La dimensión nombrada en este parámetro debe existir en el conjunto de datos para el cual se crean los informes. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Enviar correo electrónico solo si es perfecto </td> 
   <td colname="col2"> <i>Opcional</i>. Permite al usuario especificar que un conjunto de informes se debe enviar solamente cuando no se hayan producido errores durante la ejecución. Las opciones son true y false. El valor predeterminado es false. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Fecha final </td> 
   <td colname="col2"> <p><i>Opcional</i>. Fecha y hora de la última vez que desea que se ejecute el informe. Este tiempo se basa en el valor Con el tiempo del conjunto de datos. </p> <p>Formato: MM/DD/AAAA hh:mm huso horario, usando la sintaxis de 24 horas para hora </p> <p>Ejemplo: 08/01/2007 12:01 EDT </p> <p>Para obtener más información sobre la configuración de huso horario, consulte la Guía <i>de configuración de</i>conjuntos de datos. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Cada </td> 
   <td colname="col2"> Frecuencia de generación del conjunto de informes: día, semana o mes. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Tiempo de espera de vigilancia de Excel (segundos) </td> 
   <td colname="col2"> <p><i>Opcional</i>. Cantidad de segundos que desea que <span class="keyword"> el servidor de informes espere </span> a que Microsoft Excel responda al generar un informe como archivo de Excel antes de que el servidor de <span class="keyword"> informes </span> decida que Excel no responde y finalice el proceso. El uso de este parámetro permite <span class="keyword"> que el servidor de informes </span> termine Excel cuando deja de responder y siga procesando los informes que no sean de Excel. El valor predeterminado es 300.0. Para deshabilitar esta funcionalidad, establezca este parámetro en 0.0. </p> <p>Asegúrese de que el valor que defina sea lo suficientemente largo como para permitir que el informe se exporte a Excel. De lo contrario, <span class="keyword"> el servidor de informes </span> podría finalizar Excel antes de tiempo y el informe no se generará. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Fórmula de filtro </td> 
   <td colname="col2"> <p><i>Opcional</i>. Filtro que se aplica a cada área de trabajo del conjunto de informes. </p> <p>Para obtener más información, consulte la <a href="https://docs.adobe.com/content/help/en/data-workbench/using/client/t-open-ins.html#Syntax_for_Filter_Expressions" format="http" scope="external"> sintaxis para crear filtros </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Corrección de gamma </td> 
   <td colname="col2"> <p>Configuración de gamma para la salida <span class="filepath"> .png </span> . El valor predeterminado es 1.6. </p> <p> <p>Nota:  Adobe recomienda que no cambie este valor. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Ocultar logotipos </td> 
   <td colname="col2"> Indica si el servidor de informes oculta los logotipos al generar los informes. Las opciones son <span class="filepath"> true </span> o <span class="filepath"> false </span>. Si se establece en <span class="filepath"> false </span>, el informe se genera con el logotipo del informe. The default is <span class="filepath"> false </span>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Archivo de búsqueda </td> 
   <td colname="col2"> <p><i>Opcional</i>. Cuando se rellena este parámetro, el servidor de informes se ejecuta en modo dinámico y genera informes para cada elemento de la dimensión especificada en el parámetro Nombre de dimensión. Este archivo debe contener dos columnas separadas por tabuladores, sin una fila de encabezado. </p> <p> 
     <ul id="ul_378D4104BB5141C4A013EFE881BFFC6A"> 
      <li id="li_6F2C89A286B24FFE8EE8C82D278D0633">La columna 1 contiene una lista de elementos de dimensión. </li> 
      <li id="li_4BD1CAA77FEC43268B40489BC5E5E6F7">La columna 2 contiene las direcciones de correo electrónico de los destinatarios del informe. Se envía un informe de un elemento determinado en la columna 1 a la dirección de correo electrónico en la misma fila de la columna 2. Puede introducir varias direcciones de correo electrónico separándolas con comas (sin espacios). Si los informes no se van a enviar por correo electrónico, esta columna puede estar vacía pero debe existir. </li> 
     </ul> </p> <p> <p>Nota:  Si introduce un valor en este parámetro, debe introducir un valor en el parámetro Nombre de dimensión. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Solo notificación </td> 
   <td colname="col2"> Esta configuración <span class="wintitle"> del servidor de informes </span> le permite configurar el área de trabajo de datos para enviar un correo electrónico cuando se genera un informe. Al establecer este valor en <span class="filepath"> true </span> no se envía el informe, sino que se envía un mensaje de correo electrónico que notifica al usuario suscrito que se ha generado el informe. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Informe de correo </td> 
   <td colname="col2"> <p>Identificador de sección para distribuir informes por correo electrónico. Para distribuir los informes por correo electrónico, complete los siguientes parámetros para la entrada <span class="wintitle"> Informe de correo </span> . Todos los informes del conjunto de informes se envían por correo electrónico en un mensaje a las direcciones de correo electrónico especificadas en el parámetro Destinatarios. </p> <p> <p>Nota:  El servidor de informes envía un mensaje de correo electrónico únicamente cuando ha generado al menos un informe. </p> </p> <p>Para habilitar el envío de informes por correo electrónico, debe completar al menos los siguientes parámetros para esta entrada: 
     <ul id="ul_539D64D61A8B4F1E95D889C6610EE3B8"> 
      <li id="li_D2EDBEE57BFE4FD4BB66F63AE561F1E2">Servidor SMTP </li> 
      <li id="li_4EEFE6CDA3384FE38149CE8DCBEFF847">Destinatarios </li> 
      <li id="li_CF9F0CF7ECFC4D88A7F4F11BAC4938D6">Dirección del remitente </li> 
      <li id="li_40BFDCDC9640488EBB450CF8579DA250">Solo notificación </li> 
     </ul> </p> <p> <p>Nota:  Para enviar informes por correo electrónico después de volver a generar un conjunto de informes, consulte <a href="../../../home/c-rpt-oview/c-work-rpt-sets/c-edit-ex-rpt-files/c-edit-ex-rpt-files.md#concept-96fd57159f454defa09bd18655a12887"> Edición de archivos Report.cfg existentes </a>. </p> </p> <p>El valor Solo notificación está disponible en las versiones 5.4x y 5.5x. </p> <p>Para que se notifique a un gran conjunto de destinatarios (más de 20), es muy recomendable que utilice listas de distribución por correo electrónico. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Plantilla XSL de cuerpo </td> 
   <td colname="col2"> <p><i>Opcional</i>. Ruta del archivo de plantilla XSL que se aplicará al archivo <span class="filepath"> reports.xml </span> . El uso de este parámetro permite que el servidor de informes envíe los informes dentro del correo electrónico distribuido en lugar de como archivos adjuntos. El texto resultante se utiliza como cuerpo del mensaje de correo electrónico. </p> <p>Consulte <a href="../../../home/c-rpt-oview/c-rpt-sample-files/c-rpt-sample-files.md#concept-a06b93f21c5d4888be335fa2281b2a87"> Archivos de muestra de informes </a> para ver un archivo de muestra. </p> <p>Para obtener información sobre el lenguaje de hojas de estilo extensible (XSLT), consulte <a href="http://www.w3.org/Style/XSL/" format="http" scope="external"> La familia de lenguajes de hoja de estilo extensible </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Destinatarios </td> 
   <td colname="col2"> Direcciones de correo electrónico de las personas a las que desee enviar el informe. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Dirección del remitente </td> 
   <td colname="col2"> Dirección de correo electrónico del remitente. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Nombre del remitente </td> 
   <td colname="col2"> Opcional. Nombre del remitente. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Servidor SMTP </td> 
   <td colname="col2"> Dirección del equipo del servidor SMTP y la contraseña y el nombre de usuario necesarios para la autenticación. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Asunto </td> 
   <td colname="col2"> <i>Opcional</i>. Línea de asunto que describe el correo electrónico que se va a enviar. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Solo notificación </td> 
   <td colname="col2"> Permite configurar el área de trabajo de datos para enviar un correo electrónico cuando se genera un informe en segundo plano. Al establecer este valor en True, no se envía el informe, sino que se envía un correo electrónico que vincula al usuario suscrito con la ubicación del informe. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Raíz de salida </td> 
   <td colname="col2"> <p><i>Opcional</i>. Ubicación de salida de los conjuntos de informes generados. El valor predeterminado es la carpeta <i>&lt;profile name&gt;</i>\Reports dentro del directorio de instalación del servidor de informes. </p> <p>Para configurar <span class="keyword"> el servidor de informes </span> para que genere informes en un portal, establezca la raíz de salida en la raíz del <span class="wintitle"> documento </span> del servidor web utilizado para el portal. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Precargar filtro de consulta </td> 
   <td colname="col2"> <p><i>Opcional</i>. Este parámetro se aplica solamente al tipo de informe <span class="wintitle"> Elemento de dimensión superior </span> . </p> <p>Nombre del filtro que desea aplicar a la consulta que debe ejecutarse para determinar los elementos de dimensión N principales antes de que se pueda generar el informe. El valor predeterminado es <span class="wintitle"> Broken_Session_Filter </span>. Para obtener más información sobre el filtro de sesión <span class="wintitle"> interrumpida </span>, consulte la Guía del usuario <i>del área de trabajo de datos</i>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Tipos de informes </span> </td> 
   <td colname="col2"> <p>Formato(s) en el que desea generar la salida. Puede utilizar cualquiera o todas las siguientes opciones para generar el conjunto de informes en varios formatos al mismo tiempo: 
     <ul id="ul_FAF024F73F6B4F2C9D6760441E8F0CF9"> 
      <li id="li_04A3E0C7812B43E7BBFCDA8C3EA21CFC">Excel crea un libro de Excel con una visualización por hoja de cálculo. Como regla general, utilice archivos de Excel para la distribución por correo electrónico. Consulte <a href="../../../home/c-rpt-oview/c-work-rpt-sets/t-create-rpt-set/t-config-rpt-set/c-gen-rpts-ex-files.md#concept-0b0fdb938805422d95c5f6fe706f09ee"> Generación de informes como archivos de Microsoft Excel </a>. Para obtener información sobre el uso de un archivo de plantilla, consulte <a href="../../../home/c-rpt-oview/c-work-rpt-sets/t-create-rpt-set/t-config-rpt-set/c-gen-rpts-ex-files.md#section-40ab11916f464b1a88214ab969da6751"> Uso de un archivo de plantilla </a>. </li> 
      <li id="li_CD1BDDEDE85349CE8C736887BB5E4726">png crea archivos de gráficos de red portátiles. Como regla general, utilice archivos <span class="filepath"> .png </span> para mostrarlos en un navegador web (portal). </li> 
      <li id="li_869DA266E6A041A5BD343537743FAC79">La miniatura crea una miniatura (archivo <span class="filepath"> .jpg </span> ) del espacio de trabajo. El tamaño predeterminado es 240 x 180. Para cambiar el tamaño predeterminado, edite los parámetros Miniatura X y Miniatura Y. </li> 
     </ul> </p> <p>Para agregar un nuevo tipo de informe al editar <span class="filepath"> Report.cfg </span> en el área de trabajo de datos, haga clic con el botón secundario en <span class="uicontrol"> Tipos de informes </span>, haga clic en <span class="uicontrol"> Agregar nuevo elemento secundario </span>y seleccione el tipo de informe deseado. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Fecha inicial </td> 
   <td colname="col2"> <p>La primera fecha y hora en que desea que se ejecute el informe. Este tiempo se basa en el valor Con el tiempo del conjunto de datos. </p> <p>Formato: MM/DD/AAAA hh:mm huso horario, usando la sintaxis de 24 horas para el tiempo. </p> <p>Para obtener más información sobre la configuración de huso horario, consulte la Guía <i>de configuración de</i>conjuntos de datos. </p> <p> <p>Nota:  Los informes comienzan a ejecutarse cuando las marcas de hora de los datos del perfil coinciden con la fecha y la hora especificadas. </p> </p> <p>Ejemplo: </p> <p>Si la fecha de inicio es 08/08/2006 12:00 EST, los informes se ejecutan para datos con una marca de tiempo de 08/08/2006 12:00 EST y posterior. 
     <ul id="ul_EEF6F61B55E440DFB3348A9B10DFA5F1"> 
      <li id="li_133374F1287D4631BCAE7691E3FC93B6">Los informes diarios se ejecutarán para el 08/08/2006 y cada día a partir de entonces para los datos con hh:mm = 12:00 EST. </li> 
      <li id="li_89514719C5F94D789E4A1049D2CD5F93">Los informes semanales se ejecutarán para el 08/08/2006 y para cada 7 días a partir de entonces para los datos con hh:mm = 12:00 EST. </li> 
      <li id="li_EB986D04FA664DB89C66B0FC1CE4D36B">Los informes mensuales se ejecutarán para el 08/08/2006 y para el octavo día de cada mes a partir de entonces para los datos con hh:mm = 12:00 EST. </li> 
     </ul> </p> <p>La métrica <span class="wintitle"> Hora del </span> informe afecta a las dimensiones de informes "Última N", como "Últimos 7 días", "Ayer" y "Hace 3 semanas". Para las consultas en el servidor de informes, la <span class="wintitle"> métrica Tiempo del informe </span> ( <span class="filepath"> Tiempo del informe.métrica </span>) identifica la fecha y la hora para las que se ejecutan los informes. Inicialmente es la fecha y la hora especificadas en el parámetro Fecha de inicio, que luego se incrementa según el período especificado por el parámetro Cada. Para las consultas en el área de trabajo de datos, la métrica Tiempo del <span class="wintitle"> informe </span> se basa en la medianoche de la métrica Con fecha ( <span class="filepath"> Con fecha.métrica </span>). Debido a la diferencia en las definiciones de la métrica Tiempo de informe, si consulta un espacio de trabajo que utiliza una dimensión Última N, puede recibir resultados diferentes en el área de trabajo de datos y en el servidor de informes <span class="keyword"> </span> para el mismo espacio de trabajo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Miniatura X </td> 
   <td colname="col2"> <i>Opcional</i>. Número entero que controla el tamaño (en píxeles) del eje X de las miniaturas generadas como salida. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Miniatura Y </td> 
   <td colname="col2"> <i>Opcional</i>. Número entero que controla el tamaño (en píxeles) del eje Y de las miniaturas generadas como salida. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Métrica N principal </td> 
   <td colname="col2"> <p><i>Opcional</i>. Consulte la descripción del parámetro Valor N superior. </p> <p> <p>Nota:  Si introduce un valor en este parámetro, debe introducir un valor en el parámetro Nombre de dimensión y en el parámetro Valor N superior. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Valor N superior </td> 
   <td colname="col2"> <p><i>Opcional</i>. Cuando se rellena este parámetro, el servidor de informes <span class="keyword"> </span> se ejecuta en modo dinámico y genera informes para el número superior (especificado en este parámetro) de elementos para la dimensión especificada en el parámetro Nombre de dimensión, contando por la métrica especificada en el parámetro Métrica N superior. </p> <p>Ejemplo: Si introduce Página en el parámetro Nombre de dimensión, Sesiones en el parámetro Métrica N superior y 5 en este parámetro, el informe generado muestra las cinco páginas principales con el mayor número de sesiones. </p> <p> <p>Nota:  Si introduce un valor en este parámetro, debe introducir un valor en el parámetro Nombre de dimensión y en el parámetro Métrica N superior. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Usar sólo muestra local </td> 
   <td colname="col2"> <i>Opcional</i>. Indica si desea que <span class="keyword"> el servidor de informes </span> genere informes utilizando solo la muestra local del conjunto de datos. Si este parámetro se establece en true, podrá ver una muestra del conjunto de informes (sin colocar una carga en un servidor del área de trabajo de datos) para ver el aspecto del resultado sin tener que dedicar todo el tiempo necesario para procesar los datos. Esto funciona como una función de prueba. Las opciones son true o false. El valor predeterminado es false. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Ruta del espacio de trabajo </td> 
   <td colname="col2"> <p><i>Opcional</i>. Ubicación de una colección de espacios de trabajo para un conjunto de informes determinado. Esto resulta útil para mantener una única copia de los espacios de trabajo que deben generarse y distribuirse de varias formas, mediante el uso de archivos <span class="filepath"> Report.cfg </span> para varios conjuntos de informes. El directorio raíz de esta ruta puede ser cualquier carpeta de perfil. No introduzca una barra (\) al principio de la cadena de ruta. </p> <p>Ejemplo: Puede guardar los espacios de trabajo comunes para los conjuntos A y B en la carpeta <span class="filepath"> Informes\Común </span> y, a continuación, definir los archivos <span class="filepath"> Report.cfg </span> para dos conjuntos de informes diferentes, cada uno con una configuración de distribución y generación diferentes. En ambos <span class="filepath"> archivos Report.cfg </span> , se establecería el parámetro de ruta de espacio de trabajo en <i>nombre</i>de perfil \Reports\Common. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Archivo de salida XSL </td> 
   <td colname="col2"> <i>Opcional</i>. Ruta del archivo de salida que se crea al aplicar la plantilla <span class="wintitle"> XSL </span> al índice del informe. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Plantilla XSL </td> 
   <td colname="col2"> <p><i>Opcional</i>. Ruta del archivo de plantilla XSL que se aplicará al índice del informe. El <span class="filepath"> .xml transformado resultante </span> se escribe en el archivo de salida <span class="wintitle"> XSL especificado </span>. Consulte <a href="../../../home/c-rpt-oview/c-rpt-sample-files/c-rpt-sample-files.md#concept-a06b93f21c5d4888be335fa2281b2a87"> Archivos de muestra de informes </a> para ver un archivo de muestra. </p> <p> <p>Nota:  A menos que utilice una plantilla <span class="filepath"> .xsl </span> al generar los informes, todos los informes se distribuyen por correo electrónico como archivos adjuntos. </p> </p> </td> 
  </tr> 
 </tbody> 
</table>

