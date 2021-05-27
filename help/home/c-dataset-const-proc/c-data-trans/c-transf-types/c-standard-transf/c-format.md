---
description: La transformación Formato toma un conjunto de entradas y las da formato para crear una salida que coincida con la estructura dada.
title: Formato
uuid: c596902e-21bc-4ce6-9ca4-7ca86dfc0a6c
exl-id: 842b502e-cd16-45b3-ada8-6f2d899f1d54
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '327'
ht-degree: 3%

---

# Formato{#format}

La transformación Formato toma un conjunto de entradas y las da formato para crear una salida que coincida con la estructura dada.

La transformación funciona tanto en cadenas simples como en vectores de cadenas y produce resultados aplicando el formato dado a cada valor de entrada hasta que se han transformado todos los valores de entrada.

<table id="table_3953C993167248AA9A47964A51C4AB5D"> 
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
   <td colname="col1"> Formato </td> 
   <td colname="col2"> <p>Cadena de formato utilizada para especificar el aspecto que tendrá el resultado. </p> <p> %1% hace referencia a un valor del primer vector de entrada, %2% hace referencia a un valor del segundo vector de entrada, etc. </p> </td> 
   <td colname="col3"></td> 
  </tr> 
  <tr> 
   <td colname="col1"> Entradas </td> 
   <td colname="col2"> <p>Campos que contienen cadenas simples o vectores de cadenas. En el caso de los vectores de cadena como entradas, la salida también será un vector de cadena resultante de la aplicación del parámetro <span class="wintitle"> Format</span> a cada conjunto de valores de entrada. </p> <p> <p>Nota:  La numeración de las entradas comienza en 0, pero la numeración de los valores de sustitución de formato comienza en %1%. </p> </p> </td> 
   <td colname="col3"></td> 
  </tr> 
  <tr> 
   <td colname="col1"> Salida </td> 
   <td colname="col2"> Nombre del campo creado para contener los resultados de la transformación. Si las entradas son vectores de cadena, la longitud del vector de cadena de salida será la longitud del vector de entrada más largo. Si algunos de los vectores de cadena de entrada tienen una longitud menor, se utilizan cadenas vacías para su posición en la cadena de formato hasta que se alcance la longitud del vector de salida. </td> 
   <td colname="col3"></td> 
  </tr> 
 </tbody> 
</table>

En este ejemplo, dos vectores, uno un vector de cadenas que representa las categorías de productos y el otro un vector de cadena correspondiente que representa la cantidad de cada producto comprado, se transforman en un solo vector de longitud equivalente que adopta la forma: Producto %1%, Cantidad %2%.

![](assets/cfg_TransformationType_Format.png)

Si los vectores de entrada contenían categorías de producto de (683, 918) y cantidades de (10, 4), el resultado sería un vector de salida final que contenía las dos cadenas siguientes: (&quot;Product 683, Quantity 10&quot;, &quot;Product 918, Quantity 4&quot;).
