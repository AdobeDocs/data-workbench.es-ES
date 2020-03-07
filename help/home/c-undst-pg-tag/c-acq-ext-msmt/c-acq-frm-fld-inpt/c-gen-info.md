---
description: Los valores introducidos en un formulario en una página Web pueden recopilarse y anexarse en la cadena de consulta de la página solicitada posteriormente (en el envío del formulario) mediante el uso de JavaScript.
solution: Analytics
title: Información general
topic: Data workbench
uuid: 401816a5-1d95-48e6-bedf-ee2a5dbd2d50
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Información general{#general-information}

Los valores introducidos en un formulario en una página Web pueden recopilarse y anexarse en la cadena de consulta de la página solicitada posteriormente (en el envío del formulario) mediante el uso de JavaScript.

Podemos verlo en el ejemplo siguiente. Incluya este JavaScript después de cualquier secuencia de comandos de validación de formularios utilizada en las páginas HTML.

```
<html> 
<head> 
</head> 
<script language="JavaScript"> 
 
function AppendFormValues() 
{ 
 
for(var i = 0; i < document.formname.length; i++) 
{ 
var item = document.formname.elements[i]; 
var formitem = “v_”+i; 
var formvalue = item.value; 
formvalues += formitem + '=' + formvalue + '&'; 
} 
document.formname.action = document.formname.action + '?' + formvalues; 
 
} 
</script> 
<body> 
<form name="formname" action="thankyou.asp" method="POST" onSubmit="AppendFormValues();"> 
<input name="NAME" size="50" value=""></input>name<br/> 
<input name="CITY" size="50" value=""></input>city<br/> 
<input name="STATE" size="50" value=""></input>state<br/> 
<input name="ZIP" size="10" value=""></input>zip<br /> 
<input type="submit" name="submit" value="submit"/> 
</body> 
</html> 
```

En este ejemplo se anexan los valores introducidos en el formulario por el usuario del explorador a la página &quot;thankyou.asp&quot; siguiente indicada en el valor de Acción de FORMULARIO de la siguiente manera:

```
http://www.myserver.com/thankyou.asp?v_1=John Smith&v_2=Los Angeles&v_3=California&v_4=90210
```

Con esta solicitud se obtendrían las siguientes mediciones ampliadas, además de las mediciones de referencia recopiladas por [!DNL Sensor]:

| Datos recopilados | Explicación | Ejemplo |
|---|---|---|
| v_1 | Valor asociado al campo de formulario NOMBRE | v_1=John Smith |
| v_2 | Valor asociado al campo de formulario CITY | v_2=Los Ángeles |
| v_3 | Valor asociado al campo de formulario STATE | v_3=California |
| v_4 | Valor asociado al campo de formulario ZIP | v_4=90210 |

