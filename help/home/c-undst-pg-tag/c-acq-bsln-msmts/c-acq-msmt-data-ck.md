---
description: Como parte de los datos de medición de línea de base recopilados, Sensor recopila las cookies de dominio enviadas desde el equipo de un visitante cuando realiza una solicitud desde el servidor web.
title: Adquisición de datos de medición mediante cookies
uuid: 34cd6baf-6317-4774-8165-58208698b53c
exl-id: 37c7b5f6-33bf-4373-963a-e08a826e05df
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '587'
ht-degree: 2%

---

# Adquisición de datos de medición mediante cookies{#acquiring-measurement-data-through-cookies}

{{eol}}

Como parte de los datos de medición de línea de base recopilados, Sensor recopila las cookies de dominio enviadas desde el equipo de un visitante cuando realiza una solicitud desde el servidor web.

Esto incluye tanto las cookies persistentes como las de sesión que establece el sitio web cuando un visitante interactúa con el sistema.

En la mayoría de los casos, los sitios web establecen cookies persistentes para identificar visitantes o capturar entradas de usuario para usarlas en sesiones de visitantes posteriores. Cualquier información escrita y almacenada en cookies persistentes se puede capturar y utilizar junto con todos los demás datos de medición dentro del servidor de Data Workbench.

Un ejemplo de una cookie persistente de este tipo podría implicar un identificador de cliente en forma de clave numérica presente en una cookie específica de dominio que reside en el equipo del visitante. Además de identificar al usuario como un visitante de retorno, la cookie persistente también se podría usar para identificar más al visitante como un cliente que retorna o para enlazar al visitante a información contenida en una base de datos de clientes para permitir que la información demográfica del cliente sin conexión se muestre dentro de [!DNL Site] y se utiliza para el análisis interactivo.

Las cookies de sesión pueden ser un buen mecanismo para recopilar los datos introducidos por el usuario a través de los campos de formulario u otros elementos interactivos dinámicos dentro del sitio web. En el caso de un sitio web que implemente formularios para capturar datos de entrada específicos del usuario, la información permanece en la cookie de sesión solo durante el tiempo que la sesión esté activa. Cuando un usuario abandona el sitio web o posteriormente finaliza una sesión, la información ya no se almacena en el equipo del usuario. Sin embargo, la información introducida es capturada por [!DNL Sensor] y se ponen a disposición como datos de medición dentro de [!DNL Site].

A continuación se muestra un ejemplo del uso de una cookie de sesión para capturar una sola variable de formulario introducida por un visitante.

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

En este ejemplo, se llama a una función para establecer una cookie de sesión en el equipo del visitante con el nombre del campo y el valor introducido en el campo de formulario. A medida que se envía el formulario y se solicita la página web siguiente, el conjunto de cookies de sesión se pasa al servidor web y lo recopila el [!DNL Sensor]. Por lo tanto, los siguientes datos están disponibles en el servidor de Data Workbench para su uso en el análisis de datos:

| Datos recopilados | Explicación | Ejemplo |
|---|---|---|
| v_1 | Valor asociado con la cookie v_1. Este valor representa el NOMBRE introducido en el campo de formulario que dio como resultado que se estableciera la cookie de sesión. | v_1=John Smith |

Las cookies de sesión también se pueden utilizar para capturar de forma iterativa campos de formulario o una multitud de variables JavaScript incrustadas presentes en una página de HTML. En el ejemplo siguiente, se utiliza JavaScript para capturar de forma recursiva cualquier campo de formulario presente en un archivo HTML y establecer una cookie de sesión con los pares nombre=valor correspondientes.

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

En este ejemplo, se establece una cookie de sesión en el equipo del visitante con el nombre y el valor de todos los campos de formulario que existan en el formulario. Esto incluye campos de entrada, casillas de verificación, botones de opción, cuadros de selección y áreas de texto. Como puede observar en este ejemplo, dado que el número de campos de formulario es desconocido, es necesario capturar todos los valores de campo y nombre de formulario como una sola cadena, delimitada por un signo &amp;. Este paso debe realizarse debido a un límite en el número de cookies que un usuario puede tener en su equipo en un momento dado. Microsoft Internet Explorer solo permite que haya veinte (20) cookies de sesión presentes antes de comenzar a soltar las más antiguas.
