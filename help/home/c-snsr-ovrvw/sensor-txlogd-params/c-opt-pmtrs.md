---
description: Información sobre los parámetros opcionales del archivo txlogd.conf del sensor.
title: Parámetros opcionales
uuid: 8515a571-93ce-49cd-9ded-c9273259d0ee
exl-id: 5141f215-979c-4eb8-8c2c-94eef5815743
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '1484'
ht-degree: 1%

---

# Parámetros opcionales{#optional-parameters}

Información sobre los parámetros opcionales del archivo txlogd.conf del sensor.

<table id="table_5FF491A7A6C24E43A06A5C344BF05430"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parámetro </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> AddressFilter </td> 
   <td colname="col2"> <p>Permite filtrar direcciones IP especificadas. </p> <p>Al filtrar una dirección determinada, no se registra un "paquete". Esta función elimina los agentes internos o supervisados antes del procesamiento de registros, lo que aumenta la velocidad de procesamiento de registros y reduce los requisitos de almacenamiento de datos. Al especificar direcciones, pueden utilizarse caracteres comodín. </p> <p>Ejemplo: <span class="filepath"> AddressFilter 10.0.0.000</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ContentFilterInclude </p> <p>ContentFilterExclude </p> </td> 
   <td colname="col2"> <p>Especifique si se incluyen o excluyen ciertos tipos de contenido del registro. </p> <p>Los valores de parámetro coinciden con los prefijos en relación con el tipo de contenido de la respuesta. </p> <p>Por ejemplo, "image/" coincide con todos los tipos de contenido de imagen, mientras que "image/gif" coincide únicamente con ese tipo exactamente. Cuando se producen varias coincidencias para un tipo de contenido determinado, se utiliza la coincidencia más específica. Por lo tanto, podría poner "image/gif" en el parámetro ContentFilterInclude y "image/" en el parámetro ContentFilterExclude y se permiten las respuestas "image/gif", pero todos los demás tipos de imágenes se filtran hacia fuera. </p> <p>Ejemplo: <span class="filepath"> ContentFilterInclude *</span> </p> <p>Ejemplo: <span class="filepath"> ContentFilterExclude image/,text/css,application/x-javascript</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> DebugLogPath </td> 
   <td colname="col2"> <p>Establezca este parámetro solo cuando trabaje con los servicios de consultoría de Adobe. </p> <p>Habilita el registro de depuración para el módulo web y el transmisor. </p> <p>Utilice este parámetro cuando el <span class="wintitle"> Sensor</span> no funcione correctamente. Una vez establecido este parámetro, debe crear un archivo vacío en la ubicación de ruta especificada y darle derechos de escritura para todos los usuarios. Por ejemplo (dentro de un shell unix en el servidor web): 
     <ul id="ul_7A067014A78048BF9D2F23DC66FF9E24"> 
      <li id="li_11C51EB9B9CC431585ECE9E8648F6122"><span class="filepath"> % cd /var/log</span> </li> 
      <li id="li_C56B2B5D49A543DBB258C5DE099B4AE5"><span class="filepath"> % touch vslog.txt</span> </li> 
      <li id="li_DA914383F813453AB6EF4F89279FD786"><span class="filepath"> % chmod a+w vslog.txt</span> </li> 
     </ul> </p> <p>Debe habilitar el registro de depuración solo durante un breve período de tiempo, tras el cual el archivo de registro debe enviarse a los servicios de consultoría de Adobe para que se analicen. </p> <p>Ejemplo: <span class="filepath"> DebugLogPath /var/log/vslog.txt</span> </p> <p>Adobe recomienda que este parámetro se establezca primero en un entorno de prueba para determinar el efecto en el sistema. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> DisableField </td> 
   <td colname="col2"> <p>Desactiva el campo especificado </p> <p>Los usuarios pueden eliminar campos que no utilizan o que no desean almacenar. Si el campo toma valores de cadena, al desactivarlo, se pasa una cadena en blanco. Si el campo toma valores numéricos, al desactivarlo, se pasa el número cero (0). Puede desactivar los campos siguientes: 
     <ul id="ul_4537B345EFAE449A9946DA0B52EA5C43"> 
      <li id="li_D674BC1982344C49B25A73EFF095C34A">sc-status </li> 
      <li id="li_6D647C845EB54B1B84C756DCDD7DD4CC">x-new-visitor </li> 
      <li id="li_65EB695B223040BCB9888375354B6E8B">x-trackingid </li> 
      <li id="li_41197A9CB961496B9CD26AA8457233FD">sc-bytes </li> 
      <li id="li_DCD45D7E21964B959299494FA719F453">c-ip </li> 
      <li id="li_7650796C6246484C8267ED9923596AFB">cs-method </li> 
      <li id="li_8941FCBBAA5E42EA9F04DA06EB91CAC5">cs-uri-stem </li> 
      <li id="li_A10438D2DEBB4ADFB574BF7094F9F0C4">cs-uri-query </li> 
      <li id="li_1D83BA59AC8543319D1966BB8ED1D931">s-dns </li> 
      <li id="li_34A23CE1944F4AEFBE7D74E8D6D5BEE6">cs(referrer) </li> 
      <li id="li_B85D93C381BD440F82C711C9A6D56CE9">cs(cookie) </li> 
      <li id="li_18D9C084450149D6A8713EBDA0C02E5B">cs(user-agent) </li> 
      <li id="li_A175CAF03E51473E990BE4F31F198B42">cs(useragent) </li> 
      <li id="li_ED38ED31B2644F2FA1C86FF93ADB9CEF">sc(tipo de contenido) </li> 
      <li id="li_1173C0027C8A4638BDF35E9719CD9D4C">x-experimentar </li> 
     </ul> </p> <p>Ejemplo: <span class="filepath"> DisableField x-trackingid</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ExpFile </td> 
   <td colname="col2"> <p>Ruta al archivo de configuración de Experimento controlado. </p> <p>Ejemplo: <span class="filepath"> ExpFile C:\VisualSensor\experiment.txt</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ExpCookieURL </td> 
   <td colname="col2"> <p>Recurso que, cuando se solicita, genera un nuevo ID de seguimiento y el usuario se coloca en un grupo de experimentos. </p> <p> <p>Nota:  Este recurso no tiene que existir físicamente en el servidor web. </p> </p> <p>Ejemplo: <span class="filepath"> ExpCookieURL /setcookie.htm</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ExpPartialMatch </td> 
   <td colname="col2"> <p>Si desea permitir que los experimentos controlados reasignen todo el sitio o un subdirectorio completo del sitio a otra ubicación, establezca este parámetro en "activado". El valor predeterminado es "off". </p> <p>Ejemplo: <span class="filepath"> ExpPartialMatch off</span> </p> <p> <p>Nota:  Tenga mucho cuidado al configurar este parámetro en "on". </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> LogAllNewUsers </td> 
   <td colname="col2"> <p>Determina si se registra el primer clic de cada nuevo usuario aunque el usuario solicite un tipo de documento filtrado por el parámetro ContentFilterExclude. </p> <p>El valor predeterminado es "no". </p> <p>Normalmente, los archivos de imagen se filtran mediante el parámetro ContentFilterExclude . Si LogAllNewUsers está establecido en "sí" y el primer documento que un nuevo usuario obtiene del servidor es una imagen, esa solicitud se registra. Si el parámetro LogAllNewUsers está establecido en "no" o no está establecido (y suponiendo que las imágenes están filtradas por el parámetro ContentFilterExclude) y el primer documento que un nuevo usuario obtiene del servidor es una imagen, esa solicitud no se registra. </p> <p>Ejemplo: <span class="filepath"> LogAllNewUsers no</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> MaxPageLoadTime </td> 
   <td colname="col2"> <p>Cantidad de tiempo en segundos que el transmisor espera para enviar el siguiente lote de paquetes. </p> <p>El valor predeterminado es 15. </p> <p>Ejemplo: <span class="filepath"> MaxPageLoadTime 15</span> </p> <p> <p>Nota:  No cambie este valor de parámetro sin ponerse en contacto primero con los Servicios de consultoría de Adobe. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> PrivacyID </td> 
   <td colname="col2"> <p>Permite desactivar el seguimiento de visitantes, que se puede utilizar para cumplir con las políticas de exclusión. </p> <p>Cuando está habilitado, el <span class="wintitle"> Sensor</span> no registra un "paquete" para ningún visitante cuya cookie V1st esté configurada con el ID de privacidad especificado. Debido a que no se registra información para esos visitantes, no se envía ninguna información sobre esos visitantes al <span class="keyword"> servidor de Data Workbench</span> para su procesamiento. </p> <p>Para habilitar esta función, debe completar los siguientes pasos: 
     <ol id="ol_5D658C5E4AB14F419029E0FFC52F1310"> 
      <li id="li_BF056439F92148169BF592731264C3CD"> PrivacyID debe definirse con un valor de 0 (cero) en el archivo <span class="filepath"> txlogd.conf</span> para el <span class="wintitle"> Sensor</span>. <p>Ejemplo: <span class="filepath"> PrivacyID 0</span> </p> </li> 
      <li id="li_3E20F068C2F94512A92F284C80273B1C">Los propietarios de sitios web deben escribir código para establecer las cookies de visitante (V1st) de manera que el valor de ID de cookie coincida con el valor de PrivacyID definido "<span class="filepath"> txlogd.conf</span>". </li> 
     </ol> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> SiteTest </td> 
   <td colname="col2"> <p>Ubicación a la que el transmisor (txlogd) envía periódicamente solicitudes para ver si el sitio web funciona correctamente. </p> <p>Tenga en cuenta que la ubicación se especifica en el siguiente formato, no como URL: </p> <p>http,<i>serverAddress,port/resource</i> </p> <p>donde <i>serverAddress</i> es un nombre de servidor o una dirección IP, <i>port</i> es el puerto de escucha HTTP del servidor y <i>resource</i> es el recurso específico que se va a solicitar (puede incluir una cadena de consulta). </p> <p>Puede especificar varias líneas de SiteTest. </p> <p>Ejemplo: <span class="filepath"> SiteTest http,localhost,80,/test.html</span> </p> <p> <p>Nota:  Solo se admite http en este momento. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> TrackingCookie </td> 
   <td colname="col2"> <p>Nombre de la cookie configurada en el explorador del visitante. </p> <p>El valor predeterminado es "v1st". </p> <p>Ejemplo: <span class="filepath"> TrackingCookie v1st</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> VerifyCertName </td> 
   <td colname="col2"> <p>Indica si se debe validar el servidor con el parámetro CertName </p> <p>El valor predeterminado es "activado". </p> <p>Ejemplo: <span class="filepath"> VerifyCertName en</span> </p> </td> 
  </tr> 
 </tbody> 
