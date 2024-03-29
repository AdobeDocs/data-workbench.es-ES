---
description: La llamada de ejecución de etiquetas de página de referencia se inserta en las páginas web para las que se desea recopilar datos de medición.
title: Añadir llamadas de ejecución de etiquetas de página de referencia
uuid: 8c682649-d1b1-40a6-a2b2-4ff5a92b732f
exl-id: a4f9ab2b-50e8-4e0b-9c87-80dffb697316
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '356'
ht-degree: 3%

---

# Añadir llamadas de ejecución de etiquetas de página de referencia{#adding-reference-page-tag-execution-calls}

{{eol}}

La llamada de ejecución de etiquetas de página de referencia se inserta en las páginas web para las que se desea recopilar datos de medición.

Debe incluirse en el cuerpo del documento del HTML y puede colocarse dentro de un pie de página de inclusión global, si corresponde. La variable [!DNL Reference Page Tag Execution Call] su equipo puede modificarlo para recopilar información adicional que podría identificarse durante las reuniones de recopilación de requisitos con el equipo de servicios de consultoría de Adobe.

Para facilitar la recopilación de datos mediante el uso de la variable [!DNL Reference Page Tag], complete los siguientes pasos:

1. Copie el siguiente código en el cuerpo del documento del HTML:

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

1. Modifique la ruta a la ubicación del [!DNL zig.js] y [!DNL zag.gif] archivos. Por ejemplo:

   ```
   //www.mysite.com/scripts/zig.js 
   //www.mysite.com/images/zag.gif 
   ```

Asegúrese de que se hayan configurado los encabezados de control de caché HTTP adecuados en el servidor web para garantizar que la variable [!DNL zig.js]y [!DNL zag.gif] el explorador no almacena en caché los archivos. Puede establecer la información del encabezado HTTP Cache-Control mediante uno de estos dos métodos. El primer método es establecer un encabezado HTTP mediante el servidor web. El segundo método es establecer un encabezado HTTP para cada página o objeto incrustado específico mediante una secuencia de comandos. Con el método de secuencias de comandos, la página web debe haberse creado con un lenguaje de programación como JSP o ASP. A continuación, se genera una secuencia de comandos para que la página envíe la información de encabezado adecuada. Este método contiene dos desventajas obvias: 1) todas las páginas deben estar codificadas para enviar el encabezado, y 2) las páginas no pueden ser HTML estáticos, lo que tiene algún efecto en el rendimiento del servidor web.

Los sitios web que se ejecutan en Microsoft IIS pueden agregar el encabezado HTTP adecuado a través de la Consola de administración de Microsoft. Los sitios web servidos desde servidores web de Netscape iPlanet pueden hacerlo editando el [!DNL obj.conf] dentro del directorio de configuración del sitio. El servidor web Apache proporciona a los webmasters la capacidad de personalizar encabezados HTTP usando el módulo mod_headers incluido, donde AOLServer se puede personalizar mediante el uso de módulos Tcl. Antes de implementar encabezados de control de caché HTTP, debe consultar la documentación específica de su plataforma de servidor web.

En general, el encabezado HTTP debe estructurarse de la siguiente manera:

```
Cache-Control: no-cache 
Pragma: no-cache 
Expires: -1
```
