---
description: La llamada de ejecución de etiquetas de página de referencia se inserta en las páginas web para las que se desea recopilar datos de medición.
solution: Analytics
title: Adición de llamadas de ejecución de etiquetas de página de referencia
topic: Data workbench
uuid: 8c682649-d1b1-40a6-a2b2-4ff5a92b732f
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Adición de llamadas de ejecución de etiquetas de página de referencia{#adding-reference-page-tag-execution-calls}

La llamada de ejecución de etiquetas de página de referencia se inserta en las páginas web para las que se desea recopilar datos de medición.

Debe incluirse en el cuerpo del documento HTML y puede colocarse dentro de un pie de página de inclusión global, si corresponde. Su equipo [!DNL Reference Page Tag Execution Call] puede modificarlo para recopilar información adicional que podría identificarse durante las reuniones de recopilación de requisitos con el equipo de servicios de consultoría de Adobe.

Para facilitar la recopilación de datos mediante el uso del [!DNL Reference Page Tag], complete los siguientes pasos:

1. Copie el siguiente código en el cuerpo del documento HTML:

   ```
   <!--//BEGIN REFERENCE PAGE TAG--> 
   <script language="javascript"> 
   var vlc = "0" //Capture Link Click  1=TRUE, 0=FALSE 
   var v = {}; 
   </script> 
   
   <!--//MODIFIY PATH TO ZIG.JS--> 
   <script language="javascript" src="/path/to/zig.js" type="text/javascript"></script> 
   <!--//END REFERENCE PAGE TAG--> 
   
   <noscript> 
   <img src="/path/to/zag.gif?Log=1&v_jd=1" border="0" width="1" height="1"/> 
   </noscript> 
   <!-- END REFERENCE PAGE TAG-->
   ```

1. Modifique la ruta a la ubicación de los [!DNL zig.js] archivos y [!DNL zag.gif] . Por ejemplo:

   ```
   //www.mysite.com/scripts/zig.js 
   //www.mysite.com/images/zag.gif 
   ```

Asegúrese de que los encabezados de control de caché HTTP adecuados se hayan establecido en el servidor web para garantizar que el explorador no almacene los archivos [!DNL zig.js]y [!DNL zag.gif] los archivos en caché. Puede establecer la información del encabezado HTTP Cache-Control mediante uno de los dos métodos. El primer método es establecer un encabezado HTTP a través del servidor web. El segundo método consiste en establecer un encabezado HTTP para cada página específica u objeto incrustado mediante una secuencia de comandos. Con el método de secuencias de comandos, la página web debe haberse creado con un lenguaje de programación como JSP o ASP. A continuación, se genera un script para que la página envíe la información de encabezado adecuada. Este método conlleva dos inconvenientes obvios: 1) todas las páginas deben codificarse para enviar el encabezado, y 2) las páginas no pueden ser HTML estático, lo que tiene algún efecto en el rendimiento del servidor web.

Los sitios Web que se ejecutan en Microsoft IIS pueden agregar el encabezado HTTP adecuado a través de Microsoft Management Console. Los sitios web que se proporcionan desde servidores web de Netscape iPlanet pueden hacerlo editando el archivo [!DNL obj.conf] dentro del directorio de configuración del sitio. El servidor web Apache proporciona a los webmasters la capacidad de personalizar encabezados HTTP utilizando el módulo mod_headers incluido, donde AOLServer se puede personalizar mediante el uso de módulos Tcl. Antes de implementar los encabezados de control de caché HTTP, debe consultar la documentación específica de la plataforma de servidor web.

En general, el encabezado HTTP debe estructurarse de la siguiente manera:

```
Cache-Control: no-cache 
Pragma: no-cache 
Expires: -1
```

