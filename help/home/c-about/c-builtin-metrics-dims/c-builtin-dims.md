---
description: Data Workbench incluye dimensiones integradas.
title: Dimensiones integradas
uuid: 0aabbc52-266d-46c1-a4b3-dd575c0f2c72
exl-id: c08a487d-60b8-4db7-8776-7ae1b9f1f27c
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '100'
ht-degree: 14%

---

# Dimensiones integradas{#built-in-dimensions}

Data Workbench incluye dimensiones integradas.

En la tabla siguiente se enumeran las dimensiones integradas disponibles para Data Workbench:

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
   <td colname="col4">Tiene un solo elemento "" que se relaciona con todos los elementos de todas las dimensiones. Evaluar una métrica sobre Ninguno es como evaluarla sobre ninguna dimensión. <p>El <span class="filepath"> Filtro [None=""]</span> es equivalente a <span class="filepath"> [True]</span>. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> Uno (oculto) </td> 
   <td colname="col2"> Numéricos </td> 
   <td colname="col3"> N/D </td> 
   <td colname="col4">El elemento "1", que también tiene un valor ordinal <span class="filepath"> = 1</span>, se relaciona con todos los elementos de todas las dimensiones. La dimensión One se utiliza normalmente para construir recuentos utilizando esta sintaxis: <p><span class="filepath"> sum(one,Countable_Dimension)</span></p></td> 
  </tr> 
 </tbody> 
</table>
