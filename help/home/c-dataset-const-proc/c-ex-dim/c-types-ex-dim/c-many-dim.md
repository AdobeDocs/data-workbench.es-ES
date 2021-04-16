---
description: Una dimensión "varios a varios" tiene una relación "varios a varios" con su dimensión contable principal.
title: Dimensión “varios a varios”
uuid: 42c909e8-1228-4210-9406-ffc0d92372fa
exl-id: 02d1a21c-a5b4-4b58-8089-9b9c68a7b1d1
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '400'
ht-degree: 3%

---

# Dimensión “varios a varios”{#many-to-many-dimensions}

Una dimensión &quot;varios a varios&quot; tiene una relación &quot;varios a varios&quot; con su dimensión contable principal.

Puede considerar una dimensión &quot;varios a varios&quot; como una representación de un conjunto de valores para cada elemento en su dimensión principal. Por ejemplo, la dimensión &quot;varios a varios&quot; Frase de búsqueda es una dimensión de nivel de sesión (tiene una dimensión principal Sesión). Representa el conjunto de frases de búsqueda asociadas a cada sesión en la dimensión Sesión . Se puede utilizar una sola frase de búsqueda en cualquier número de sesiones y una sola sesión puede incluir cero o más frases de búsqueda. Por lo tanto, la dimensión Frase de búsqueda tiene una relación &quot;varios a varios&quot; con la dimensión Sesión .

Las dimensiones &quot;varios a varios&quot; se definen mediante los siguientes parámetros:

<table id="table_A6D495008DFF4DD28A3ECD718D775E54"> 
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
   <td colname="col2"> Nombre descriptivo de la dimensión tal como aparece al usuario en Data Workbench. El nombre de la dimensión no puede incluir un guión (-). </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Comentarios </td> 
   <td colname="col2"> Opcional. Notas sobre la dimensión extendida. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Condición </td> 
   <td colname="col2"> Condiciones en las que se debe crear la relación entre el elemento principal y el valor del campo de entrada. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Oculto </td> 
   <td colname="col2"> Determina si la dimensión aparece en la interfaz de Data Workbench. De forma predeterminada, este parámetro se establece en false. Si, por ejemplo, la dimensión se va a utilizar solo como base de una métrica, puede establecer este parámetro en true para ocultar la dimensión de la visualización del Data Workbench. </td> 
   <td colname="col3"> false </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Entrada </td> 
   <td colname="col2"> <p>El valor relacionado con la dimensión principal (Principal). Si este campo es un vector de cadenas, cada elemento del vector tiene su propia relación con el elemento principal. </p> <p> <p>Nota:  Si el valor de entrada de cada entrada de registro de un elemento de la dimensión principal está vacío, ningún elemento de la dimensión "varios a varios" se relacionará con ese elemento de la dimensión principal. </p> </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Principal </td> 
   <td colname="col2"> Nombre de la dimensión principal. Cualquier dimensión contable puede ser una dimensión principal. </td> 
   <td colname="col3"> </td> 
  </tr> 
 </tbody> 
</table>

Este ejemplo ilustra la definición de una dimensión &quot;varios a varios&quot; mediante los datos de evento recopilados a partir del tráfico del sitio web. Esta dimensión &quot;varios a varios&quot;, denominada &quot;Producto seleccionado&quot;, relaciona las sesiones con los productos comprados por el visitante durante esa sesión. El campo x-products contiene un vector de valores, cada uno de los cuales está asociado a una vista de página que, a su vez, está asociado a una sesión.

![](assets/cfg_Transformation_Dim_ManytoMany.png)

Al crear una transformación de este tipo, puede crear una visualización en Data Workbench que represente la relación entre la dimensión del producto seleccionada y el número de sesiones que involucran a cada uno de los productos.
