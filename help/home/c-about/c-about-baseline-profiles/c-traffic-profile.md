---
description: El perfil Tráfico contiene las siguientes métricas para identificar el tráfico de visitantes.
solution: Analytics
title: Métricas de perfil de tráfico
topic: Data workbench
uuid: 7dfa18ef-d2cd-44ae-8c56-a0630a9d5cf2
translation-type: tm+mt
source-git-commit: 2e4991206394ca0c463210990ea44dfb700341a5

---


# Métricas de perfil de tráfico{#traffic-profile-metrics}

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
   <td colname="col3"> El número de sesiones que ingresaron al sitio en cada página. Esta métrica solo se evalúa en la dimensión Página. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Tasa de salida </td> 
   <td colname="col2">Fórmula: <span class="filepath"> Salidas/Vistas de página </span><p>Nivel: Vista de página </p></td> 
   <td colname="col3"> El porcentaje de sesiones que salieron del sitio desde cada página. La métrica Tasa de salida solo se puede evaluar en la dimensión de página. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Salidas </td> 
   <td colname="col2">Fórmula:<span class="filepath"> Page_Views[sin desplazamiento(None,Page_View, Session,1)] </span><p>Nivel: Vista de página </p></td> 
   <td colname="col3"> Número de sesiones que salieron del sitio desde cada página. Esta métrica solo se evalúa en la dimensión Página. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> LVCI90 </td> 
   <td colname="col2">Fórmula: <span class="filepath"> (sin procesar(Visitantes) - ((sin procesar (Visitantes) + 0,69)^0,5 * 1,281551 - 1,2269))*(Visitantes/sin procesar(Visitantes))</span><p>Nivel: Visitante </p></td> 
   <td colname="col3"> Medición del número más bajo de visitantes posibles según Insight. Matemáticamente, especifica el número más bajo de visitantes con una probabilidad del 90 %. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Duración de la vista de página </td> 
   <td colname="col2"> <p>Fórmula: <span class="filepath"> sum (exacto_page_duration, page_view)*0.1/Page_Views[cualquier Exact_Page_Duration]</span></p> <p>Nivel: Vista de página </p> </td> 
   <td colname="col3"> Tiempo promedio (MM:SS) empleado en una página o grupo de páginas en particular. Esta métrica solo se evalúa en la dimensión Página. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Vistas de página por sesión </td> 
   <td colname="col2"> <p>Fórmula: <span class="filepath"> Page_Views/ (Sesiones por vista de página) </span></p> <p>Nivel: Sesión </p> </td> 
   <td colname="col3"> Cantidad promedio de vistas de página en cada sesión que tiene vistas de página. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Vistas de páginas </td> 
   <td colname="col2">Fórmula: <span class="filepath"> sum(One, Page_View)</span><p>Nivel: Vista de página </p></td> 
   <td colname="col3"> Número de vistas de página. Una vista de página es una solicitud para una página definida (no se cuenta el acceso a las imágenes ni a otros tipos de contenido filtrado). </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Vistas de página </td> 
   <td colname="col2">Fórmula: <span class="filepath"> Page_Views/total(Page_Views) </span><p>Nivel: Vista de página </p></td> 
   <td colname="col3"> Porcentaje de vistas de página. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Parte de las sesiones </td> 
   <td colname="col2">Fórmula: Sesiones <span class="filepath"> /total(Sesiones)</span><p>Nivel: Sesión </p></td> 
   <td colname="col3"> El porcentaje de sesiones. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Página de visitantes </td> 
   <td colname="col2">Fórmula: <span class="filepath"> Visitantes/total (Visitantes) </span><p>Nivel: Visitante </p></td> 
   <td colname="col3"> El porcentaje de visitantes. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Visitantes Remitidos Por Pct </td> 
   <td colname="col2"> <p>Fórmula: Referred_Visitors/Visitors </p> <p>Nivel: Visitante </p> </td> 
   <td colname="col3"> El porcentaje de visitantes que llegaron a este sitio desde otro sitio. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Sesiones referidas </td> 
   <td colname="col2"> <p>Fórmula: Sesiones <span class="filepath"> [Referente&lt;&gt; 'Ninguno' y Referente&lt;&gt;'Marcadores']</span></p> <p>Nivel: Sesión </p> </td> 
   <td colname="col3"> Número de sesiones que se han referido a este sitio desde otro sitio. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Visitantes referidos </td> 
   <td colname="col2"> <p>Fórmula: <span class="filepath"> Visitantes[Visitor_Referrer&lt;&gt;'None' y Visitor_Referrer&lt;&gt;'bookmarks']</span></p> <p>Nivel: Visitante </p> </td> 
   <td colname="col3"> Cantidad de visitantes que llegaron a este sitio desde otro sitio. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Retención </td> 
   <td colname="col2"> <p>Fórmula: Sesiones <span class="filepath"> [mayús(Ninguno,Ses sion,Visitante,1) = ""] / Sesiones</span></p> <p>Nivel: Sesión </p> </td> 
   <td colname="col3"> El porcentaje de sesiones que no son las últimas sesiones de los visitantes. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Duración de la sesión </td> 
   <td colname="col2"> <p>Fórmula: <span class="filepath"> (suma (Exact_Page_Duration, Sesión)*.1/Sesiones)[Duración_Sesión &lt;= '01:00:00']</span></p> <p>Nivel: Sesión </p> </td> 
   <td colname="col3">El tiempo promedio (MM:SS) que un visitante emplea en una sesión. <p><p>Nota: Puede utilizar esta métrica con la función <a href="https://docs.adobe.com/content/help/en/data-workbench/using/client/t-open-ins.html#Segment_Export" format="http" scope="external"> Exportación</a> de segmentos. </p></p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> Sesiones por vista de página </td> 
   <td colname="col2"> <p>Fórmula: Sesiones <span class="filepath"> por vista de página</span></p> <p> Nivel: Sesión </p> </td> 
   <td colname="col3"> Número de sesiones que tuvieron una vista de página. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Sesiones </td> 
   <td colname="col2"> <p>Fórmula: <span class="filepath"> sum(Una, Sesión)</span></p> <p>Nivel: Sesión </p> </td> 
   <td colname="col3"> Recuento de sesiones de visitantes. Una sesión es un período de actividad para un visitante de un sitio Web. Las sesiones individuales de cada visitante se identifican mediante cookies, tiempos de espera y otras heurísticas. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> SCI80 </td> 
   <td colname="col2"> <p>Fórmula: <span class="filepath"> confianza (Sesiones) * 1.281551 / Sesiones</span></p> <p>Nivel: Visitante </p> </td> 
   <td colname="col3"> Una medida de confianza de la métrica Sesiones según lo informado por el área de trabajo de datos. Matemáticamente, es un porcentaje +/- que especifica el intervalo dentro del cual la respuesta real será el 80% del tiempo. Como regla general, duplicar el porcentaje de SCI80 dará un intervalo dentro del cual la respuesta real será del 99% del tiempo. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> UVCI90 </td> 
   <td colname="col2"> <p>Fórmula: <span class="filepath"> ((sin procesar (visitantes) + 0,68)^0,5 * 1,281551 + 1,2269) + sin procesar (visitantes))*( Visitantes/sin procesar (visitantes))</span></p> <p>Nivel: Visitante </p> </td> 
   <td colname="col3"> Medida del mayor número de posibles visitantes según Insight. Matemáticamente, especifica el número más alto de visitantes con una probabilidad del 90 %. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> VCI80 </td> 
   <td colname="col2">Fórmula: <span class="filepath"> ((sin procesar (visitantes) + 0,68)^0,5 * 1,281551 + 1,2269) / sin procesar (visitantes)</span><p>Nivel: Visitante </p></td> 
   <td colname="col3"> Una medida de confianza de la métrica Visitantes según lo informado por Insight. Matemáticamente, es un porcentaje +/- que especifica el intervalo dentro del cual la respuesta real será el 80% del tiempo. Como regla general, duplicar el porcentaje de VCI80 proporcionará un intervalo dentro del cual la respuesta real será del 99% del tiempo. </td> 
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

