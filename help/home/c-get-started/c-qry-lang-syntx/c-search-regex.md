---
description: El área de trabajo de datos utiliza expresiones regulares (regex) para las operaciones de búsqueda y ordenación.
solution: Analytics
title: Expresiones regulares
topic: Data workbench
uuid: dc8c1e88-4d95-4011-8a38-70fae0c5cf6d
translation-type: tm+mt
source-git-commit: 2e4991206394ca0c463210990ea44dfb700341a5

---


# Regular expressions{#regular-expressions}

El área de trabajo de datos utiliza expresiones regulares (regex) para las operaciones de búsqueda y ordenación.

Dentro del **[!UICONTROL Search]** campo puede realizar una búsqueda siguiendo la instrucción &quot;re:&quot; utilizando expresiones comunes, por ejemplo:

```
<b>re: *.s</b>
```

<table id="table_BA125AB039794EE382B33003BE4E0AFB"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> metacarácter </th> 
   <th colname="col2" class="entry"> description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>. (punto) </p> </td> 
   <td colname="col2"> <p>Coincide con un solo carácter, por ejemplo: <span class="filepath"> re:x.z </span> coincide con "xyz" o "xxz". </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>* (estrella) </p> </td> 
   <td colname="col2"> <p>Coincide con uno o varios caracteres, por ejemplo: <span class="filepath"> re:Z* </span> coincide con "ZZZ". </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>? (comodín) </p> </td> 
   <td colname="col2"> <p>Coincide con 0 o 1 de la expresión anterior para forzar la coincidencia mínima, por ejemplo: <span class="filepath"> xy?z </span> coincide con "xy" y "xyz". </p> </td> 
  </tr> 
 </tbody> 
</table>

También se pueden utilizar expresiones regulares comunes adicionales para crear cadenas de búsqueda más complejas. Las expresiones regulares se utilizan en todos los campos de búsqueda del Área de trabajo de datos, incluidos los paneles de entidad de consulta.

Consulte información detallada en expresiones [regulares](https://docs.adobe.com/content/help/en/data-workbench/using/dataset/c-dataset-constr.html#Regular_Expressions).