</table>

<table id="table_598C3CDA5AA440228AF88C3BE4A8F77C"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parámetro </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> IISCaptureBytesSent </td> 
   <td colname="col2"> <p>Establezca este parámetro solo cuando trabaje con los servicios de consultoría de Adobe. </p> <p>Indica al sensor <span class="wintitle"> de IIS</span> cuál de los dos posibles "ganchos" de registro debe utilizarse para registrar un paquete </p> <p>Utilice este parámetro cuando el sensor <span class="wintitle"> de IIS</span> no esté registrando los paquetes correctamente. Este parámetro se establecería en "off" si el enlace de registro predeterminado no funcionaba correctamente. El valor predeterminado es "activado". </p> <p>Ejemplo: <span class="filepath"> IISCaptureBytesSent en</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> IISUseAlternateHandler </td> 
   <td colname="col2"> <p>Establezca este parámetro solo cuando trabaje con los servicios de consultoría de Adobe. </p> <p>Indica al <span class="wintitle"> Sensor</span> cuál de los dos posibles "ganchos" debe utilizarse para configurar la cookie v1st. </p> <p>Utilice este parámetro cuando el sensor <span class="wintitle"> de IIS</span> no esté configurando correctamente la cookie v1st. Este parámetro se establecería en "sí" si el vínculo predeterminado no configuraba correctamente la cookie v1st. El valor predeterminado es "no". </p> <p>Ejemplo: <span class="filepath"> IISUseAlternateHandler no</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>NewUserCacheControl </p> <p>CacheControl </p> </td> 
   <td colname="col2"> <p>De forma predeterminada, <span class="wintitle"> Sensor</span> envía encabezados de respuesta de control de caché en cada solicitud. Cuando la función de control de caché está habilitada, <span class="wintitle"> Sensor</span> envía un encabezado Expires con un valor de Thu, 1 de diciembre de 1994 16:00:00 GMT al explorador. </p> <p>Puede modificar las cadenas de respuesta según lo desee editando las dos líneas siguientes en el archivo <span class="filepath"> txlogd.conf</span>: </p> <p> <span class="filepath"> </span> <i>&lt;&gt; NewUserCacheControlstring1</span>&gt;</i><span class="filepath"> </span></p> <p> <span class="filepath"> </span> <i>&lt;&gt; CacheControlstring2</span>&gt;</i><span class="filepath"> </span></p> <p>Ejemplo: </p> <p> <span class="filepath"> NewUserCacheControl no-cache=Set-Cookie</span> </p> <p> <span class="filepath"> CacheControl private,max-age=0,must-revalidate</span> </p> <p>Para desactivar el envío de encabezados de respuesta de control de caché, escriba un guión para cada línea como se muestra a continuación: </p> <p> <span class="filepath"> NewUserCacheControl -</span> </p> <p> <span class="filepath"> CacheControl -</span> </p> </td> 
  </tr> 
 </tbody> 
