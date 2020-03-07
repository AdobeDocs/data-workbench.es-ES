---
description: Capturar la actividad en vínculos de sitios web de terceros para habilitar el análisis de salida de Target.
solution: Analytics
title: Seguimiento de salidas a vínculos externos
topic: Data workbench
uuid: 523f5b4c-4600-4d44-82e7-4a8b2db2d266
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Seguimiento de salidas a vínculos externos{#tracking-exits-to-external-links}

Capturar la actividad en vínculos de sitios web de terceros para habilitar el análisis de salida de Target.

Las páginas web pueden contener vínculos a sitios web de terceros, y se puede capturar la actividad de estos vínculos para habilitar el análisis de Salir de Target, especialmente en el caso de que el sitio de terceros sea responsable de pagar las tarifas de referencia cuando se reciban dichas referencias. Dado que el evento click se escribe en los archivos de registro del sistema de terceros de forma predeterminada, es necesario realizar modificaciones en el vínculo para que el evento click se capture localmente. El vínculo de terceros presente en el sitio web debe modificarse de la siguiente manera:

```
<A HREF=”http://www.myserver.com/PageExit.htm?v_eurl=http://www.othersite.com”>
```

El [!DNL PageExit.htm] archivo al que se hace referencia debe crearse y estar estructurado para que contenga la siguiente secuencia de comandos:

```
<html> 
<head> 
 
<script> 
function getExitURLQuery(variable) 
{ 
 
var query = window.location.search.substring(1); 
var vars = query.split("&"); 
for (var i=0; i<vars.length; i++) 
{ 
var pair = vars[i].split("="); 
if (pair[0] == variable) 
{ 
return pair[1]; 
} 
 }  
} 
</script> 
 
<script> 
location.replace(getExitURLQuery("v_eurl")); 
</script>  
 
</head> 
</html>
```

Al realizar la solicitud del [!DNL PageExit.htm] archivo, el valor v_eurl se recopila con fines de análisis. Además, cuando [!DNL PageExit.htm] se carga, inmediatamente redirige a la ubicación de destino v_eurl especificada.

| Datos recopilados | Explicación | Ejemplo |
|---|---|---|
| v_eurl | Valor asociado con la variable de cadena de consulta v_eurl. Este valor representa la dirección URL de destino del vínculo presente en la página HTML. | v_eurl=www.othersite.com |

