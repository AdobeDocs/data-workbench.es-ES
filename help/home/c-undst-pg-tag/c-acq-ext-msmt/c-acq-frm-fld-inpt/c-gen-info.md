---
description: Los valores introducidos en un formulario en una página web se pueden recopilar y anexar en la cadena de consulta de la página solicitada posteriormente (al enviar el formulario) mediante el uso de JavaScript.
title: Información general
uuid: 401816a5-1d95-48e6-bedf-ee2a5dbd2d50
exl-id: 9effc72b-e75f-423c-87ec-6ac25edee8d6
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '175'
ht-degree: 7%

---

# Información general{#general-information}

{{eol}}

Los valores introducidos en un formulario en una página web se pueden recopilar y anexar en la cadena de consulta de la página solicitada posteriormente (al enviar el formulario) mediante el uso de JavaScript.

Podemos verlo en el ejemplo siguiente. Incluya este JavaScript después de cualquier secuencia de comandos de validación de formulario que se utilice en las páginas de HTML.

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

En este ejemplo se añaden los valores introducidos en el formulario por el usuario del explorador a la página siguiente &quot;thankyou.asp&quot; que se indica en el valor Acción de formulario de la siguiente manera:

```
https://www.myserver.com/thankyou.asp?v_1=John Smith&v_2=Los Angeles&v_3=California&v_4=90210
```

Con esta solicitud se adquirirían las siguientes mediciones ampliadas, además de las mediciones de referencia recopiladas por [!DNL Sensor]:

| Datos recopilados | Explicación | Ejemplo |
|---|---|---|
| v_1 | Valor asociado al campo de formulario NAME | v_1=John Smith |
| v_2 | Valor asociado al campo de formulario CITY | v_2=Los Ángeles |
| v_3 | Valor asociado al campo de formulario STATE | v_3=California |
| v_4 | Valor asociado al campo de formulario ZIP | v_4=90210 |
