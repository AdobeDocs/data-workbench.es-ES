---
description: Información conceptual sobre las expresiones de hoja de cálculo y el uso de referencias de celda.
solution: Analytics
title: Expresiones de hoja de cálculo
topic: Data workbench
uuid: be57d6bd-3e13-4c90-9034-8e0f2b8315aa
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Expresiones de hoja de cálculo{#worksheet-expressions}

Información conceptual sobre las expresiones de hoja de cálculo y el uso de referencias de celda.

La siguiente hoja de cálculo proporciona detalles sobre los visitantes que ven la página Asistente para solicitudes que se proporciona en el formulario de solicitud en línea del sitio web de un banco.

![](assets/client-wkst.png)

* La columna A muestra una lista de las categorías de visitantes que se evalúan: visitantes, visitantes de referencia y visitantes de referencia del referente A.
* La columna B muestra el número de visitantes en cada categoría que vieron la página Aplicar ahora.
* La columna C muestra los visitantes que vieron las páginas Aplicar ahora y Asistente para aplicaciones.
* La columna D contiene los porcentajes de los visores Aplicar ahora en las tres categorías que también vieron la página Asistente para aplicaciones.

La hoja de cálculo muestra que aproximadamente el 55 por ciento de los visitantes referidos desde el referente A que vieron la página Aplicar ahora también vieron la página Asistente para solicitudes.

La siguiente tabla proporciona fórmulas de ejemplo para la hoja de cálculo del ejemplo anterior:

<table id="table_0F5EFDB58040465AB599E6BE93324822"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Celda de hoja de cálculo </th> 
   <th colname="col2" class="entry"> Fórmula </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>B2 </p> <p>Visitantes que vieron la página Aplicar ahora </p> </td> 
   <td colname="col2"> <p><span class="filepath"> =Visitantes[Página="/applynow/default.asp"]</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>B3 </p> <p>Visitantes referidos que vieron la página Aplicar ahora </p> </td> 
   <td colname="col2"> <p><span class="filepath"> =Visitantes_referidos[Página="/applynow/default.asp"]</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>B4 </p> <p>Visitantes remitidos desde el referente A que vieron la página Aplicar ahora </p> </td> 
   <td colname="col2"> <p> <span class="filepath"> =Visitantes_referidos[Página="/applynow/default.asp" </span> </p> <p> AND <span class="filepath"> Referrer="Ref A"]</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>C2 </p> <p>Visitantes que vieron la página Aplicar ahora y la página Asistente para aplicaciones </p> </td> 
   <td colname="col2"> <p> <span class="filepath"> =Visitantes[Página="/applynow/default.asp" </span> </p> <p> AND <span class="filepath"> Page="/applynow/appwizard.asp"]</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>C3 </p> <p>Visitantes referidos que vieron la página Aplicar ahora y la página Asistente para aplicaciones </p> </td> 
   <td colname="col2"> <p> <span class="filepath"> =Visitantes_referidos[Página="/applynow/default.asp" </span> </p> <p> AND <span class="filepath"> Page="/applynow/appwizard.asp"]</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>C4 </p> <p>Visitantes remitidos desde el referente A que vieron la página Aplicar ahora y la página Asistente para aplicaciones </p> </td> 
   <td colname="col2"> <p> <span class="filepath"> =Visitantes_referidos[Página="/applynow/default.asp"</span> </p> <p> AND <span class="filepath"> Page="/applynow/appwizard.asp"</span> </p> <p> AND <span class="filepath"> Referrer="Ref A"]</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>D2 </p> <p>Porcentaje de visitantes que vieron la página Aplicar ahora y la página Asistente para aplicaciones </p> </td> 
   <td colname="col2"> <p><span class="filepath"> =C2/B2*100</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>D3 </p> <p>Porcentaje de visitantes referidos que vieron la página Aplicar ahora y la página Asistente para aplicaciones </p> </td> 
   <td colname="col2"> <p><span class="filepath"> =C3/B3*100</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>D4 </p> <p>Porcentaje de visitantes remitidos desde el referente A que vieron la página Aplicar ahora y la página Asistente para aplicaciones </p> </td> 
   <td colname="col2"> <p><span class="filepath"> =C4/B4*100</span> </p> </td> 
  </tr> 
 </tbody> 
</table>

Al igual que con otras visualizaciones, las hojas de cálculo se actualizan automáticamente al realizar una selección en otra visualización del espacio de trabajo. Para obtener más información sobre cómo realizar selecciones, consulte [Realizar selecciones en Visualizaciones](../../../../home/c-get-started/c-vis/c-sel-vis/c-sel-vis.md#concept-012870ec22c7476e9afbf3b8b2515746).

En el siguiente ejemplo de datos web, se han seleccionado varios días de datos de sesión en la visualización Sesiones por día. La hoja de cálculo muestra que durante el intervalo de tiempo seleccionado, aproximadamente el 69 por ciento de los visitantes del referente A que vieron la página Aplicar ahora también vieron la página Asistente para solicitudes. Sin esta selección (como se muestra en el ejemplo anterior), aproximadamente el 55 por ciento de los visitantes del referente A vio la página Aplicar ahora, así como la página Asistente para solicitudes.

![](assets/client-exp.png)

## Uso de referencias de celda {#section-0004e315c9c94d359b1a8a39794ba555}

Puede sustituir cualquier cadena, ya sea por sí misma o dentro de otra expresión de la hoja de cálculo, por una referencia de celda.

* **Referencia de celda simple:** La celda A2 contiene el texto Visitantes, que se utiliza como encabezado. La celda B2 contiene [!DNL eval(A1)], que se evalúa como [!DNL =Visitors].

* **Referencia de celda de filtro:** La celda A5 contiene la fecha de ayer. La celda B5 contiene [!DNL Visitors[ Day=A5 ]], que se evalúa como el número de visitantes de ayer.

* **Referencia de celda concatenada:** La celda A5 contiene la fecha de hoy y la celda A6 contiene el período de tiempo de una hora de 08:00 a 08:59. La celda B6 contiene [!DNL Visitors[ Hour=A5+&quot;&quot;+A6 ]], que se evalúa como el número de visitantes hoy entre las 8:00 AM y las 9:00 AM.

