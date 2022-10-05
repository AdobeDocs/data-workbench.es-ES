---
description: Captura de la actividad en vínculos de sitios web de terceros para habilitar el análisis de salida de Target.
title: Seguimiento de salidas a vínculos externos
uuid: 523f5b4c-4600-4d44-82e7-4a8b2db2d266
exl-id: fd7434e9-cd66-408e-baa9-6a0df4039786
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '193'
ht-degree: 6%

---

# Seguimiento de salidas a vínculos externos{#tracking-exits-to-external-links}

{{eol}}

Captura de la actividad en vínculos de sitios web de terceros para habilitar el análisis de salida de Target.

Las páginas web pueden contener vínculos a sitios web de terceros, y se puede capturar la actividad de estos vínculos para habilitar el análisis de Salir de Target, especialmente en el caso de que el sitio de terceros sea responsable de pagar las tarifas de referencia cuando se reciban dichas referencias. Dado que el evento de clic se escribe en los archivos de registro del sistema de terceros de forma predeterminada, es necesario realizar modificaciones en el vínculo para que el evento de clic se capture localmente. El vínculo de terceros presente en el sitio web debe modificarse de la siguiente manera:

```
<A HREF=”https://www.myserver.com/PageExit.htm?v_eurl=https://www.othersite.com”>
```

Se hace referencia a [!DNL PageExit.htm] debe crearse y estructurarse para que contenga la siguiente secuencia de comandos:

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

Al realizar la solicitud de [!DNL PageExit.htm] , el valor v_eurl se recopila para fines de análisis. Además, cuando [!DNL PageExit.htm] se carga, redirige inmediatamente a la ubicación de destino de v_eurl especificada.

| Datos recopilados | Explicación | Ejemplo |
|---|---|---|
| v_eurl | Valor asociado con la variable de cadena de consulta v_eurl. Este valor representa la dirección URL de destino del vínculo presente en la página del HTML. | v_eurl=www.othersite.com |
