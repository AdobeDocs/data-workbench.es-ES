---
description: La leyenda de procesamiento proporciona información detallada sobre el procesamiento y la transformación de datos de un servidor en particular, lo que permite realizar un seguimiento del progreso de los datos que se están reprocesando y retransformando.
title: Leyenda de procesamiento
uuid: 6c082c8f-fbb3-4e48-a249-2a13345fda86
exl-id: a83ce514-c92b-4cf8-a3cc-bff4e2ba63f1
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '214'
ht-degree: 2%

---

# Leyenda de procesamiento{#processing-legend}

{{eol}}

La leyenda de procesamiento proporciona información detallada sobre el procesamiento y la transformación de datos de un servidor en particular, lo que permite realizar un seguimiento del progreso de los datos que se están reprocesando y retransformando.

![](assets/vis_ProcessingLegend.png)

La tabla siguiente enumera las tareas que se pueden completar utilizando la variable [!DNL Processing Legend].

<table id="table_6149250C44B14C44A3CB1CEF68B280C6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Para realizar esta tarea... </th> 
   <th colname="col2" class="entry"> Instrucciones </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Para ver el tamaño total de todos los datos </p> </td> 
   <td colname="col2"> <p>Revise los valores de la variable <span class="wintitle"> Entradas de registro totales</span> y <span class="wintitle"> Total de bytes de registro</span> campos. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Para comprobar si el filtrado funciona </p> </td> 
   <td colname="col2"> <p>Revise los valores de la variable <span class="wintitle"> Total de entradas de registro filtradas</span> campos. Si el valor es 0, el filtrado no funciona y debe comprobar la configuración para solucionar el problema. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Para comprobar el progreso del procesamiento de registros </p> </td> 
   <td colname="col2"> <p>Revise el valor en la variable <span class="wintitle"> Progreso del procesamiento de registros</span> campo . Este porcentaje indica cuánto del reprocesamiento se ha completado. </p> <p>Al reprocesar para restringir el conjunto de datos, es posible que desee tener en cuenta el número de <span class="wintitle"> Total de entradas de registro descodificadas</span> frente al número de <span class="wintitle"> Total de entradas de registro filtradas</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Para comprobar el progreso de la transformación </p> </td> 
   <td colname="col2"> <p>Revise el valor en la variable <span class="wintitle"> Progreso de la transformación</span> campo . Este porcentaje indica cuánto de la transformación se ha completado. </p> </td> 
  </tr> 
 </tbody> 
</table>
