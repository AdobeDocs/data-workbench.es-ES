---
description: Los sitios web creados con Flash requieren especial atención con respecto a la captura de acciones de visitante realizadas dentro del contenido de medios enriquecidos.
solution: Analytics
title: Seguimiento de la Actividad de Visitante dentro del contenido Flash Rich Media
topic: Data workbench
uuid: fe2e75eb-0897-4f63-b582-b4f1fdce02a1
translation-type: tm+mt
source-git-commit: 48892b1b4fc9e9fdeacee8ca318025f43f2d0064

---


# Seguimiento de la Actividad de Visitante dentro del contenido Flash Rich Media{#tracking-visitor-activity-within-flash-rich-media-content}

Los sitios web creados con Flash requieren especial atención con respecto a la captura de acciones de visitante realizadas dentro del contenido de medios enriquecidos.

Con [!DNL Flash] ActionScript, puede realizar cambios sencillos en sus [!DNL Flash] películas existentes para permitir el seguimiento de todas las interacciones de visitante con la película, como clics en botones o movimientos del ratón.

Para facilitar el seguimiento de la actividad de Visitantes dentro de la [!DNL Flash] película, siga los pasos que se enumeran a continuación:

1. Añada el siguiente código ActionScript a la película. Este código representa una función a la que pueden llamar eventos dentro de la [!DNL Flash] película que desea rastrear.

   ```
   // FLASH TAG CODE BEGIN 
   var FLASHTAGURI = "[PATH_TO_WEB_SERVER]/flashtag.txt"; 
   function tag(PAGENAME,VARIABLES) { 
   loadVariablesNum(FLASHTAGURI+”?”+"PAGENAME="+PAGENAME+"&"+VARIABLES,0); 
   } 
   // FLASH TAG CODE END
   ```

1. Cree un archivo en blanco con el nombre [!DNL flashtag.txt] y colóquelo en los servidores web.
1. Dentro de la función del paso 1, reemplace el marcador de posición \[[!DNL PATH_TO_WEB_SERVER]\] por la ruta completa o relativa a la ubicación del [!DNL flashtag.txt] archivo. Por ejemplo:

   ```
   var FLASHTAGURI = http://www.mysite.com/flashtag/flashtag.txt”;
   ```

1. Añada el siguiente código ActionScript a todos los eventos que se rastrearán. Este código representa una llamada de función utilizada para capturar datos sobre el evento:

   ```
   on(release) {tag("[PUT_PAGE_NAME_HERE]","[PUT_ADDITIONAL_VAR_HERE]");}
   ```

   Este ejemplo ilustra el uso del evento on(release); sin embargo, se puede hacer referencia a la función tag() a través de cualquier evento que desee rastrear, como un evento on(press), on(rollover), on(rollout) o on(keypress).

   El marcador de posición \[[!DNL PUT_PAGE_NAME_HERE]\] debe reemplazarse por una cadena que represente el nombre de la página o el evento que esté rastreando. La variable \[[!DNL PUT_PAGE_NAME_HERE]\] se puede modificar manualmente o mediante referencia de variable para denotar un nombre único para la página o el evento dentro de la [!DNL Flash] aplicación. El valor que sustituye al marcador de posición \[[!DNL PUT_PAGE_NAME_HERE]\] puede consistir en un nombre simple o puede estructurarse para representar una estructura jerárquica similar a una URI completa. Por ejemplo:

   ```
   on(release) {tag(“/about_us/index.swf","[PUT_ADDITIONAL_VAR_HERE]");}
   ```

   Adobe recomienda que, antes de la implementación del código, compile una especificación por escrito para nombres de páginas y nombres de eventos para facilitar la alineación de los requisitos comerciales y las tareas de desarrollo y reducir el potencial de ciclos de desarrollo adicionales.

