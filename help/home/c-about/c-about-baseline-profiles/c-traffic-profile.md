---
description: El perfil Tráfico contiene las siguientes métricas para identificar el tráfico de visitantes.
title: Métricas del perfil de tráfico
uuid: 7dfa18ef-d2cd-44ae-8c56-a0630a9d5cf2
exl-id: 38f191e5-5b30-4fe0-a680-bcb33fe52eca
source-git-commit: 4ab43bfbad96096fb2cebd77a8be8fa6d49fa7dc
workflow-type: tm+mt
source-wordcount: '709'
ht-degree: 2%

---

# Métricas del perfil de tráfico{#traffic-profile-metrics}

{{eol}}

El perfil Tráfico contiene las siguientes métricas para identificar el tráfico de visitantes.

<table id="table_D981FB9F8B734E3C845A9628548565F1"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Métrica </th> 
   <th colname="col2" class="entry"> Fórmula y nivel de métrica </th> 
   <th colname="col3" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Entradas </td> 
   <td colname="col2">Fórmula: <span class="filepath"> Page_Views[sin mayús(None,Page_View, Session,-1)]</span><p>Nivel: Vista de página </p></td> 
   <td colname="col3"> Número de sesiones que entraron al sitio en cada página. Esta métrica solo se evalúa sobre la dimensión Página . </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Tasa de salida </td> 
   <td colname="col2">Fórmula: <span class="filepath"> Salidas/Vistas de página </span><p>Nivel: Vista de página </p></td> 
   <td colname="col3"> El porcentaje de sesiones que salieron del sitio desde cada página. La métrica Tasa de salida solo se puede evaluar en la dimensión de página. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Salidas </td> 
   <td colname="col2">Fórmula:<span class="filepath"> Page_Views[sin mayús(None,Page_View, Session,1)] </span><p>Nivel: Vista de página </p></td> 
   <td colname="col3"> Número de sesiones que salieron del sitio desde cada página. Esta métrica solo se evalúa sobre la dimensión Página . </td> 
  </tr> 
  <tr> 
   <td colname="col1"> LVCI90 </td> 
   <td colname="col2">Fórmula: <span class="filepath"> (sin procesar (visitantes) - ((sin procesar (visitantes) + 0,69)^0,5 * 1,281551 - 1,2269))*(Visitantes/sin procesar(visitantes))</span><p>Nivel: Visitante </p></td> 
   <td colname="col3"> Medición del número más bajo de visitantes posibles según la información de Insight. Matemáticamente, especifica el número más bajo de visitantes con una probabilidad del 90 %. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Duración de la vista de página </td> 
   <td colname="col2"> <p>Fórmula: <span class="filepath"> sum (exactamente_page_duration, page_view)*0.1/Page_Views[any Exact_Page_Duration]</span></p> <p>Nivel: Vista de página </p> </td> 
   <td colname="col3"> El tiempo promedio (MM:SS) empleado en una página o grupo de páginas en particular. Esta métrica solo se evalúa sobre la dimensión Página . </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Vistas de página por sesión </td> 
   <td colname="col2"> <p>Fórmula: <span class="filepath"> Vistas de página/ (Sesiones por vista de página) </span></p> <p>Nivel: Sesión </p> </td> 
   <td colname="col3"> Número promedio de vistas de página en cada sesión que tiene vistas de página. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Vistas de páginas </td> 
   <td colname="col2">Fórmula: <span class="filepath"> sum(One, Page_View)</span><p>Nivel: Vista de página </p></td> 
   <td colname="col3"> Número de vistas de página. Una vista de página es una solicitud para una página definida (el acceso a imágenes y otros tipos de contenido filtrado no se cuentan). </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Resumen de las vistas de página </td> 
   <td colname="col2">Fórmula: <span class="filepath"> Page_Views/total(Page_Views) </span><p>Nivel: Vista de página </p></td> 
   <td colname="col3"> El porcentaje de vistas de página. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Resumen de las sesiones </td> 
   <td colname="col2">Fórmula: <span class="filepath"> Sesiones/total(Sesiones)</span><p>Nivel: Sesión </p></td> 
   <td colname="col3"> El porcentaje de sesiones. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Resumen de los visitantes </td> 
   <td colname="col2">Fórmula: <span class="filepath"> Visitantes/total(Visitantes) </span><p>Nivel: Visitante </p></td> 
   <td colname="col3"> El porcentaje de visitantes. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Visitantes Remitidos Por Pct </td> 
   <td colname="col2"> <p>Fórmula: Visitantes/Visitantes_referidos </p> <p>Nivel: Visitante </p> </td> 
   <td colname="col3"> El porcentaje de visitantes que llegaron a este sitio desde otro sitio. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Sesiones referidas </td> 
   <td colname="col2"> <p>Fórmula: <span class="filepath"> Sessions[Referrer&lt;&gt; 'None' y Referrer&lt;&gt;'bookmarks']</span></p> <p>Nivel: Sesión </p> </td> 
   <td colname="col3"> Número de sesiones que se han referido a este sitio desde otro sitio. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Visitantes referidos </td> 
   <td colname="col2"> <p>Fórmula: <span class="filepath"> Visitors[Visitor_ Referrer&lt;&gt;'None' y Visitor_Referrer&lt;&gt;'bookmarks']</span></p> <p>Nivel: Visitante </p> </td> 
   <td colname="col3"> Número de visitantes que llegaron a este sitio desde otro sitio. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Retención </td> 
   <td colname="col2"> <p>Fórmula: <span class="filepath"> Sesiones[Mayús(Ninguno,Ses sion,Visitor,1) = ""] / Sesiones</span></p> <p>Nivel: Sesión </p> </td> 
   <td colname="col3"> El porcentaje de sesiones que no son las últimas sesiones de los visitantes. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Duración de la sesión </td> 
   <td colname="col2"> <p>Fórmula: <span class="filepath"> (sum (Exact_Page_Duration, Session)*.1/Sessions)[Session_ Duration &lt;= '01:00:00']</span></p> <p>Nivel: Sesión </p> </td> 
   <td colname="col3">El tiempo promedio (MM:SS) que un visitante emplea en una sesión. <p><p>Nota: Puede utilizar esta métrica con la variable <a href="https://experienceleague.adobe.com/docs/data-workbench/using/client/t-open-ins.html#Segment_Export" format="http" scope="external"> Exportación de segmentos</a> función. </p></p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> Sesiones por vista de página </td> 
   <td colname="col2"> <p>Fórmula: <span class="filepath"> Sesiones por vista de página</span></p> <p> Nivel: Sesión </p> </td> 
   <td colname="col3"> Número de sesiones que tuvieron una vista de página. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Sesiones </td> 
   <td colname="col2"> <p>Fórmula: <span class="filepath"> sum(One, Session)</span></p> <p>Nivel: Sesión </p> </td> 
   <td colname="col3"> Recuento de sesiones de visitantes. Una sesión es un período de actividad para un visitante de un sitio web. Las sesiones individuales de cada visitante se identifican mediante cookies, tiempos de espera y otras métricas. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> SCI80 </td> 
   <td colname="col2"> <p>Fórmula: <span class="filepath"> confianza (sesiones) * 1.281551 / Sesiones</span></p> <p>Nivel: Visitante </p> </td> 
   <td colname="col3"> Una medida de confianza de la métrica Sesiones según la información de Data Workbench. Matemáticamente, es un porcentaje +/- que especifica el intervalo dentro del cual la respuesta real será del 80% de las veces. Como regla general, duplicar el porcentaje de SCI80 dará un rango en el que la respuesta real residirá el 99% del tiempo. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> UVCI90 </td> 
   <td colname="col2"> <p>Fórmula: <span class="filepath"> (((sin procesar(visitantes) + .68)^0.5 * 1.281551 + 1.2269) + sin procesar(visitantes))*( Visitantes/sin procesar(visitantes)))</span></p> <p>Nivel: Visitante </p> </td> 
   <td colname="col3"> Una medida del número más alto de visitantes posibles según la información de Insight. Matemáticamente, especifica el número más alto de visitantes con una probabilidad del 90 %. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> VCI80 </td> 
   <td colname="col2">Fórmula: <span class="filepath"> ((raw(Visitors) + .68)^0.5 * 1.281551 + 1.2269) / raw(Visitors)</span><p>Nivel: Visitante </p></td> 
   <td colname="col3"> Una medida de confianza de la métrica Visitantes según la información de Insight. Matemáticamente, es un porcentaje +/- que especifica el intervalo dentro del cual la respuesta real será del 80% de las veces. Como regla general, duplicar el porcentaje de VCI80 dará un rango en el cual la respuesta real residirá el 99% del tiempo. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Visitantes por vista de página </td> 
   <td colname="col2"> <p>Fórmula: <span class="filepath"> Visitantes por vista de página</span></p> <p>Nivel: Vista de página </p> </td> 
   <td colname="col3"> El número de visitantes que tuvieron una vista de página. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Visitantes por sesión </td> 
   <td colname="col2"> <p>Fórmula: <span class="filepath"> Visitantes por sesión </span></p> <p>Nivel: Sesión </p> </td> 
   <td colname="col3"> El número de visitantes que tuvieron una sesión. </td> 
  </tr> 
 </tbody> 
</table>
