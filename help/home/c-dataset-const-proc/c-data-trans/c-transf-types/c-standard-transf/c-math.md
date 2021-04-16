---
description: La transformación Math permite el uso de operaciones aritméticas en campos dentro de las entradas de registro.
title: Math
uuid: 9e1a5950-8fb2-48e9-b9a1-82c5165fba10
exl-id: d8b9cacd-67d1-447c-94dd-7028aa371dfa
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '256'
ht-degree: 6%

---

# Math{#math}

La transformación Math permite el uso de operaciones aritméticas en campos dentro de las entradas de registro.

Las operaciones pueden incluir enteros decimales y constantes de coma flotante.

<table id="table_FDF3DDF1960E43E391A67C9DC2A0E302"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Campo </th> 
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
   <td colname="col1"> Expresión </td> 
   <td colname="col2"> <p>Expresión aritmética que describe el cálculo que se va a realizar. </p> <p> Puede utilizar cualquiera de las operaciones y funciones enumeradas a continuación y puede incorporar nombres de campo en la expresión: </p> <p> Operaciones 
     <ul id="ul_DB5915FADA0A41A3B11F1F48615F40A9">
      <li id="li_CA9EA97243F04760A81313C17EE057B3"> Adición (+) </li>
      <li id="li_908A272EBA2340098C20F22AA8D9ED26"> Resta (-) </li>
      <li id="li_C62257FF3AAB436D9148BBEA441621D7"> Multiplicación (*) </li>
      <li id="li_B5A9EAB3E49D4CB9A297172199F23542"> División (/) </li>
      <li id="li_D2D2B51DB2C8412A9B6F9D5F3CC03F8A"> Resto (%) </li>
      <li id="li_07E7E368FFD2437A852B785E159848E5"> Exponenciación (^) </li>
     </ul></p> <p>Funciones 
     <ul id="ul_E335AE8D684340AA998C4A2633FFDEE1">
      <li id="li_E036FF0B5DF244DDBFEDA9BFEDC62251"> sgn(x). Devuelve 1 si x es positivo, 0 si x es cero o -1 si x es negativo. </li>
      <li id="li_90CD8899DDC14778A95930C2768C82BC"> abs(x). Devuelve el valor absoluto de x. </li>
      <li id="li_F4AF23F343F74BD88B7166B1C2BB065E"> floor(x). Devuelve el entero bueno menor o igual que x. </li>
      <li id="li_A31379A3659240C3A629BFAF19A6DDF1"> round(x). Devuelve el entero más cercano a x. </li>
      <li id="li_9C0A0F3A4A304026B543F2A64B98B922"> log(b,x). Devuelve el logaritmo de x base b. </li>
      <li id="li_124D62C2CA5A42CBBCC5DB18FAA8920E"> min(x,y,...). Devuelve el menor de todos sus argumentos. </li>
      <li id="li_3B7B9FC1C0BF4E7688F9F49130B97B7F"> max(x,y,...). Devuelve el mayor de todos sus argumentos. </li>
     </ul></p> </td> 
   <td colname="col3"></td> 
  </tr> 
  <tr> 
   <td colname="col1"> Salida </td> 
   <td colname="col2"> Nombre del campo que contiene el resultado de la operación aritmética. </td> 
   <td colname="col3"></td> 
  </tr> 
 </tbody> 
</table>

En este ejemplo, que utiliza campos de datos recopilados del tráfico del sitio web, se calcula un nuevo campo denominado x-page-duration restando x-last-pv-timestamp de x-timestamp y, a continuación, añadiendo 1. El resultado se calcula únicamente si el campo definido por el usuario x-last-pv-timestamp (que representa la marca de tiempo de la última vista de página de un visitante), está relleno o &quot;no está vacío&quot;.

![](assets/cfg_TransformationType_Math.png)

Para obtener información sobre la condición [!DNL Not Empty], consulte [Condiciones](../../../../../home/c-dataset-const-proc/c-conditions/c-abt-cond.md).
