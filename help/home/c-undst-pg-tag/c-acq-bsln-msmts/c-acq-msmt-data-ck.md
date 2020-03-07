---
description: Como parte de los datos de medición de línea base recopilados, Sensor recopila las cookies de dominio enviadas desde el equipo del visitante cuando realiza una solicitud desde el servidor web.
solution: Analytics
title: Adquisición de datos de medición mediante cookies
topic: Data workbench
uuid: 34cd6baf-6317-4774-8165-58208698b53c
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Adquisición de datos de medición mediante cookies{#acquiring-measurement-data-through-cookies}

Como parte de los datos de medición de línea base recopilados, Sensor recopila las cookies de dominio enviadas desde el equipo del visitante cuando realiza una solicitud desde el servidor web.

Esto incluye las cookies persistentes y de sesión que su sitio web establece cuando un visitante interactúa con su sistema.

En la mayoría de los casos, los sitios Web configuran cookies persistentes para identificar a los visitantes o capturar los datos introducidos por el usuario para utilizarlos en sesiones posteriores de visitantes. Cualquier información escrita y almacenada en cookies persistentes puede capturarse y utilizarse junto con todos los demás datos de medición dentro del servidor del área de trabajo de datos.

Un ejemplo de una cookie persistente de este tipo podría implicar un identificador de cliente en forma de clave numérica presente en una cookie específica de dominio que reside en el equipo del visitante. Además de identificar al usuario como visitante de retorno, la cookie persistente también se puede utilizar para identificar más al visitante como cliente de retorno o para asociar al visitante con la información contenida en una base de datos de clientes para permitir que la información demográfica del cliente sin conexión se muestre dentro [!DNL Site] y se utilice para el análisis interactivo.

Las cookies de sesión pueden ser un buen mecanismo para recopilar datos introducidos por el usuario a través de campos de formulario u otros elementos interactivos dinámicos dentro del sitio web. En el caso de un sitio web que implementa formularios para capturar datos de entrada específicos del usuario, la información permanece en la cookie de sesión sólo mientras la sesión esté activa. Cuando un usuario abandona el sitio web o finaliza una sesión posteriormente, la información ya no se almacena en el equipo del usuario. Sin embargo, la información ingresada es capturada [!DNL Sensor] y se pone a disposición como datos de medición dentro de [!DNL Site].

A continuación se muestra un ejemplo de uso de una cookie de sesión para capturar una sola variable de formulario ingresada por un visitante.

```
<html> 
<head> 
<title>Cookie Collection </title> 
 
<script language="JavaScript"> 
function AppendFormValues() 
{ 
 
var item = document.testform.elements[i]; 
var formitem = “v_”+i; 
var formvalue = item.value; 
cookie += formitem + "=" + formvalue + "&"; 
document.cookie = cookie; 
 
testform.submit(); 
 
} 
</script> 
</head> 
<body> 
<form name="testform" method="post" action="nextpage.asp"> 
<input type="text" size=15 name="name"><br />enter name 
<br><br> 
 
<a href="javascript:AppendFormValues();">Click Here To </a><br /><br /> 
<br /><br /><br /> 
 
</body> 
</html> 
```

En este ejemplo, se llama a una función para establecer una cookie de sesión en el equipo del visitante con el nombre del campo y el valor introducido en el campo del formulario. A medida que se envía el formulario y se solicita la página web subsiguiente, la cookie de sesión establecida se pasa al servidor web y se recopila en [!DNL Sensor]. Por lo tanto, los siguientes datos están disponibles en el servidor del área de trabajo de datos para su uso en el análisis de datos:

| Datos recopilados | Explicación | Ejemplo |
|---|---|---|
| v_1 | Valor asociado con la cookie v_1. Este valor representa el NOMBRE introducido en el campo de formulario que dio como resultado que se configurara la cookie de sesión. | v_1=John Smith |

Las cookies de sesión también pueden utilizarse para capturar de forma iterativa campos de formulario o una multitud de variables JavaScript incrustadas presentes en una página HTML. En el ejemplo siguiente, JavaScript se utiliza para capturar de forma recursiva cualquier campo de formulario presente en un archivo HTML y establecer una cookie de sesión con los pares nombre=valor correspondientes.

```
<script language="JavaScript"> 
 
function AppendFormValues() 
{ 
 
var cookie="formcookie="; 
for (i=0; i<document.testform.length; i++){ 
if (document.testform.elements[i].type =="radio") {            
if (document.testform.elements[i].checked){ 
var item = document.testform.elements[i]; 
var formitem = “v_”+i; 
var formvalue = item.value; 
cookie += formitem + "=" + formvalue + "&"; 
} 
} 
else if (document.testform.elements[i].type =="select") { 
var item = document.testform.elements[i]; 
var formitem = “v_”+i; 
var optionindex = eval(document.testform.elements[i].selectedIndex); 
var formvalue = document.testform.elements[i].options[optionindex].value;             
cookie += formitem + "=" + formvalue + "&"; 
} 
else{ 
var item = document.testform.elements[i]; 
var formitem = “v_”+i; 
var formvalue = item.value; 
cookie += formitem + "=" + formvalue + "&"; 
} 
} 
document.cookie = cookie; 
document.testform.submit(); 
} 
 
</script>
```

En este ejemplo, se establece una cookie de sesión en el equipo del visitante con el nombre y el valor de cada campo de formulario que exista en el formulario. Esto incluye campos de entrada, casillas de verificación, botones de opción, cuadros de selección y áreas de texto. Como puede observar en este ejemplo, debido a que el número de campos de formulario es desconocido, es necesario capturar todos los valores de campo y nombre del formulario como una sola cadena, delimitada por un símbolo de unión. Este paso debe realizarse debido a un límite en el número de cookies que un usuario puede tener en su equipo en un momento dado. Microsoft Internet Explorer permite que solo estén presentes veinte (20) cookies de sesión antes de que comience a soltar las más antiguas.
