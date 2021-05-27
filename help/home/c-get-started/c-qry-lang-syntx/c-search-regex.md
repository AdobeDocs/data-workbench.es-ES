---
description: Data Workbench utiliza expresiones regulares (regex) para operaciones de búsqueda y ordenación.
title: Expresiones regulares
uuid: dc8c1e88-4d95-4011-8a38-70fae0c5cf6d
exl-id: bb1be6d8-3b7a-47e4-bb29-4a65de99666b
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '134'
ht-degree: 3%

---

# Expresiones regulares{#regular-expressions}

Data Workbench utiliza expresiones regulares (regex) para operaciones de búsqueda y ordenación.

Dentro del campo **[!UICONTROL Search]** puede realizar una búsqueda siguiendo la instrucción &quot;re:&quot; utilizando expresiones comunes, por ejemplo:

```
<b>re: *.s</b>
```

<table id="table_BA125AB039794EE382B33003BE4E0AFB"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> metacaracteres </th> 
   <th colname="col2" class="entry"> descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>  (punto) </p> </td> 
   <td colname="col2"> <p>Coincide con un solo carácter, por ejemplo: <span class="filepath"> re:x.z </span> coincide con "xyz" o "xxz". </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>* (estrella) </p> </td> 
   <td colname="col2"> <p>Coincide con uno o varios caracteres, por ejemplo: <span class="filepath"> re:Z* </span> coincide con "ZZZ". </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>? (comodín) </p> </td> 
   <td colname="col2"> <p>Coincide con 0 o 1 de la expresión anterior para forzar una coincidencia mínima, por ejemplo: <span class="filepath"> xy?z </span> coincide con "xy" y "xyz". </p> </td> 
  </tr> 
 </tbody> 
</table>

También se pueden utilizar expresiones regulares comunes adicionales para crear cadenas de búsqueda más complejas. Las expresiones regulares se utilizan en todos los campos de búsqueda de Datas Workbench, incluidos los paneles de entidades de consulta.

Consulte la información detallada en [expresiones regulares](https://docs.adobe.com/content/help/en/data-workbench/using/dataset/c-dataset-constr.html#Regular_Expressions).
