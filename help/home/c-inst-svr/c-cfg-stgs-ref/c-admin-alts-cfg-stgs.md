---
description: Instrucciones para configurar alertas administrativas para el servidor de Insight, el repetidor o la transformación.
title: Configuración de alertas administrativas
uuid: c2be2d1e-d81d-4d9f-ac94-4b642dad90b9
exl-id: c75e442e-33e6-4fc8-8368-29482f09e1cc
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '514'
ht-degree: 4%

---

# Configuración de alertas administrativas{#administrative-alerts-configuration-settings}

Instrucciones para configurar alertas administrativas para el servidor de Insight, el repetidor o la transformación.

Complete los parámetros del siguiente archivo:

[!DNL Product Name installation directory\Components\Administrative Alerts.cfg]

<table id="table_5A2298906D5F4215B8FAC42CACBC0002"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parámetro </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Categoría </td> 
   <td colname="col2"> Nombre de la categoría. Se requiere una categoría de Predeterminado. Consulte Categorías de error en esta tabla. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Categorías de error </td> 
   <td colname="col2"> Permite clasificar los errores junto con el archivo de clasificación de errores. Cada categoría de error puede tener su propio conjunto de destinatarios y su propio retraso de aceleración. Por ejemplo, puede crear una categoría Crítica con un retardo de aceleración de 0, de modo que cada error crítico se envíe inmediatamente por correo electrónico a los destinatarios especificados en la lista Destinatarios. Los errores que no coinciden con una subcadena en el archivo de clasificación de errores se asignan a la categoría Predeterminado. Para agregar una nueva categoría, haga clic con el botón derecho en un número y haga clic en <span class="uicontrol"> Agregar nueva </span> &gt; <span class="uicontrol"> Categoría de error </span>. También puede copiarlos o eliminarlos con la acción del botón derecho. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Archivo de clasificación de errores </td> 
   <td colname="col2"> <p>Nombre del archivo que desea utilizar para categorizar cada alerta. Puede crear este archivo utilizando el Bloc de notas. Este archivo debe tener tres columnas en cada línea, separadas por tabulaciones. La primera columna es una cadena que coincide en errores. Un signo ^ coincide con el principio y un signo $ coincide con el final de la cadena; todos los demás caracteres coinciden literalmente. La segunda columna es una categoría para los errores que coinciden, que se encuentra en Categorías de error. El tercero es un mensaje alternativo, que se añade al mensaje de error real en los correos electrónicos que se envían. Si no se especifica ningún archivo, todos los errores se clasifican como Predeterminado. </p> <p>Para ver un ejemplo de este archivo, consulte el archivo <span class="filepath"> Error Categories.txt </span> en el directorio Lookups. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> De </td> 
   <td colname="col2"> <p>Dirección que aparece en el parámetro "from" del mensaje de correo electrónico. </p> <p>Ejemplo: <span class="filepath"> server_errors@mycompany.com </span></p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Espacio mínimo en disco (MB) </td> 
   <td colname="col2"> El servidor genera una alerta de correo electrónico cuando está disponible el almacenamiento en disco en cualquier directorio utilizado por el servidor cae por debajo de este valor. El valor predeterminado es 1000. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Tiempo de espera de alerta del sensor (min.) </td> 
   <td colname="col2"> <p>El servidor genera una alerta por correo electrónico cuando no ha recibido datos de un <span class="wintitle"> sensor </span> configurado y conectado anteriormente dentro de este período de tiempo. El valor predeterminado es 15. </p> <p> <p>Nota:  <span class="wintitle"> El tiempo de espera de alerta del sensor </span> solo funciona si se interrumpe una conexión existente con un sensor <span class="wintitle"> </span>. Si el servicio del servidor se detiene y se reinicia y los <span class="wintitle"> sensores </span> no se conectan, el servidor no genera alertas por correo electrónico. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Dirección del servidor </td> 
   <td colname="col2"> <p>La dirección del servidor SMTP para el correo electrónico saliente. </p> <p>Ejemplo: <span class="filepath"> mail.mycompany.com </span></p> <p>Se requiere un servidor SMTP para utilizar las capacidades descritas. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Contraseña del servidor </td> 
   <td colname="col2"> <p>La contraseña para iniciar sesión en el servidor SMTP. Este parámetro es opcional a menos que sea necesario iniciar sesión para enviar correo. </p> <p>Se requiere un servidor SMTP para utilizar las capacidades descritas. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Usuario del servidor </td> 
   <td colname="col2"> <p>ID/nombre de usuario para iniciar sesión en el servidor SMTP. Este parámetro es opcional a menos que sea necesario iniciar sesión para enviar correo. </p> <p>Se requiere un servidor SMTP para utilizar las capacidades descritas. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Retraso del acelerador (segundos) </td> 
   <td colname="col2"> El número mínimo de segundos que deben transcurrir entre dos errores en esa categoría para que se envíe un correo electrónico. Un valor de 0 envía el correo electrónico inmediatamente. </td> 
  </tr> 
 </tbody> 
</table>
