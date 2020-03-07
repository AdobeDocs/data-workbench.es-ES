---
description: La etiqueta de página de referencia consiste en una secuencia de comandos de ejecución de etiquetas de página que reside en un servidor web y, cuando se llama, resulta en la recopilación de todos los datos del lado del cliente para la página solicitada por el visitante del sitio.
solution: Analytics
title: Edición del script de ejecución de etiquetas de página de referencia
topic: Data workbench
uuid: 0db00b89-e420-423d-9b88-8b724baa828f
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Edición del script de ejecución de etiquetas de página de referencia{#editing-the-reference-page-tag-execution-script}

La etiqueta de página de referencia consiste en una secuencia de comandos de ejecución de etiquetas de página que reside en un servidor web y, cuando se llama, resulta en la recopilación de todos los datos del lado del cliente para la página solicitada por el visitante del sitio.

Puede modificar el [!DNL Reference Page Tag Execution Script] para recopilar información adicional que se puede identificar durante la recopilación de requisitos con el equipo de servicios de consultoría de Adobe. El tamaño [!DNL Reference Page Tag Execution Script] es relativamente pequeño para evitar grandes adiciones de descarga a las páginas web.

Se le proporciona el siguiente [!DNL Reference Page Tag Execution Script] código en un archivo llamado [!DNL zig.js]:

```
//REFERENCE PAGE TAG 
// CONSTANTS 
var ct = "<img src="; 
var cd = "[PATH_TO_WEB_SERVER]"; //this should contain the domain of 
                               //the web site that will host the 
                                //page tag 
 
var cu = "[PATH_TO_WEB_PAGE_TAG_CODE]/zag.gif?Log=1";  
                                 //this should contain the full path to 
                                 //the zag.gif file (excluding domain) 
                                 //and include the query string of log=1 
var ce = ">"; 
var c = {}; 
c["sw"] = screen.width; 
c["sh"] = screen.height; 
c["cd"] = screen.colorDepth; 
var co = ""; 
 
for ( cKey in c ) { 
co = co+"&"+cKey+"="+escape(c[cKey]); 
} 
document.write(ct,cd,cu,co,ce); 
 
var d = {}; 
d["dt"] = document.title; 
d["dr"] = document.referrer; 
d["cb"] = new Date().getTime(); 
var vo = ""; 
 
if (typeof v != "undefined") { 
for ( vKey in v ) { 
vo = vo+"&"+vKey+"="+escape(v[vKey]); 
} 
} 
for ( dKey in d ) { 
vo = vo+"&"+dKey+"="+escape(d[dKey]); 
} 
document.write(ct,cd,cu,vo,ce); 
//END REFERENCE PAGE TAG 
```

Para facilitar la recopilación de datos mediante el uso del [!DNL Reference Page Tag], complete los siguientes pasos:

1. Cree o coloque el archivo de imagen de 1 píxel por 1 píxel denominado [!DNL zag.gif] en un directorio presente en el servidor web.
1. Modifique la variable cd para que haga referencia al dominio correspondiente del sitio web o al dominio de servicios gestionados por Adobe desde el que se hace referencia al [!DNL zag.gif] archivo. La referencia al archivo se crea mediante la ejecución de las funciones del [!DNL zig.js] archivo. Por ejemplo:

   ```
   //www.mysite.com
   ```

1. Modifique la variable cu para hacer referencia a la ruta de acceso adecuada a la ubicación del [!DNL zag.gif] archivo. Por ejemplo

   ```
   /scripts
   ```

1. Asegúrese de que se establezcan los encabezados de control de caché adecuados para los [!DNL zag.gif] archivos y [!DNL zig.js] .
