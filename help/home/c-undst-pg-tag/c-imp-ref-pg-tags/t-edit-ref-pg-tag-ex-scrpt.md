---
description: La etiqueta de página de referencia consiste en un script de ejecución de etiquetas de página que reside en un servidor web y, cuando se llama, resulta en la recopilación de todos los datos del lado del cliente para la página solicitada por el visitante del sitio.
title: Edición del script de ejecución de etiquetas de página de referencia
uuid: 0db00b89-e420-423d-9b88-8b724baa828f
exl-id: bc922b59-716e-4e92-84b5-59a52620df03
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '231'
ht-degree: 7%

---

# Edición del script de ejecución de etiquetas de página de referencia{#editing-the-reference-page-tag-execution-script}

La etiqueta de página de referencia consiste en un script de ejecución de etiquetas de página que reside en un servidor web y, cuando se llama, resulta en la recopilación de todos los datos del lado del cliente para la página solicitada por el visitante del sitio.

Puede modificar el [!DNL Reference Page Tag Execution Script] para recopilar información adicional que se puede identificar durante las reuniones de recopilación de requisitos con el equipo de servicios de consultoría de Adobe. El [!DNL Reference Page Tag Execution Script] es relativamente pequeño en tamaño para evitar grandes adiciones de descarga a las páginas web.

El siguiente código [!DNL Reference Page Tag Execution Script] se proporciona en un archivo llamado [!DNL zig.js]:

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

Para facilitar la recopilación de datos mediante el uso de [!DNL Reference Page Tag], complete los siguientes pasos:

1. Cree o coloque el archivo de imagen de 1 píxel por 1 píxel llamado [!DNL zag.gif] en un directorio presente en el servidor web.
1. Modifique la variable cd para hacer referencia al dominio apropiado del sitio web o del dominio de servicios administrados de Adobe desde el cual se hace referencia al archivo [!DNL zag.gif]. La referencia al archivo se crea mediante la ejecución de las funciones del archivo [!DNL zig.js]. Por ejemplo:

   ```
   //www.mysite.com
   ```

1. Modifique la variable cu para hacer referencia a la ruta adecuada a la ubicación del archivo [!DNL zag.gif]. Por ejemplo

   ```
   /scripts
   ```

1. Asegúrese de que se hayan establecido los encabezados de control de caché adecuados para los archivos [!DNL zag.gif] y [!DNL zig.js].