</table>

<table id="table_88696CCA93874BB683538BD614E07890"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> En este parámetro... </th> 
   <th colname="col2" class="entry"> Especifique... </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> ApacheUseAlternateHandler </td> 
   <td colname="col2"> <p>Establezca este parámetro solo cuando trabaje con los servicios de consultoría de Adobe. </p> <p>Indica al <span class="wintitle"> Sensor</span> cuál de los dos posibles "ganchos" debe utilizarse para configurar la cookie v1st. </p> <p>Utilice este parámetro cuando el sensor <span class="wintitle"> de Apache</span> no esté configurando correctamente la cookie v1st. Este parámetro se establecería en "sí" si el vínculo predeterminado no configuraba correctamente la cookie v1st. El valor predeterminado es "no". </p> <p>Ejemplo: <span class="filepath"> ApacheUseAlternateHandler no</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ApacheUseAmbasHandlers </td> 
   <td colname="col2"> <p>Establezca este parámetro solo cuando trabaje con los servicios de consultoría de Adobe. </p> <p>Indica al <span class="wintitle"> Sensor</span> que intente configurar la cookie v1st en ambos ganchos. </p> <p>Utilice este parámetro cuando el sensor <span class="wintitle"> de Apache</span> no esté configurando correctamente la cookie v1st. El valor predeterminado es "sí". </p> <p>Si se establece en "sí" y la cookie v1st no se establece correctamente en el primer vínculo, se utiliza el segundo vínculo. Si se establece en "no", establecería el parámetro ApacheUseAlternateHandler para indicar qué vínculo utilizar para establecer la cookie v1st. </p> <p>Ejemplo: <span class="filepath"> ApacheUseAmbasHandlers yes</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>NewUserCacheControl </p> <p>CacheControl </p> </td> 
   <td colname="col2"> <p>De forma predeterminada, <span class="wintitle"> Sensor</span> envía encabezados de respuesta de control de caché en cada solicitud. Cuando la función de control de caché está habilitada, <span class="wintitle"> Sensor</span> envía un encabezado Expires con un valor de Thu, 1 de diciembre de 1994 16:00:00 GMT al explorador. </p> <p>Puede modificar las cadenas de respuesta según lo desee editando las dos líneas siguientes en el archivo <span class="filepath"> txlogd.conf</span>: </p> <p> <span class="filepath"> </span> <i>&lt;&gt; NewUserCacheControlstring1</span>&gt;</i><span class="filepath"> </span></p> <p> <span class="filepath"> </span> <i>&lt;&gt; CacheControlstring2</span>&gt;</i><span class="filepath"> </span></p> <p>Ejemplo: </p> <p> <span class="filepath"> NewUserCacheControl no-cache=Set-Cookie</span> </p> <p> <span class="filepath"> CacheControl private,max-age=0,must-revalidate</span> </p> <p>Para desactivar el envío de encabezados de respuesta de control de caché, escriba un guión para cada línea como se muestra a continuación: </p> <p> <span class="filepath"> NewUserCacheControl -</span> </p> <p> <span class="filepath"> CacheControl -</span> </p> <p> <p>Nota:  Adobe recomienda que no deshabilite esta función. </p> </p> </td> 
  </tr> 
 </tbody> 
