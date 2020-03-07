---
description: Las páginas Web suelen estructurarse con lenguaje de programación ASP (páginas de servidor activas).
solution: Analytics
title: Información específica de ASP
topic: Data workbench
uuid: 552288cb-b775-4121-8869-322f2a26932b
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Información específica de ASP{#asp-specific-information}

Las páginas Web suelen estructurarse con lenguaje de programación ASP (páginas de servidor activas).

ASP es una tecnología de Microsoft que se ejecuta en IIS (Internet Information Services). Cuando un explorador solicita un archivo ASP, IIS pasa la solicitud al motor ASP. El motor ASP lee el archivo ASP, línea por línea, y ejecuta las secuencias de comandos del archivo. Por último, el archivo ASP se devuelve al explorador como HTML sin formato. ASP proporciona objetos RESPOND o REQUEST que, además de otros usos, permiten la respuesta o solicitud de consultas de usuario o datos enviados desde formularios HTML.

En algunos casos, es posible que no desee anexar los valores introducidos en los formularios a la dirección URL que se muestra en la barra de direcciones del navegador de un usuario o que se puede ver en el propio código HTML. JavaScript simple del lado del servidor le permite anexar nombres de campos de formulario y sus respectivos valores al archivo de registro sin ponerlos a disposición en el navegador del usuario ni incrustarlos en el archivo HTML. Para capturar los valores reales del formulario ingresados en formularios concretos dentro del sitio web, se deben agregar unas pocas líneas de código para anexar los valores del formulario a la solicitud de registro.

Dentro de la página de procesamiento de un formulario, incluya el siguiente código para anexar los valores de formulario introducidos a los datos de la solicitud (además de escribir los valores de formulario enviados en una base de datos externa u otra ubicación):

```
var sName= Request.Form("Name"); 
var sCity= Request.Form("City"); 
var sState= Request.Form("State"); 
var sZip= Request.Form("Zip"); 
 
Response.AppendToLog("&v_1=" +  sName); 
Response.AppendToLog("&v_2=" +  sCity); 
Response.AppendToLog("&v_3=" +  sState); 
Response.AppendToLog("&v_4=" +  sZip);
```

Este proceso anexaría los valores del formulario tal como se definen a los datos de solicitud de la [!DNL Form Processing] página. Dentro de los datos del registro, los valores anexados estarían disponibles como cadenas de consulta de la [!DNL Form Processing] página, como se ilustra a continuación. Por ejemplo, v_1, v_2, v_3 y v_4 serían ahora cadenas de consulta que contienen los datos introducidos en los campos de formulario correspondientes. La sintaxis descrita en el ejemplo anterior se puede duplicar para cualquier campo de formulario y valor adicionales que desee capturar.

```
http://www.myserver.com/path/to/formprocessingpage.asp?v_1=John+Smith&v_2=Los+Angeles&v_3=California&v_4=90210
```

Si desea que todos los campos y valores del formulario se capturen y estén disponibles para análisis, puede utilizar la siguiente sintaxis:

```
var formvalues = Response.Form; 
Response.AppendToLog(formvalues); 
```

En este ejemplo se tomarían todos los campos de formulario presentes en el HTML junto con sus valores respectivos y se anexarían como cadenas de consulta a la entrada de registro de la [!DNL Form Processing] página. Cabe señalar que esto incluiría cualquier campo oculto presente en el formulario.

Los datos del registro se aumentarían como se detalla en la siguiente tabla:

| Datos recopilados | Explicación | Ejemplo |
|---|---|---|
| v_1 | Valor asociado a la cadena de consulta NAME | v_1=John Smith |
| v_2 | Valor asociado con la cadena de consulta CITY | v_2=Los Ángeles |
| v_3 | Valor asociado con la cadena de consulta STATE | v_3=California |
| v_4 | Valor asociado a la cadena de consulta ZIP | v_4=90210 |

