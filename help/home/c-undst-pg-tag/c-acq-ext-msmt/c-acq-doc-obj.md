---
description: Con el Modelo de objetos de documento de JavaScript, se pueden utilizar métodos de secuencias de comandos adicionales para aumentar la solicitud del archivo zig.js.
solution: Analytics
title: Adquisición de objetos de documento
topic: Data workbench
uuid: 7681c337-b147-4937-9d9c-0ff48d9bdd00
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Adquisición de objetos de documento{#acquiring-document-objects}

Con el Modelo de objetos de documento de JavaScript, se pueden utilizar métodos de secuencias de comandos adicionales para aumentar la solicitud del archivo zig.js.

Se puede hacer referencia por nombre a información como el valor de las etiquetas META, los valores de ID de las etiquetas DIV, etc., y recopilarla como variables para su uso en el análisis. Por ejemplo, para capturar dinámicamente la información contenida en el elemento META del documento HTML, puede utilizar la siguiente sintaxis de JavaScript:

```
<!-- BEGIN REFERENCE PAGE TAG--> 
<script language="javascript"> 
var m0 = document.getElementsByTagName('META')[0]; //define the first instance of META 
var metacontent = m0.getAttribute('content'); //get the ‘content’ value of META 
var vlc = "0" //Capture Link Click  1=TRUE, 0=FALSE 
var v = {}; 
v["_1"] = metacontent; 
</script> 
 
<script language="javascript" src=”http://www.myserver.com/path/to/zig.js" type="text/javascript"></script> 
 
<noscript> 
<img src="/path/to/zag.gif?Log=1&v_jd=1" border="0" width="1" height="1"/> 
</noscript> 
 
<!-- END REFERENCE PAGE TAG-->
```

| Datos recopilados | Explicación | Ejemplo |
|---|---|---|
| v_1= | Valor asociado con la variable de cadena de consulta METAVALUE. Este valor representa los datos dentro del elemento META del documento HTML. | v_1=Esta página proporciona contenido relacionado con la página de agradecimiento del pedido. |

Una vez recopilados los datos, puede configurar el servidor del área de trabajo de datos para procesar estos datos de medición con fines de análisis e informes.
