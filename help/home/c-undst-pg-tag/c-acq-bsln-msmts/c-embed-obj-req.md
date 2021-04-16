---
description: Una vez que un explorador solicita el HTML de una página, el explorador solicita los objetos incrustados a los que se hace referencia en el HTML de esa página desde un servidor web para rellenar la página mostrada por el explorador.
title: Adquisición de solicitudes de objetos incrustados (etiquetas de página)
uuid: 7fe561d1-aa5a-4ac9-82ba-aa27c7d208dd
exl-id: 593e49bc-9619-4e85-8ce3-2e9d23d175c9
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '604'
ht-degree: 4%

---

# Adquisición de solicitudes de objetos incrustados (etiquetas de página){#acquiring-embedded-object-requests-page-tags}

Una vez que un explorador solicita el HTML de una página, el explorador solicita los objetos incrustados a los que se hace referencia en el HTML de esa página desde un servidor web para rellenar la página mostrada por el explorador.

Estas solicitudes de objetos incrustados suelen ser solicitudes de archivos de imagen o archivos JavaScript, aunque hay cientos o tal vez miles de tipos de objetos incrustados que se utilizan actualmente en Internet. Muchas de estas solicitudes de objetos incrustados no suelen ser útiles para analizar la actividad comercial de un sitio de Internet ni para generar informes al respecto; por lo tanto, muchas de estas solicitudes no son deseables para la adquisición a menos que tengan un propósito comercial específico, como presentar un anuncio o realizar otra medición de la actividad del sitio.

Por ejemplo, una imagen puede ser un anuncio y es posible que desee saber que el anuncio fue impresionado por un visitante. Puede que se esté utilizando un fragmento de JavaScript para medir que el navegador concreto tiene una determinada característica y pasarla a [!DNL Sensor] para la adquisición. Cada página de un sitio puede tener entre 10 y 100 solicitudes de objetos incrustados. Si un sitio almacena la información de registro para cada una de estas solicitudes, la cantidad de almacenamiento de datos necesario para mantener los datos de registro disponibles para análisis futuros se multiplica por el número de solicitudes de objeto incorporadas para cada página solicitada. Por este motivo, [!DNL Site] permite mantener las solicitudes que son importantes para el análisis y descartar otras antes de incurrir en costos de almacenamiento innecesarios.

Al utilizar la función de anulación proporcionada en las capacidades de filtrado de tipo de contenido de [!DNL Sensor] (anexando &quot;Log=1&quot; a la cadena de consulta de una URL de solicitud de objeto incrustado), esa solicitud de objeto incrustado en particular y los datos de medición relacionados se pueden adquirir sin requerir que el administrador del sitio almacene todas las solicitudes de ese tipo (por ejemplo, todas `<image>` solicitudes).

[!DNL Sensor] recopila los datos de medición en la tabla siguiente para cada solicitud de objeto incrustado realizada del servidor web, suponiendo que no  [!DNL Sensor] esté configurado para filtrarlo o que el filtro se haya anulado. La información recopilada está relacionada con el visitante y la sesión y las sesiones posteriores a través de las entradas del campo de registro x-trackingid o cs(cookie) .

<table id="table_11BE08A798E743EC8E76F738F0CE5884"> 
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
   <td colname="col3"> Identificador leído desde una cookie colocada en el explorador del usuario por el <span class="wintitle"> Sensor </span> en la solicitud inicial </td> 
   <td colname="col4"> V1st=3C94007B4E01F9C2 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Fecha </p> <p>Fecha </p> </td> 
   <td colname="col2"> Marca de tiempo </td> 
   <td colname="col3"> Hora a la que el servidor procesó la solicitud (con una precisión de 100 ns; la precisión depende del entorno del servidor y de NTP) </td> 
   <td colname="col4"> 2002-11-21 17:21:45.123 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> sc(content-Type) </td> 
   <td colname="col2"> Tipo de contenido </td> 
   <td colname="col3"> Tipo de objeto devuelto desde el servidor </td> 
   <td colname="col4"> text/html </td> 
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
   <td colname="col3"> La parte "raíz" del URI solicitado por el cliente </td> 
   <td colname="col4"> pagedir/page.asp </td> 
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
   <td colname="col4"> <span class="filepath"> www.domain.com  </span> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> cs(referrer) </td> 
   <td colname="col2"> Dirección URL de referencia </td> 
   <td colname="col3"> Contenido del campo de referente HTTP enviado por el cliente </td> 
   <td colname="col4"> <span class="filepath"> http://www.referringsite.com  </span> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> cs(user-agent) </td> 
   <td colname="col2"> Agente de usuario </td> 
   <td colname="col3"> Dispositivo utilizado para realizar una solicitud al servidor HTTP </td> 
   <td colname="col4"> <p>Mozilla/4.0+(compatible;+MSIE+6.0) </p> <p>+Windows+NT+5.1) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> cs(cookie) </td> 
   <td colname="col2"> Cookies de cliente del dominio </td> 
   <td colname="col3"> Contenido de todas las cookies del usuario para el sitio </td> 
   <td colname="col4"> <p>KL_TC1 1038058778312 </p> <p>KL972 x1038058778312282052 </p> <p>KL_PVKL972 0 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> cs-uri-query </td> 
   <td colname="col2"> Cadena de consulta </td> 
   <td colname="col3"> La parte de la cadena de consulta, si la hay, del URI solicitado por el cliente </td> 
   <td colname="col4"> PAGENAME=dynamic1&amp;link=3001 </td> 
  </tr> 
 </tbody> 
</table>
