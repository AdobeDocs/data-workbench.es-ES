---
description: Las páginas web suelen estructurarse con un lenguaje de programación ASP (páginas de Active Server).
title: Información específica de ASP
uuid: 552288cb-b775-4121-8869-322f2a26932b
exl-id: f73235e1-d44a-4056-b1f4-a86879c19483
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '446'
ht-degree: 1%

---

# Información específica de ASP{#asp-specific-information}

{{eol}}

Las páginas web suelen estructurarse con un lenguaje de programación ASP (páginas de Active Server).

ASP es una tecnología de Microsoft que se ejecuta en IIS (Servicios de Internet Information Server). Cuando un explorador solicita un archivo ASP, IIS pasa la solicitud al motor ASP. El motor ASP lee el archivo ASP línea a línea y ejecuta las secuencias de comandos del archivo. Finalmente, el archivo ASP se devuelve al explorador como HTML sin formato. ASP proporciona objetos RESPOND o REQUEST que, además de otros usos, permiten la respuesta o solicitud de consultas de usuario o datos enviados desde formularios de HTML.

En algunos casos, es posible que no desee anexar los valores introducidos en los formularios a la dirección URL que se muestra en la barra de direcciones del explorador de un usuario o que se puede ver en el propio código del HTML. El JavaScript simple del lado del servidor le permite anexar nombres de campos de formulario y sus valores respectivos al archivo de registro sin ponerlos a disposición en el explorador del usuario ni insertarlos en el archivo HTML. Para capturar los valores de formulario reales introducidos en formularios concretos dentro del sitio web, se deben agregar algunas líneas de código para anexar los valores de formulario a la solicitud de registro.

En la página de procesamiento de un formulario, incluya el siguiente código para anexar los valores de formulario introducidos a los datos de solicitud (además de escribir los valores de formulario enviados en una base de datos externa u otra ubicación):

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

Este proceso anexaría los valores del formulario tal como se definen en los datos de solicitud para la variable [!DNL Form Processing] página. Dentro de los datos de registro, los valores añadidos estarían disponibles como cadenas de consulta de la variable [!DNL Form Processing] como se ilustra a continuación. Por ejemplo, v_1, v_2, v_3 y v_4 ahora serían cadenas de consulta que contengan los datos introducidos en los campos de formulario correspondientes. La sintaxis descrita en el ejemplo anterior se puede duplicar para cualquier campo de formulario adicional y valor que desee capturar.

```
https://www.myserver.com/path/to/formprocessingpage.asp?v_1=John+Smith&v_2=Los+Angeles&v_3=California&v_4=90210
```

Si desea que todos los campos y valores del formulario se capturen y estén disponibles para su análisis, puede utilizar la siguiente sintaxis:

```
var formvalues = Response.Form;
Response.AppendToLog(formvalues);
```

En este ejemplo se tomarían todos los campos de formulario presentes en el HTML junto con sus valores respectivos y se adjuntarían como cadenas de consulta a la entrada de registro para la variable [!DNL Form Processing] página. Cabe señalar que esto incluiría cualquier campo oculto presente en el formulario.

Los datos de registro se aumentarían como se detalla en la siguiente tabla:

| Datos recopilados | Explicación | Ejemplo |
|---|---|---|
| v_1 | Valor asociado a la cadena de consulta NAME | v_1=John Smith |
| v_2 | Valor asociado con la cadena de consulta CITY | v_2=Los Ángeles |
| v_3 | Valor asociado con la cadena de consulta STATE | v_3=California |
| v_4 | Valor asociado con la cadena de consulta ZIP | v_4=90210 |