</table>

<table id="table_BF01F6265B8544DA9D9AD2C80A64C0F3"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> En este parámetro... </th> 
   <th colname="col2" class="entry"> Especifique... </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> ApacheUseAlternateHandler </td> 
   <td colname="col2"> <p>Establezca este parámetro solo cuando trabaje con los servicios de consultoría de Adobe. </p> <p>Indica al <span class="wintitle"> Sensor</span> cuál de los dos posibles "ganchos" debe utilizarse para configurar la cookie v1st. </p> <p>Utilice este parámetro cuando el sensor <span class="wintitle"> de Apache</span> no esté configurando correctamente la cookie v1st. Este parámetro se establecería en "sí" si el vínculo predeterminado no configuraba correctamente la cookie v1st. El valor predeterminado es "no". </p> <p>Ejemplo: <span class="filepath"> ApacheUseAlternateHandler no</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ApacheUseAmbasHandlers </td> 
   <td colname="col2"> <p>Establezca este parámetro solo cuando trabaje con los servicios de consultoría de Adobe. </p> <p>Indica al <span class="wintitle"> Sensor</span> que intente configurar la cookie v1st en ambos ganchos. </p> <p>Utilice este parámetro cuando el sensor <span class="wintitle"> de Apache</span> no esté configurando correctamente la cookie v1st. El valor predeterminado es "sí". </p> <p>Si se establece en "sí" y la cookie v1st no se establece correctamente en el primer vínculo, se utiliza el segundo vínculo. Si se establece en "no", establecería el parámetro ApacheUseAlternateHandler para indicar qué vínculo utilizar para establecer la cookie v1st. </p> <p>Ejemplo: <span class="filepath"> ApacheUseAmbasHandlers yes</span> </p> </td> 
  </tr> 
 </tbody> 
</table>
