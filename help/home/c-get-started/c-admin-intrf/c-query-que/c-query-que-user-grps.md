---
description: Tabla que define los parámetros del grupo de usuarios.
solution: Analytics
title: Grupos de usuarios de la cola de consultas
topic: Data workbench
uuid: 90d9058c-1809-4579-a8c6-930a07affc83
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Grupos de usuarios de la cola de consultas{#query-queue-user-groups}

Tabla que define los parámetros del grupo de usuarios.

<table id="table_670A47E25A7A43F0B599BD7ABB173E69"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Campo </th> 
   <th colname="col2" class="entry"> Tipo </th> 
   <th colname="col3" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Nombre </p> </td> 
   <td colname="col2"> <p>string </p> </td> 
   <td colname="col3"> <p>Nombre definido por el usuario del grupo de usuarios, como por ejemplo Analistas. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Políticas </p> </td> 
   <td colname="col2"> <p>vector </p> </td> 
   <td colname="col3"> <p>Especifica un tipo de directiva. Haga clic con el botón derecho para elegir Política estándar o Programación diaria. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Política estándar </p> </td> 
   <td colname="col2"> </td> 
   <td colname="col3"> <p>Una directiva estándar garantiza que los usuarios con una prioridad baja se muevan de forma incremental hacia arriba en la cola y se programen, incluso si los usuarios con mayor prioridad entran en la cola. Puede agregar varias directivas del mismo tipo en un grupo y su efecto es acumulativo. 
     <ul id="ul_F7F60D23DC934F61AF2183177A11FA65"> 
      <li id="li_805ED3E740814FAEBFF2B411BAB3D248"><b>Límite de prioridad:</b> Límite por encima del cual no se incrementa la prioridad. El valor de prioridad máximo. Puede utilizar este valor para mantener las prioridades generadas por esta política en un rango específico (por ejemplo, para que las prioridades de algún otro grupo de usuarios sean siempre más altas, o para que no superen la prioridad intocable. </li> 
     </ul> </p> <p> <b>Incrementos de directiva estándar</b> </p> <p>La configuración de incremento de la directiva estándar aumenta la prioridad de un grupo de consultas a medida que pasa el tiempo. Esto no fuerza la programación de los paquetes, pero puede utilizar esta configuración para priorizar a los usuarios que han estado esperando durante mucho tiempo. Los parámetros en cola afectan a las consultas que están actualmente en cola (por ejemplo, en espera debido a que no hay recursos suficientes para completarlas). Los parámetros programados afectan a las consultas que se están respondiendo. La prioridad de una consulta aumenta según el número especificado en los campos de incremento e intervalo de incremento correspondientes: 
     <ul id="ul_7A5EE18CE10E4484A203B938525C806C"> 
      <li id="li_4B5CD827AF3848DA811A96C851340518"><b>Aumento en cola:</b> Establece el incremento de prioridad por actualización mientras se coloca en cola. Esta configuración garantiza que los usuarios con baja prioridad se muevan hacia arriba en la cola de programación. </li> 
      <li id="li_91CA798235234A1CAC7AB32A7FB1CE84"><b>Intervalo de aumento en cola:</b> Define el número de segundos entre las actualizaciones mientras se ponen en cola. </li> 
      <li id="li_079275E21ABA43B796A853624A6BDC29"><b>Incremento programado:</b> Establece el incremento de prioridad por actualización durante la programación. </li> 
      <li id="li_3AE2EC3EBE6C4670BA0FA1BBD03FEBBD"><b>Intervalo de aumento programado:</b> Define el número de segundos entre las actualizaciones durante la programación. <p> <p>Nota:  La configuración de las tasas de actualización de intervalo y aumento más altas para los paquetes en cola que para los paquetes programados puede provocar oscilación. (Por ejemplo, supongamos que establece el valor de Incremento en cola en 100 y el aumento programado en 0, y establece el valor de Intervalo de aumento en cola en 1 y la prioridad intocable en alta. Si hay dos paquetes de consultas con una prioridad base de 0 y no hay suficientes recursos para ejecutar ambas consultas al mismo tiempo, entonces se programa uno de ellos. Después de un segundo, la consulta que no se programó tiene una prioridad de 100 y se adelanta a la programada. Después de dos segundos más, el que estaba anticipado ahora tiene una prioridad de 200, y los dos switches se colocan de nuevo. Ninguna consulta termina, porque cada dos segundos la consulta que se está calculando tiene preferencia para que se pueda ejecutar la otra consulta). </p> </p> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Política de programación diaria </p> </td> 
   <td colname="col2"> </td> 
   <td colname="col3"> <p>Permite cambiar la prioridad en momentos específicos del día. Esta programación resulta útil para clientes automatizados, como <span class="wintitle"> el servidor</span>de informes, y cuando los usuarios del sistema viven en diferentes zonas horarias. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Cambios </p> </td> 
   <td colname="col2"> <p>int </p> </td> 
   <td colname="col3"> <p>Haga clic con el botón secundario para agregar un cambio de prioridad programado. La hora de cambio es la hora del día en que se produce el cambio. El formato es hora:minutos AM/PM. Si no se ingresa a la AM o al PM, el sistema utiliza el tiempo militar. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Límite de prioridad </p> </td> 
   <td colname="col2"> <p>int </p> </td> 
   <td colname="col3"> <p>El valor de prioridad máximo resultante de un cambio. El cambio de prioridad es la cantidad agregada a la prioridad. Por ejemplo, un valor de 0 devuelve a una prioridad predeterminada. Cualquier otro valor resulta en una prioridad de la prioridad predeterminada más este número. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Usuarios </p> </td> 
   <td colname="col2"> <p>vector </p> </td> 
   <td colname="col3"> <p>Enumera los usuarios que son miembros del grupo. </p> <p> <b>Nombre:</b> Nombre del usuario tal como aparece en el campo Nombre común del certificado del usuario. </p> <p> <b>Prioridad adicional:</b> Proporciona prioridad adicional a la prioridad base del grupo de usuarios para determinar la prioridad de inicio para ese usuario. </p> </td> 
  </tr> 
 </tbody> 
</table>

