---
description: La transformación Merge toma los valores del campo de entrada (normalmente un vector de cadenas), los combina en una sola cadena separada por el delimitador dado y coloca la cadena resultante en el campo de salida dado.
title: Merge
uuid: 9ca2ab22-d854-47b0-8189-f563c1e83d1c
exl-id: 75fa824b-f68d-4ec4-a75d-0f742a7bb1ba
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '254'
ht-degree: 4%

---

# Combinar{#merge}

La transformación Merge toma los valores del campo de entrada (normalmente un vector de cadenas), los combina en una sola cadena separada por el delimitador dado y coloca la cadena resultante en el campo de salida dado.

<table id="table_2458E008C9A14B31A774E6819D07E9BE"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parámetro </th> 
   <th colname="col2" class="entry"> Descripción </th> 
   <th colname="col3" class="entry"> Predeterminado </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Nombre </td> 
   <td colname="col2"> Nombre descriptivo de la transformación. Puede introducir cualquier nombre aquí. </td> 
   <td colname="col3"></td> 
  </tr> 
  <tr> 
   <td colname="col1"> Comentarios </td> 
   <td colname="col2"> Opcional. Notas sobre la transformación. </td> 
   <td colname="col3"></td> 
  </tr> 
  <tr> 
   <td colname="col1"> Condición </td> 
   <td colname="col2"> Condiciones en las que se aplica esta transformación. </td> 
   <td colname="col3"></td> 
  </tr> 
  <tr> 
   <td colname="col1"> Predeterminado </td> 
   <td colname="col2"> El valor predeterminado que se debe utilizar si se cumple la condición y el valor de entrada no está disponible. </td> 
   <td colname="col3"></td> 
  </tr> 
  <tr> 
   <td colname="col1"> Delimitador </td> 
   <td colname="col2"> <p>Cadena que se utiliza para separar los elementos individuales del vector de cadena de entrada en la cadena de salida única. </p> <p> Si mantiene pulsada la tecla Ctrl y hace clic con el botón derecho en el parámetro Delimitador, aparece un menú <span class="wintitle"> Insertar</span>. Este menú contiene una lista de caracteres especiales que a menudo se utilizan como delimitadores. </p> </td> 
   <td colname="col3"></td> 
  </tr> 
  <tr> 
   <td colname="col1"> Entrada </td> 
   <td colname="col2"> Un vector de valores de cadena que se combinan para formar la cadena de salida. </td> 
   <td colname="col3"></td> 
  </tr> 
  <tr> 
   <td colname="col1"> Salida </td> 
   <td colname="col2"> Nombre de la cadena de salida. </td> 
   <td colname="col3"></td> 
  </tr> 
 </tbody> 
</table>

En este ejemplo, se supone que un vector de entrada de cadenas contiene un conjunto de productos seleccionados para su compra. Estos productos se colocan en una sola cadena de salida y se separan con &quot;::&quot; (dos puntos).

![](assets/cfg_TransformationType_Merge.png)

Por lo tanto, si el campo de entrada x-products contenía los valores de cadena B57481, C46355 y Z97123, la cadena de salida x-show-products resultante sería B57481::C46355::Z97123.
