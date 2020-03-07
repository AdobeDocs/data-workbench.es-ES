---
description: El área de trabajo de datos incluye dimensiones integradas.
solution: Analytics
title: Dimensiones integradas
topic: Data workbench
uuid: 0aabbc52-266d-46c1-a4b3-dd575c0f2c72
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Dimensiones integradas{#built-in-dimensions}

El área de trabajo de datos incluye dimensiones integradas.

En la tabla siguiente se muestran las dimensiones integradas disponibles para el área de trabajo de datos:

<table id="table_40796088B3484F98889859C59D525AD7"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Nombre </th> 
   <th colname="col2" class="entry"> Detalles </th> 
   <th colname="col3" class="entry"> Nivel </th> 
   <th colname="col4" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Ninguna </td> 
   <td colname="col2"> Derivado </td> 
   <td colname="col3"> N/A </td> 
   <td colname="col4">Tiene un solo elemento "" que se relaciona con todos los elementos de todas las dimensiones. Evaluar una métrica sobre Ninguna es como evaluarla sobre ninguna dimensión. <p>El <span class="filepath"> filtro [None=""]</span> equivale a <span class="filepath"> [True]</span>. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> Uno (oculto) </td> 
   <td colname="col2"> Numéricos </td> 
   <td colname="col3"> N/A </td> 
   <td colname="col4">El elemento "1", que también tiene un valor ordinal <span class="filepath"> = 1</span>, se refiere a todos los elementos de todas las dimensiones. La dimensión One se utiliza normalmente para construir recuentos utilizando esta sintaxis: <p><span class="filepath"> sum(one,Countable_Dimension)</span></p></td> 
  </tr> 
 </tbody> 
</table>

