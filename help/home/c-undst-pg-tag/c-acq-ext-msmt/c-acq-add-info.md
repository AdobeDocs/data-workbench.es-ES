---
description: Las variables de cadena de consulta se pueden agregar a una solicitud de JavaScript para recopilar medidas adicionales cuando se realiza una solicitud.
solution: Analytics
title: Adquisición de información adicional
topic: Data workbench
uuid: 0a8075e9-4986-42c4-b505-3985b433cf8e
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Adquisición de información adicional{#acquiring-additional-information}

Las variables de cadena de consulta se pueden agregar a una solicitud de JavaScript para recopilar medidas adicionales cuando se realiza una solicitud.

Estas variables pueden agregarse manualmente o mediante secuencia de comandos en la propia página.

Se puede añadir información adicional que se puede adquirir desde una página al objeto incrustado mediante una secuencia de comandos utilizando el siguiente código como ejemplo:

```
<!-- BEGIN REFERENCE PAGE TAG--> 
<script language="javascript"> 
var vlc = "0" //Capture Link Click  1=TRUE, 0=FALSE 
var v = {}; 
v["_pn"] = "Application Form"; 
v["_1"] = “99.99”; 
v["_2"] = "visa"; 
</script> 
 
<script language="javascript" src=”http://www.myserver.com/path/to/zig.js" type="text/javascript"></script> 
<noscript> 
 
<img src="/path/to/zag.gif?Log=1&v_jd=1" border="0" width="1" height="1"/> 
</noscript> 
<!-- END REFERENCE PAGE TAG-->
```

En este ejemplo, las variables de secuencia de comandos para v_1 y v_2 pueden derivarse de otra función dentro de la página web. Las variables se han insertado como ejemplos. Además de las mediciones de referencia adquiridas con cada solicitud, se obtendrían las siguientes mediciones extensas con la solicitud de la dirección URL anterior:

| Datos recopilados | Explicación | Ejemplo |
|---|---|---|
| v_pn= | Valor asociado con la variable de cadena de consulta v_pn | v_pn=Formulario de solicitud |
| v_1= | Valor asociado con la variable de cadena de consulta v_1 | v_1=99.99 |
| v_2= | Valor asociado con la variable de cadena de consulta v_2 | v_2=visa |

