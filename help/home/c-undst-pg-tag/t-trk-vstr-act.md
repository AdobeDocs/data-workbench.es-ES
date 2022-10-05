---
description: Los sitios web creados con Flash requieren una atención especial con respecto a la captura de las acciones del visitante realizadas dentro del contenido multimedia enriquecido.
title: Seguimiento de la actividad de visitante dentro del contenido con medios enriquecidos
uuid: fe2e75eb-0897-4f63-b582-b4f1fdce02a1
exl-id: f51c7034-a7fd-4575-80e1-18fc6513ca2b
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '713'
ht-degree: 5%

---

# Seguimiento de la actividad de visitante dentro del contenido con medios enriquecidos{#tracking-visitor-activity-within-flash-rich-media-content}

{{eol}}

Los sitios web creados con Flash requieren una atención especial con respecto a la captura de las acciones del visitante realizadas dentro del contenido multimedia enriquecido.

Uso [!DNL Flash] ActionScript, puede realizar cambios sencillos en su [!DNL Flash] películas para permitir el seguimiento de todas las interacciones de los visitantes con la película, como clics en botones o movimientos del ratón.

Para facilitar el seguimiento de las actividades de los visitantes dentro de su [!DNL Flash] película, siga los pasos que se enumeran a continuación:

1. Agregue el siguiente código de ActionScript a la película. Este código representa una función a la que los eventos pueden llamar dentro del [!DNL Flash] película que desea rastrear.

   ```
   // FLASH TAG CODE BEGIN
   var FLASHTAGURI = "[PATH_TO_WEB_SERVER]/flashtag.txt";
   function tag(PAGENAME,VARIABLES) {
   loadVariablesNum(FLASHTAGURI+”?”+"PAGENAME="+PAGENAME+"&"+VARIABLES,0);
   }
   // FLASH TAG CODE END
   ```

1. Crear un archivo en blanco con el nombre [!DNL flashtag.txt] y coloque el archivo en los servidores web.
1. Dentro de la función del paso 1, reemplace la función \[[!DNL PATH_TO_WEB_SERVER]\] marcador de posición con la ruta completa o relativa a la ubicación de la variable [!DNL flashtag.txt] archivo. Por ejemplo:

   ```
   var FLASHTAGURI = https://www.mysite.com/flashtag/flashtag.txt”;
   ```

1. Agregue el siguiente código de ActionScript a todos los eventos para rastrear. Este código representa una llamada a una función que se usa para capturar datos sobre el evento:

   ```
   on(release) {tag("[PUT_PAGE_NAME_HERE]","[PUT_ADDITIONAL_VAR_HERE]");}
   ```

   Este ejemplo ilustra el uso del evento on(release) . sin embargo, se puede hacer referencia a la función tag() a través de cualquier evento que desee rastrear, como un evento on(press), on(rollover), on(rollout) o on(keypress).

   El \[[!DNL PUT_PAGE_NAME_HERE]\] el marcador de posición debe reemplazarse por una cadena que represente el nombre de la página o evento que está rastreando. El \[[!DNL PUT_PAGE_NAME_HERE]La variable \]se puede modificar manualmente o mediante referencia de variable para denotar un nombre único para la página o evento dentro de la variable [!DNL Flash] aplicación. El valor que sustituye al valor \[[!DNL PUT_PAGE_NAME_HERE]\] el marcador de posición puede consistir en un nombre simple o puede estar estructurado para representar una estructura jerárquica similar a una URI completa. Por ejemplo:

   ```
   on(release) {tag(“/about_us/index.swf","[PUT_ADDITIONAL_VAR_HERE]");}
   ```

   Adobe recomienda que, antes de la implementación del código, compile una especificación escrita para nombres de páginas y nombres de eventos para facilitar la alineación de los requisitos del negocio y las tareas de desarrollo y reducir el potencial para ciclos de desarrollo adicionales.

1. Si lo desea, se pueden recopilar variables adicionales que se pueden asociar a páginas o eventos en la variable [!DNL Flash] película. Para ello, reemplace la variable \[[!DNL PUT_ADDITIONAL_VAR_HERE]\] marcador de posición con un conjunto de pares nombre=valor separados por un signo &amp;. Por ejemplo:

   ```
   on(release) {tag(“/about_us/index.swf"," var1=value1&var2=value2");}
   ```

   Las variables se pueden modificar manualmente o a través de una referencia de variable para denotar atributos adicionales que se deben recopilar y asociar a la página o evento. Si no hay variables adicionales aplicables que recopilar, elimine \[[!DNL PUT_ADDITIONAL_VAR_HERE]\].

   La configuración del seguimiento de visitantes dentro de [!DNL Flash] ya se ha completado el contenido de medios enriquecidos. Cuando se invoca el evento, la etiqueta [!DNL (PAGENAME,VARIABLES)] se llamará a , lo que dará como resultado que se realice una solicitud HTTP para el siguiente archivo. Se llamará a esta función además de a otras funciones que se puedan activar según se definen en el [!DNL Flash] película:

   ```
   https://www.mysite.com/flashtag/flashtag.txt?PAGENAME=/about_us/index.swf&var1=value1&var2=value2
   ```

