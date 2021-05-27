---
description: Una dimensión numérica consta de elementos numéricos ordenados y tiene una relación "uno a varios" con su dimensión contable principal.
title: Dimensiones numéricas
uuid: 19fab770-1535-41b2-bad1-811eba5f3575
exl-id: 69a4dfa6-8402-4c2b-8b04-e6e1a0fd5ccb
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '990'
ht-degree: 2%

---

# Dimensiones numéricas{#numeric-dimensions}

Una dimensión numérica consta de elementos numéricos ordenados y tiene una relación &quot;uno a varios&quot; con su dimensión contable principal.

Una dimensión numérica se puede considerar como una representación de las propiedades numéricas de los elementos de la dimensión principal. Por ejemplo, si está trabajando con datos web, puede definir la dimensión numérica Ingresos de sesión, que define una cantidad de ingresos, en dólares, para cada sesión en la dimensión Sesión . Cada sesión tiene una única cantidad de ingresos asociados, pero varias sesiones pueden tener la misma cantidad de ingresos asociados. Por lo tanto, la dimensión Ingresos de sesión tiene una relación &quot;uno a varios&quot; con la dimensión Sesión .

Las dimensiones numéricas se utilizan a menudo para definir métricas que suman valores, cuenten ocurrencias de una condición o localicen un valor mínimo o máximo. Por ejemplo, se puede definir una métrica denominada &quot;Ingresos&quot; mediante la dimensión Ingresos de sesión: sum(Session_Revenue, Session). Definida de esta manera, la métrica Ingresos daría la cantidad total de ingresos para las sesiones seleccionadas.

Las dimensiones numéricas no pueden ser elementos primarios de otras dimensiones.

Las dimensiones numéricas se definen mediante los siguientes parámetros:

<table id="table_15B849DD0BFC4D57AD6CF28898901324"> 
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
   <td colname="col2"> Nombre descriptivo de la dimensión tal como aparece en Data Workbench. El nombre de la dimensión no puede incluir un guión (-). </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Valores de clip </td> 
   <td colname="col2"> Verdadero o falso. Especifica si el valor de entrada (después de Operación ) se va a recortar para que esté entre los valores Mínimo y Máx. Si los valores de clip son verdaderos, el valor se recorta a ese intervalo. Si los valores de clip son falsos, no se devuelve ningún valor para el elemento de la dimensión principal. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Comentarios </td> 
   <td colname="col2"> Opcional. Notas sobre la dimensión extendida. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Condición </td> 
   <td colname="col2"> Condiciones bajo las cuales el campo de entrada contribuye a la creación de la dimensión numérica. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Tamaño fijo </td> 
   <td colname="col2"> Verdadero o falso. Controla el número de elementos de una dimensión (cardinalidad). Si es true, todos los elementos desde Min hasta Max se incluyen en la dimensión. Si es false, el tamaño de la dimensión aumenta a medida que se añaden valores. </td> 
   <td colname="col3"> false </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Oculto </td> 
   <td colname="col2"> Determina si la dimensión aparece en la interfaz de Data Workbench. De forma predeterminada, este parámetro se establece en false. Si, por ejemplo, la dimensión se va a utilizar solo como base de una métrica, puede establecer este parámetro en true para ocultar la dimensión de la visualización del Data Workbench. </td> 
   <td colname="col3"> false </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Entrada </td> 
   <td colname="col2"> <p>El valor que se va a utilizar con la operación especificada o el valor de entrada para el que se desea contar las ocurrencias. </p> <p> Si este campo es un vector de cadenas, la evaluación se produce para cada elemento del vector. Por ejemplo, un vector con longitud 3 y una operación de RECUENTO añaden 3 al recuento. </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Mínimo </td> 
   <td colname="col2"> Límite inferior del resultado final de la dimensión. </td> 
   <td colname="col3"> 0 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Máximo </td> 
   <td colname="col2"> Límite superior del resultado final de la dimensión. </td> 
   <td colname="col3"> 1e6 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Desplazamiento </td> 
   <td colname="col2"> Consulte Escala en esta tabla. </td> 
   <td colname="col3"> 0 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Operación </td> 
   <td colname="col2"> <p>Las operaciones disponibles son las siguientes: </p> <p> 
     <ul id="ul_E04733E5E8824A2BAAB90D9356078D99"> 
      <li id="li_CAEE9167D45540BEAC538345F250B509"> RECUENTO: Se utiliza el número total de valores no vacíos en el campo <span class="wintitle"> Entrada</span> de todas las entradas de registro que cumplen la condición de la dimensión. Si el campo <span class="wintitle"> Entrada</span> es un campo vectorial, se cuenta el número total de valores no vacíos en cada entrada de registro. </li> 
      <li id="li_64A4D671E78642BD9A9334F8098450B9"> PRIMER NO EN BLANCO: Se utiliza el primer valor de entrada no vacío, independientemente de si procede de la primera entrada de registro. Si <span class="wintitle"> Entrada</span> es un campo vectorial, se utiliza la primera fila del vector para la entrada de registro correspondiente. Si el valor no es un número, no se utiliza ningún valor. </li> 
      <li id="li_C967964729BD4A638FF78D8883CE513F"> PRIMERA FILA: Se utiliza el valor de la primera entrada de registro relacionada con el elemento de dimensión principal, aunque la entrada esté en blanco. Si <span class="wintitle"> Entrada</span> es un campo vectorial, se utiliza la primera fila del vector para la entrada de registro correspondiente. Si este valor está vacío o no es un número, o si la entrada de registro correspondiente no cumple la condición de la dimensión, no se utiliza ningún valor. </li> 
      <li id="li_74171B17F480478B8547E1A361B22DA4"> ÚLTIMO NO EN BLANCO: Se utiliza el último valor de entrada que no esté en blanco, independientemente de si procede de la última entrada de registro. Si <span class="wintitle"> Entrada</span> es un campo vectorial, se utiliza la primera fila del vector para la entrada de registro correspondiente. Si el valor no es un número, no se utiliza ningún valor. </li> 
      <li id="li_1253ECF507BD4BBF97CBB2FA12915045"> ÚLTIMA FILA: Se utiliza el valor de la última entrada de registro relacionada con el elemento de dimensión principal, aunque la entrada esté en blanco. Si <span class="wintitle"> Entrada</span> es un campo vectorial, se utiliza la primera fila del vector para la entrada de registro correspondiente. Si este valor está vacío o no es un número, o si la entrada de registro correspondiente no cumple la condición de la dimensión, no se utiliza ningún valor. </li> 
      <li id="li_20819E3944544F98853D6A02814F47B2"> SUMA: Se utiliza el total de todos los valores numéricos del campo <span class="wintitle"> Input</span> en todas las entradas de registro que cumplen la condición de la dimensión. Si no se encuentran estas entradas de registro o no se encuentran valores numéricos, se utiliza el valor numérico 0. </li> 
      <li id="li_086C2E57604B4645A9203A984C6F9A04">MIN o MAX: Se utiliza el valor numérico mínimo o máximo que se encuentra en el campo <span class="wintitle"> Input</span> en todas las entradas de registro que cumplen la condición de la dimensión. Si no hay tales entradas de registro o no hay valores numéricos, no se utiliza ningún valor. </li> 
     </ul> </p> <p> <p>Nota:  Debe especificar una operación para asegurarse de que la dimensión se define como está previsto. </p> </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Principal </td> 
   <td colname="col2"> Nombre de la dimensión principal. Cualquier dimensión contable puede ser una dimensión principal. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Escala </td> 
   <td colname="col2"> <p>Para obtener el valor ordinal de la dimensión, el resultado de la operación se transforma de la siguiente manera: </p> <p> (escala * entrada) + desplazamiento </p> </td> 
   <td colname="col3"> 1.0 </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>Si [!DNL Operation] no genera ningún valor o [!DNL Clip Values] es falso y el valor no está entre [!DNL Min] y [!DNL Max], ningún elemento de la dimensión numérica está relacionado con el elemento de la dimensión principal.

Este ejemplo ilustra la definición de una dimensión numérica mediante los datos de evento recopilados del tráfico del sitio web. Esta dimensión numérica, denominada &quot;Contador de vista de anuncio&quot;, cuenta la cantidad de veces que el visitante ve un anuncio durante una sesión determinada. Se supone que todos los recursos de publicidad se solicitan al servidor web con ad= como parte de la consulta cs-uri. En el ejemplo, el número de veces (COUNT) que se presenta al visitante con un anuncio es el valor del interés, no el valor real del campo.

![](assets/cfg_Transformation_Dim_Numeric.png)