1. Si lo desea, se pueden recopilar variables adicionales y asociarlas con páginas o eventos de la [!DNL Flash] película. Para ello, reemplace el marcador de posición \[[!DNL PUT_ADDITIONAL_VAR_HERE]\] por un conjunto de pares nombre=valor separados por un signo &amp;. Por ejemplo:

   ```
   on(release) {tag(“/about_us/index.swf"," var1=value1&var2=value2");}
   ```

   Las variables se pueden modificar manualmente o a través de una referencia de variable para denotar atributos adicionales que se deben recopilar y asociar con la página o el evento. Si no hay variables adicionales aplicables para recopilar, elimine \[[!DNL PUT_ADDITIONAL_VAR_HERE]\].

   Ya se ha completado la configuración del seguimiento de visitantes dentro del contenido de medios [!DNL Flash] enriquecidos. Cuando se invoca el evento, se llama a la función de etiqueta [!DNL (PAGENAME,VARIABLES)] , lo que resulta en una solicitud HTTP para el siguiente archivo. Esta función se llamará además de otras funciones que se pueden activar según se define en la [!DNL Flash] película:

   ```
   http://www.mysite.com/flashtag/flashtag.txt?PAGENAME=/about_us/index.swf&var1=value1&var2=value2
   ```

La solicitud HTTP resultante de la función [!DNL Flash] Tag ActionScript resulta en la recopilación de la siguiente información con respecto a cada evento dentro de la [!DNL Flash] película. La última fila de la tabla (Nombre W3C cs-uri-consulta) representa la información recopilada para las variables adicionales especificadas en la llamada a la función.

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
   <td colname="col3"> Identificador leído desde una cookie colocada en el explorador del usuario por <span class="wintitle"> Sensor </span> en la solicitud inicial del Visitante </td> 
   <td colname="col4"> v1st=3C94007B4E01F9C2 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Fecha </p> <p>Fecha </p> </td> 
   <td colname="col2"> Marca de tiempo </td> 
   <td colname="col3"> Hora a la que el servidor procesó la solicitud (con una precisión de 100 ns; la precisión depende del entorno del servidor y NTP) </td> 
   <td colname="col4"> 2002-11-21 17:21:45.123 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> sc(content-Type) </td> 
   <td colname="col2"> Tipo de contenido </td> 
   <td colname="col3"> Tipo de objeto devuelto por el servidor </td> 
   <td colname="col4"> Texto/html </td> 
  </tr> 
  <tr> 
   <td colname="col1"> sc-status </td> 
   <td colname="col2"> Código de estado de respuesta HTTP </td> 
   <td colname="col3"> Código numérico generado por el servidor que anota el estado de la respuesta del servidor HTTP </td> 
   <td colname="col4"> 200 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> cs-uri-stem </td> 
   <td colname="col2"> Identificador URI </td> 
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
   <td colname="col1"> cs(remitente del reenvío) </td> 
   <td colname="col2"> Dirección URL de referencia </td> 
   <td colname="col3"> Contenido del campo remitente del reenvío HTTP enviado por el cliente </td> 
   <td colname="col4"></td> 
  </tr> 
  <tr> 
   <td colname="col1"> cs(user-agent) </td> 
   <td colname="col2"> Agente de usuario </td> 
   <td colname="col3"> Dispositivo utilizado para realizar una solicitud al servidor HTTP </td> 
   <td colname="col4"> Mozilla/4.0+(compatible;+MSIE+6.0; +Windows+NT+5.1) </td> 
  </tr> 
  <tr> 
   <td colname="col1"> cs(cookie) </td> 
   <td colname="col2"> Cookies de cliente del dominio </td> 
   <td colname="col3"> Contenido de todas las cookies del usuario para el sitio </td> 
   <td colname="col4"> <p>KL_TC1 1038058778312 </p> <p>KL972x1038058778312282052 </p> <p>KL_PVKL972 0 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> cs-uri-consulta </td> 
   <td colname="col2"> Cadena de Consulta </td> 
   <td colname="col3"> La parte de cadena de consulta, si la hay, del URI solicitado por el cliente </td> 
   <td colname="col4"> PAGENAME=/about_us/index.swf&amp;var1=value1&amp;var2=value2 </td> 
  </tr> 
 </tbody> 
</table>

