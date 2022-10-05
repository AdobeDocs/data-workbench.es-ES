---
description: Las variables de cadena de consulta se pueden agregar a una solicitud de JavaScript para recopilar mediciones adicionales cuando se realiza una solicitud.
title: Adquisición de información adicional
uuid: 0a8075e9-4986-42c4-b505-3985b433cf8e
exl-id: ad4f5e08-b7b7-4de3-b0c2-71440facb2d1
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '173'
ht-degree: 4%

---

# Adquisición de información adicional{#acquiring-additional-information}

{{eol}}

Las variables de cadena de consulta se pueden agregar a una solicitud de JavaScript para recopilar mediciones adicionales cuando se realiza una solicitud.

Estas variables se pueden agregar manualmente o mediante secuencia de comandos en la propia página.

Se puede añadir información adicional que se puede adquirir desde una página al objeto incrustado mediante una secuencia de comandos con el siguiente código como ejemplo:

```
<!-- BEGIN REFERENCE PAGE TAG-->
<script language="javascript">
var vlc = "0" //Capture Link Click  1=TRUE, 0=FALSE
var v = {};
v["_pn"] = "Application Form";
v["_1"] = “99.99”;
v["_2"] = "visa";
</script>

<script language="javascript" src=”https://www.myserver.com/path/to/zig.js" type="text/javascript"></script>
<noscript>

<img src="/path/to/zag.gif?Log=1&v_jd=1" border="0" width="1" height="1"/>
</noscript>
<!-- END REFERENCE PAGE TAG-->
```

En este ejemplo, las variables de script para v_1 y v_2 pueden derivarse de otra función dentro de la página web. Las variables se han insertado como ejemplos. Además de las mediciones de referencia adquiridas con cada solicitud, se adquirirían las siguientes mediciones ampliadas con la solicitud de la dirección URL anterior:

| Datos recopilados | Explicación | Ejemplo |
|---|---|---|
| v_pn= | Valor asociado con la variable de cadena de consulta v_pn | v_pn=Formulario de aplicación |
| v_1= | Valor asociado con la variable de cadena de consulta v_1 | v_1=99.99 |
| v_2= | Valor asociado con la variable de cadena de consulta v_2 | v_2=visa |
