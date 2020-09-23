---
description: Instrucciones para configurar alertas administrativas para Insight Server, Repeater o Transform.
solution: Analytics
title: Configuración de alertas administrativas
uuid: c2be2d1e-d81d-4d9f-ac94-4b642dad90b9
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '514'
ht-degree: 4%

---


# Configuración de alertas administrativas{#administrative-alerts-configuration-settings}

Instrucciones para configurar alertas administrativas para Insight Server, Repeater o Transform.

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
   <td colname="col2"> Permite clasificar los errores junto con el archivo de clasificación de errores. Cada Categoría de error puede tener su propio conjunto de Destinatarios y su propio retraso de aceleración. Por ejemplo, puede crear una categoría crítica con un retraso de aceleración de 0, de modo que todos los errores críticos se envíen inmediatamente por correo electrónico a los destinatarios especificados en la lista Destinatarios. Los errores que no coinciden con una subcadena en el archivo de clasificación de errores se asignan a la categoría predeterminada. Para agregar una nueva categoría, haga clic con el botón derecho en un número y haga clic en <span class="uicontrol"> Añadir nuevo </span> &gt; <span class="uicontrol"> Categoría de error </span>. También puede copiarlos o eliminarlos con la acción de hacer clic con el botón derecho. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Archivo de clasificación de errores </td> 
   <td colname="col2"> <p>Nombre del archivo que desea utilizar para categorizar cada alerta. Puede crear este archivo con el Bloc de notas. Este archivo debe tener tres columnas en cada línea, separadas por fichas. La primera columna es una cadena que coincide en errores. Un signo ^ coincide con el principio y un $ coincide con el final de la cadena; todos los demás caracteres coinciden literalmente. La segunda columna es una categoría para los errores que coinciden, que se encuentra en Categorías de error. El tercero es un mensaje alternativo, que se antepone al mensaje de error real en los mensajes de correo electrónico que se envían. Si no se especifica ningún archivo, todos los errores se clasifican como Predeterminado. </p> <p>Para ver un ejemplo de este archivo, consulte el archivo <span class="filepath"> Categorías de error.txt </span> en el directorio Lookups. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> De </td> 
   <td colname="col2"> <p>Dirección que aparece en el parámetro "from" del mensaje de correo electrónico. </p> <p>Ejemplo: <span class="filepath"> server_errors@mycompany.com </span></p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Espacio mínimo en disco (MB) </td> 
   <td colname="col2"> El servidor genera una alerta por correo electrónico cuando el almacenamiento de disco disponible en cualquier directorio utilizado por el servidor cae por debajo de este valor. El valor predeterminado es 1000. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Tiempo de espera de alerta de sensor (mín.) </td> 
   <td colname="col2"> <p>El servidor genera una alerta de correo electrónico cuando no ha recibido datos de un <span class="wintitle"> sensor configurado y conectado previamente </span> en este período de tiempo. El valor predeterminado es 15. </p> <p> <p>Nota:  <span class="wintitle"> El tiempo de espera de alerta de sensor </span> solo funciona si se interrumpe una conexión existente a un <span class="wintitle"> sensor </span> . Si el servicio del servidor se detiene y reinicia y los <span class="wintitle"> sensores </span> no se conectan, el servidor no genera alertas de correo electrónico. </p> </p> </td> 
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
   <td colname="col2"> El número mínimo de segundos que deben transcurrir entre dos errores en esa categoría para que se envíe un mensaje de correo electrónico. Un valor de 0 envía el correo electrónico inmediatamente. </td> 
  </tr> 
 </tbody> 
</table>

