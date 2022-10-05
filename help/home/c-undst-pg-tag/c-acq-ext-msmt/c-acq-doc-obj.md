---
description: Con el Modelo de objetos de documento JavaScript, se pueden utilizar métodos de secuencias de comandos adicionales para aumentar la solicitud del archivo zig.js.
title: Adquisición de objetos de documento
uuid: 7681c337-b147-4937-9d9c-0ff48d9bdd00
exl-id: eae6609c-be86-44cf-a1a1-69ffb43231fa
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '160'
ht-degree: 5%

---

# Adquisición de objetos de documento{#acquiring-document-objects}

{{eol}}

Con el Modelo de objetos de documento JavaScript, se pueden utilizar métodos de secuencias de comandos adicionales para aumentar la solicitud del archivo zig.js.

Se puede hacer referencia a información como el valor de las etiquetas META, los valores de ID de las etiquetas DIV, etc., por nombre y recopilarlos como variables para su uso en el análisis. Por ejemplo, para capturar dinámicamente la información contenida en el elemento META del documento HTML, puede utilizar la siguiente sintaxis de JavaScript:

```
<!-- BEGIN REFERENCE PAGE TAG-->
<script language="javascript">
var m0 = document.getElementsByTagName('META')[0]; //define the first instance of META
var metacontent = m0.getAttribute('content'); //get the ‘content’ value of META
var vlc = "0" //Capture Link Click  1=TRUE, 0=FALSE
var v = {};
v["_1"] = metacontent;
</script>

<script language="javascript" src=”https://www.myserver.com/path/to/zig.js" type="text/javascript"></script>

<noscript>
<img src="/path/to/zag.gif?Log=1&v_jd=1" border="0" width="1" height="1"/>
</noscript>

<!-- END REFERENCE PAGE TAG-->
```

| Datos recopilados | Explicación | Ejemplo |
|---|---|---|
| v_1= | Valor asociado con la variable de cadena de consulta METAVALUE. Este valor representa los datos dentro del elemento META del documento del HTML. | v_1=Esta página proporciona contenido relacionado con la página de agradecimiento del pedido. |

Una vez recopilados los datos, se puede configurar el servidor de Data Workbench para procesar estos datos de medición con fines de análisis e informes.
