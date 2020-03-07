---
description: Una dimensión simple tiene una relación uno a varios con su dimensión contable principal.
solution: Analytics
title: Dimensiones simples
topic: Data workbench
uuid: 3bca2354-02c4-4739-a7da-acccdb0efdfd
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Dimensiones simples{#simple-dimensions}

Una dimensión simple tiene una relación uno a varios con su dimensión contable principal.

Una dimensión simple es siempre un elemento secundario de una dimensión contable. Una dimensión simple se puede considerar como una representación de una propiedad de los elementos en su dimensión principal. Por ejemplo, si está trabajando con datos web, podría definir la dimensión Referente del visitante, que es una dimensión simple con una dimensión principal de Visitante. Representa el primer referente HTTP para cada visitante en la dimensión Visitante. Cada visitante en la dimensión Visitante tiene un solo referente de visitante, pero muchos visitantes pueden tener el mismo referente de visitante. Por lo tanto, la dimensión Referente del visitante tiene una relación uno a varios con la dimensión Visitante.

Las dimensiones simples se definen con los parámetros siguientes:

<table id="table_E6F729DFA226459DBFC1776CE8CB81F8"> 
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
   <td colname="col2"> Nombre descriptivo de la dimensión tal como aparece en el área de trabajo de datos. El nombre de la dimensión no puede incluir un guión (-). </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Comentarios </td> 
   <td colname="col2"> Opcional. Notas sobre la dimensión extendida. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Condición </td> 
   <td colname="col2"> Condiciones en las que se debe crear la relación entre el valor del campo Principal y el valor del campo de entrada. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Oculto </td> 
   <td colname="col2"> Determina si la dimensión aparece en la interfaz del área de trabajo de datos. De forma predeterminada, este parámetro se establece en false. Si, por ejemplo, la dimensión se va a utilizar solo como base de una métrica, puede establecer este parámetro en true para ocultar la dimensión de la visualización del área de trabajo de datos. </td> 
   <td colname="col3"> false </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Entrada </td> 
   <td colname="col2"> Campo de valores relacionado con la dimensión principal (Principal). </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Cargar archivo </td> 
   <td colname="col2"> <p>Opcional. Archivo de valores disponibles para la relación. Se utiliza un archivo de carga cuando se aplica cualquiera de los siguientes procedimientos: </p> <p> 
     <ul id="ul_056C4A8E46AA479397DC63173C035D5C"> 
      <li id="li_C26EB5A4AB3C4BEB8EB3A217A5A2377E"> Los valores tienen un orden específico que se desea conservar en la pantalla del área de trabajo de datos. Por ejemplo, es posible que desee crear una dimensión Trimestre cuyos elementos (los trimestres del año) siempre se muestren en orden cronológico. </li> 
      <li id="li_5D4DF56BC6124D038A7260131B1F3DB3"> Desea crear marcadores de posición para valores que no se encuentran en los datos pero que deben aparecer en la pantalla del área de trabajo de datos. </li> 
     </ul> </p> <p> Si se encuentra un valor que no está presente en el archivo, se agrega al final de los valores cuando se ve en el área de trabajo de datos. </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Operación </td> 
   <td colname="col2"> <p>Las operaciones disponibles son las siguientes: </p> <p> 
     <ul id="ul_88AE4279413C42609D8B53EC64B5E913"> 
      <li id="li_DD9623D006844BC28B2AAA8E12AA04E1"> PRIMERA NO BLANCA: Se utiliza el primer valor de entrada no en blanco, independientemente de si procede de la primera entrada de registro. Si Input es un campo vectorial, se utiliza la primera fila del vector para la entrada de registro correspondiente. </li> 
      <li id="li_0FBE7F0B7B9744D994ECEDAA08F0045C"> PRIMERA FILA: Se utiliza el valor de la primera entrada de registro relacionada con el elemento de dimensión principal, aunque la entrada esté en blanco. Si Input es un campo vectorial, se utiliza la primera fila del vector para la entrada de registro correspondiente. Si este valor está en blanco o no es un número, o si la entrada de registro pertinente no cumple la condición de la dimensión, no se utiliza ningún valor. </li> 
      <li id="li_C17190BC699D4A099DC5326C07D1044D"> ÚLTIMO NO EN BLANCO: Se utiliza el último valor de entrada que no está en blanco, independientemente de si procede de la última entrada de registro. Si Input es un campo vectorial, se utiliza la primera fila del vector para la entrada de registro correspondiente. </li> 
      <li id="li_00BAE86F12004C098F6A455908DB7062"> ÚLTIMA FILA: Se utiliza el valor de la última entrada de registro relacionada con el elemento de dimensión principal, aunque la entrada esté en blanco. Si Input es un campo vectorial, se utiliza la primera fila del vector para la entrada de registro correspondiente. Si este valor está en blanco o no es un número, o si la entrada de registro pertinente no cumple la condición de la dimensión, no se utiliza ningún valor. </li> 
     </ul> </p> <p> <p>Nota:  Si Operation no produce ningún valor o un valor en blanco para una entrada de registro en particular, el elemento correspondiente de la dimensión principal se relacionará con el elemento "None" de la dimensión simple. </p> </p> <p> Debe especificar una operación para asegurarse de que la dimensión se define de la forma prevista. </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Principal </td> 
   <td colname="col2"> Nombre de la dimensión principal. Cualquier dimensión contable puede ser una dimensión principal. </td> 
   <td colname="col3"> </td> 
  </tr> 
 </tbody> 
</table>

Este ejemplo ilustra la definición de una dimensión sencilla mediante el uso de datos de eventos recopilados a partir del tráfico del sitio web y de un archivo de carga.

Considere el ejemplo de una encuesta de las cookies favoritas de Girl Scout de los visitantes del sitio. Una página web captura este voto y lo devuelve al servidor web en la cookie de pares nombre-valor. Solo se cuenta un voto por visitante, pero los visitantes pueden cambiar de opinión y votar nuevamente si lo desean. Esta es una relación uno a varios: un visitante puede tener muchos votos, pero cada voto está asociado con un solo visitante. Por lo tanto, el elemento principal de la dimensión son los visitantes (solo un voto por visitante) y la operación es ÚLTIMA FILA (para que puedan cambiar de opinión y votar nuevamente).

Los marcadores de posición deben existir para todos los tipos de cookies, de modo que los tipos de cookies que no reciben votos aparezcan en la pantalla del área de trabajo de datos. Por estos motivos, se ha definido un archivo de carga que contiene la lista de tipos de cookies que se pueden seleccionar. El contenido de este archivo, guardado en un archivo llamado [!DNL cookietypes.txt], tiene un aspecto similar al siguiente:

Tesoros animales

Luces de Caramelo

Cremas de bollería de limón

Patas de mantequilla de cacahuate

Combinaciones de teclas

Puntos finos

La dimensión final se define como se muestra a continuación:

![](assets/cfg_Transformation_Dim_Simple.png)

