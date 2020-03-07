---
description: La transformación Formato toma un conjunto de entradas y les da formato para crear una salida que coincida con la estructura dada.
solution: Analytics
title: Formato
topic: Data workbench
uuid: c596902e-21bc-4ce6-9ca4-7ca86dfc0a6c
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Formato{#format}

La transformación Formato toma un conjunto de entradas y les da formato para crear una salida que coincida con la estructura dada.

La transformación funciona con cadenas simples o vectores de cadena y produce resultados aplicando el formato dado a cada valor de entrada hasta que se han transformado todos los valores de entrada.

<table id="table_3953C993167248AA9A47964A51C4AB5D"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parámetro </th> 
   <th colname="col2" class="entry"> Descripción </th> 
   <th colname="col3" class="entry"> Valor predeterminado </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Nombre </td> 
   <td colname="col2"> Nombre descriptivo de la transformación. Aquí puede introducir cualquier nombre. </td> 
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
   <td colname="col1"> Formato </td> 
   <td colname="col2"> <p>Cadena de formato utilizada para especificar el aspecto que tendrá el resultado. </p> <p> %1% hace referencia a un valor del primer vector de entrada, %2% hace referencia a un valor del segundo vector de entrada, etc. </p> </td> 
   <td colname="col3"></td> 
  </tr> 
  <tr> 
   <td colname="col1"> Entradas </td> 
   <td colname="col2"> <p>Campos que contienen cadenas simples o vectores de cadena. En el caso de los vectores de cadena como entradas, el resultado también será un vector de cadena resultante de la aplicación del parámetro <span class="wintitle"> Format</span> a cada conjunto de valores de entrada. </p> <p> <p>Nota:  La numeración de entradas comienza en 0, pero la numeración de los valores de sustitución de formato comienza en %1%. </p> </p> </td> 
   <td colname="col3"></td> 
  </tr> 
  <tr> 
   <td colname="col1"> Salida </td> 
   <td colname="col2"> Nombre del campo creado para contener los resultados de la transformación. Si las entradas son vectores de cadena, la longitud del vector de cadena de salida será la longitud del vector de entrada más largo. Si algunos vectores de cadena de entrada tienen una longitud más corta, se utilizan cadenas vacías para su posición en la cadena de formato hasta que se alcanza la longitud del vector de salida. </td> 
   <td colname="col3"></td> 
  </tr> 
 </tbody> 
</table>

En este ejemplo, dos vectores, uno un vector de cadenas que representa categorías de productos y el otro un vector de cadena correspondiente que representa la cantidad de cada producto comprado, se transforman en un solo vector de longitud equivalente que adopta la forma: Producto %1%, Cantidad %2%.

![](assets/cfg_TransformationType_Format.png)

Si los vectores de entrada contenían categorías de productos de (683, 918) y cantidades de (10, 4), el resultado sería un vector de salida final que contuviera las dos cadenas siguientes: (&quot;Producto 683, Cantidad 10&quot;, &quot;Producto 918, Cantidad 4&quot;).
