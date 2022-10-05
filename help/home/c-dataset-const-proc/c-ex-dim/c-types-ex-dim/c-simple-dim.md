---
description: Una dimensión simple tiene una relación "uno a varios" con su dimensión contable principal.
title: Dimensiones simples
uuid: 3bca2354-02c4-4739-a7da-acccdb0efdfd
exl-id: 2acad750-7c48-40f1-8130-ab056ac8bf0d
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '834'
ht-degree: 1%

---

# Dimensiones simples{#simple-dimensions}

{{eol}}

Una dimensión simple tiene una relación &quot;uno a varios&quot; con su dimensión contable principal.

Una dimensión simple siempre es un elemento secundario de una dimensión contable. Puede considerar una dimensión simple como una representación de una propiedad de los elementos en su dimensión principal. Por ejemplo, si trabaja con datos web, podría definir la dimensión Referente del visitante , que es una dimensión simple con una dimensión principal del Visitante. Representa el primer referente HTTP para cada visitante en la dimensión Visitante . Cada visitante de la dimensión Visitante tiene un solo referente de visitante, pero muchos visitantes pueden tener el mismo referente de visitante. Por lo tanto, la dimensión Referente de visitante tiene una relación &quot;uno a varios&quot; con la dimensión Visitante.

Las dimensiones simples se definen mediante los siguientes parámetros:

<table id="table_E6F729DFA226459DBFC1776CE8CB81F8"> 
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
   <td colname="col1"> Comentarios </td> 
   <td colname="col2"> Opcional. Notas sobre la dimensión extendida. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Condición </td> 
   <td colname="col2"> Condiciones en las que se debe crear la relación entre el elemento Principal y el valor del campo de entrada. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Oculto </td> 
   <td colname="col2"> Determina si la dimensión aparece en la interfaz de Data Workbench. De forma predeterminada, este parámetro se establece en false. Si, por ejemplo, la dimensión se va a utilizar solo como base de una métrica, puede establecer este parámetro en true para ocultar la dimensión de la visualización del Data Workbench. </td> 
   <td colname="col3"> false </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Entrada </td> 
   <td colname="col2"> Campo de valores relacionado con la dimensión principal (Principal). </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Cargar archivo </td> 
   <td colname="col2"> <p>Opcional. Archivo de valores disponibles para la relación. Utilice un archivo de carga cuando se aplique cualquiera de las siguientes opciones: </p> <p> 
     <ul id="ul_056C4A8E46AA479397DC63173C035D5C"> 
      <li id="li_C26EB5A4AB3C4BEB8EB3A217A5A2377E"> Los valores tienen un orden de clasificación específico que se desea conservar en la visualización del Data Workbench. Por ejemplo, es posible que desee crear una dimensión de trimestre cuyos elementos (los trimestres del año) siempre se muestren en orden cronológico. </li> 
      <li id="li_5D4DF56BC6124D038A7260131B1F3DB3"> Desea crear marcadores de posición para valores que pueden no encontrarse en los datos pero que deben aparecer en la visualización del área de trabajo de datos. </li> 
     </ul> </p> <p> Si se encuentra un valor que no está presente en el archivo, se agrega al final de los valores cuando se visualiza en Data Workbench. </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Operación </td> 
   <td colname="col2"> <p>Las operaciones disponibles son las siguientes: </p> <p> 
     <ul id="ul_88AE4279413C42609D8B53EC64B5E913"> 
      <li id="li_DD9623D006844BC28B2AAA8E12AA04E1"> PRIMER NO EN BLANCO: Se utiliza el primer valor de entrada no vacío, independientemente de si procede de la primera entrada de registro. Si Input es un campo vectorial, se utiliza la primera fila del vector para la entrada de registro correspondiente. </li> 
      <li id="li_0FBE7F0B7B9744D994ECEDAA08F0045C"> PRIMERA FILA: Se utiliza el valor de la primera entrada de registro relacionada con el elemento de dimensión principal, aunque la entrada esté en blanco. Si Input es un campo vectorial, se utiliza la primera fila del vector para la entrada de registro correspondiente. Si este valor está vacío o no es un número, o si la entrada de registro correspondiente no cumple la condición de la dimensión, no se utiliza ningún valor. </li> 
      <li id="li_C17190BC699D4A099DC5326C07D1044D"> ÚLTIMO NO EN BLANCO: Se utiliza el último valor de entrada que no esté en blanco, independientemente de si procede de la última entrada de registro. Si Input es un campo vectorial, se utiliza la primera fila del vector para la entrada de registro correspondiente. </li> 
      <li id="li_00BAE86F12004C098F6A455908DB7062"> ÚLTIMA FILA: Se utiliza el valor de la última entrada de registro relacionada con el elemento de dimensión principal, aunque la entrada esté en blanco. Si Input es un campo vectorial, se utiliza la primera fila del vector para la entrada de registro correspondiente. Si este valor está vacío o no es un número, o si la entrada de registro correspondiente no cumple la condición de la dimensión, no se utiliza ningún valor. </li> 
     </ul> </p> <p> <p>Nota: Si Operation no genera ningún valor o un valor en blanco para una entrada de registro en particular, el elemento correspondiente de la dimensión principal se relaciona con el elemento "None" de la dimensión simple. </p> </p> <p> Debe especificar una operación para asegurarse de que la dimensión se define como está previsto. </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Principal </td> 
   <td colname="col2"> Nombre de la dimensión principal. Cualquier dimensión contable puede ser una dimensión principal. </td> 
   <td colname="col3"> </td> 
  </tr> 
 </tbody> 
</table>

Este ejemplo ilustra la definición de una dimensión simple mediante datos de evento recopilados del tráfico del sitio web y un archivo de carga.

Consideremos el ejemplo de una encuesta de las cookies favoritas de Girl Scout de los visitantes del sitio. Una página web captura este voto y lo devuelve al servidor web en la cookie favoritecookie del par nombre-valor. Solo se cuenta un voto por visitante, pero los visitantes pueden cambiar de opinión y votar de nuevo si lo desean. Esta es una relación uno a varios: un visitante puede tener muchos votos, pero cada voto está asociado con un solo visitante. Por lo tanto, el elemento principal de la dimensión son los visitantes (solo un voto por visitante) y la operación es ÚLTIMA FILA (para que puedan cambiar de opinión y votar de nuevo).

Los marcadores de posición deben existir para todos los tipos de cookies, de modo que se muestren los tipos de cookies que no reciben votos en Data Workbench. Por estos motivos, se ha definido un archivo de carga que contiene la lista de tipos de cookies que se pueden seleccionar. El contenido de este archivo, guardado en un archivo denominado [!DNL cookietypes.txt], tiene un aspecto similar al siguiente:

Tesoros animales

Luces de Caramelo

Cremas de bollería de limón

Patentes de manteca de cacahuete

Combinaciones de teclas

Puntos finos

La dimensión final se define como se muestra aquí:

![](assets/cfg_Transformation_Dim_Simple.png)