La solicitud HTTP resultante de la variable [!DNL Flash] La función de ActionScript de etiquetas hace que se recopile la siguiente información con respecto a cada evento dentro del [!DNL Flash] película. La última fila de la tabla (Nombre de W3C cs-uri-query) representa la información recopilada para las variables adicionales especificadas en la llamada de función.

<table id="table_A7ED9D38F36B4405947B2F48EA94D3C4">
 <thead>
  <tr>
   <th colname="col1" class="entry"> Nombre de W3C </th>
   <th colname="col2" class="entry"> Datos recopilados </th>
   <th colname="col3" class="entry"> Explicación </th>
   <th colname="col4" class="entry"> Ejemplo </th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <td colname="col1"> x-trackingid </td>
   <td colname="col2"> Identificador de seguimiento (visitante único) </td>
   <td colname="col3"> Identificador leído desde una cookie ubicada en el explorador del usuario por <span class="wintitle"> Sensor </span> en la solicitud inicial del visitante </td>
   <td colname="col4"> v1st=3C94007B4E01F9C2 </td>
  </tr>
  <tr>
   <td colname="col1"> <p>Fecha </p> <p>Fecha </p> </td>
   <td colname="col2"> Marca de tiempo </td>
   <td colname="col3"> Hora a la que el servidor procesó la solicitud (con una precisión de 100 ns; la precisión depende del entorno del servidor y de NTP) </td>
   <td colname="col4"> 2002-11-21 17:21:45 123 </td>
  </tr>
  <tr>
   <td colname="col1"> sc(content-Type) </td>
   <td colname="col2"> Tipo de contenido </td>
   <td colname="col3"> Tipo de objeto devuelto desde el servidor </td>
   <td colname="col4"> Texto/html </td>
  </tr>
  <tr>
   <td colname="col1"> sc-status </td>
   <td colname="col2"> Código de estado de respuesta HTTP </td>
   <td colname="col3"> Código numérico generado por el servidor que indica el estado de la respuesta del servidor HTTP </td>
   <td colname="col4"> 200 </td>
  </tr>
  <tr>
   <td colname="col1"> cs-uri-stem </td>
   <td colname="col2"> Elemento URI </td>
   <td colname="col3"> La parte raíz del URI solicitado por el cliente </td>
   <td colname="col4"> /flashtag/flashtag.txt </td>
  </tr>
  <tr>
   <td colname="col1"> c-ip </td>
   <td colname="col2"> IP del cliente </td>
   <td colname="col3"> Dirección IP del cliente solicitante </td>
   <td colname="col4"> 127.0.0.1 </td>
  </tr>
  <tr>
   <td colname="col1"> s-dns </td>
   <td colname="col2"> Nombre de dominio del servidor </td>
   <td colname="col3"> Nombre de dominio del servidor web que procesa la solicitud </td>
   <td colname="col4"> www.mysite.com </td>
  </tr>
  <tr>
   <td colname="col1"> cs(referrer) </td>
   <td colname="col2"> Dirección URL de referencia </td>
   <td colname="col3"> Contenido del campo de referente HTTP enviado por el cliente </td>
   <td colname="col4"></td>
  </tr>
  <tr>
   <td colname="col1"> cs(user-agent) </td>
   <td colname="col2"> Agente de usuario </td>
   <td colname="col3"> Dispositivo utilizado para realizar una solicitud al servidor HTTP </td>
   <td colname="col4"> Mozilla/4.0+(compatible;+MSIE+6.0) +Windows+NT+5.1) </td>
  </tr>
  <tr>
   <td colname="col1"> cs(cookie) </td>
   <td colname="col2"> Cookies de cliente del dominio </td>
   <td colname="col3"> Contenido de todas las cookies del usuario para el sitio </td>
   <td colname="col4"> <p>KL_TC1 1038058778312 </p> <p>KL972x1038058778312282052 </p> <p>KL_PVKL972 0 </p> </td>
  </tr>
  <tr>
   <td colname="col1"> cs-uri-query </td>
   <td colname="col2"> Cadena de consulta </td>
   <td colname="col3"> La parte de la cadena de consulta, si la hay, del URI solicitado por el cliente </td>
   <td colname="col4"> PAGENAME=/about_us/index.swf&amp;var1=value1&amp;var2=value2 </td>
  </tr>
 </tbody>
</table>
