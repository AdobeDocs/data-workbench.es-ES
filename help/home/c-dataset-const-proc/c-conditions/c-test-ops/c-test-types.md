---
description: La condición Compare y la condición Range requieren que especifique el tipo de comparación que se debe realizar para la condición.
title: Tipos de pruebas para operaciones de prueba
uuid: dc0433dd-a35e-472e-8975-f58347512c11
exl-id: 8abed46e-e76d-47c0-bbe9-cf98cf2d61e8
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '425'
ht-degree: 2%

---

# Tipos de pruebas para operaciones de prueba{#test-types-for-test-operations}

La condición Compare y la condición Range requieren que especifique el tipo de comparación que se debe realizar para la condición.

En la tabla siguiente se describen los tipos disponibles ( [!DNL LEXICAL], [!DNL NUMERIC] y [!DNL DATETIME]).

<table id="table_1B3AD8BDF0414D0AB8EE0E6D1B53E2CE"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Tipo de prueba </th> 
   <th colname="col2" class="entry"> Descripción </th> 
   <th colname="col3" class="entry"> Notas </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> ENTERO</span> </p> </td> 
   <td colname="col2"> <p>Primero convierte el campo de entrada en un número entero. Si esto no es posible, se utiliza un valor de cero. La prueba solo devuelve el valor "True" si el valor de entrada del entero resultante es bueno o igual al valor mínimo especificado y menor o igual que el valor máximo especificado. </p> </td> 
   <td colname="col3"> <p>Si alguno de los campos mínimo o máximo se deja en blanco, el sistema utiliza el valor mínimo o máximo correspondiente disponible para enteros firmados de 64 bits. </p> <p> Si el valor mínimo o máximo especificado en la condición no se analiza correctamente en un valor entero, el sistema sustituye a cero y no detiene el procesamiento del conjunto de datos. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> DATETIME</span> </p> </td> 
   <td colname="col2"> <p>Primero convierte el campo de entrada en una fecha. Si el campo de entrada no se puede convertir en una fecha válida, la prueba de condición devuelve el valor "False". Si el campo se puede convertir en una fecha, la prueba devuelve el valor "True" solo si la fecha de entrada se encuentra en la fecha mínima especificada o después de ella y en o antes de la fecha máxima especificada. </p> </td> 
   <td colname="col3"> <p>Si las fechas mínima y máxima no son válidas, el conjunto de datos no se construye. </p> <p> Si no se suministran las fechas mínima o máxima, el sistema sustituye adecuadamente la fecha mínima (1 de enero de 1600) o la fecha máxima (en algún momento del siglo 24). </p> <p> Adobe recomienda usar uno de los siguientes formatos para <span class="wintitle"> DATETIME</span>: </p> 
    <ul id="ul_44F469CC5D974382AF70D7B1975CF077"> 
     <li id="li_DB5FD4AFD6B34436ACD7C13282F64956"> 1 de enero de 2013 HH:MM:SS EDT </li> 
     <li id="li_307580C3F97D495BB16F1212DB38CE37"> 1 de enero de 2013 HH:MM:SS GMT </li> 
    </ul> <p> Si no se especifica nada, la zona horaria toma el valor predeterminado GMT. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> LEXICAL</span> </p> </td> 
   <td colname="col2"> <p>El resultado es true solo si el campo de entrada es lexicamente bueno o igual a la cadena especificada como mínimo y menor o igual que la cadena especificada en el valor máximo. </p> </td> 
   <td colname="col3"> <p>La comparación lexica utiliza el valor ASCII de los caracteres en las cadenas que se desplazan de izquierda a derecha, comparando los caracteres. Para el primer carácter que no coincide, el que tiene el valor ASCII más grande se considera el bueno de los dos. En el caso de que una cadena sea más corta que la otra, pero hasta ese momento todos los caracteres hayan sido iguales, la cadena más larga se considerará la buena de los dos. Si las cadenas son equivalentes a caracteres y tienen la misma longitud, se consideran equivalentes lexicamente. </p> </td> 
  </tr> 
 </tbody> 
</table>
