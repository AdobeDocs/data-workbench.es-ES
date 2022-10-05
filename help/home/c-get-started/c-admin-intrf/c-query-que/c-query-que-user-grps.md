---
description: Tabla que define los parámetros del grupo de usuarios.
title: Grupos de usuarios de la cola de consulta
uuid: 90d9058c-1809-4579-a8c6-930a07affc83
exl-id: e9586ad4-4c0b-48b7-b533-4d23a0f4a216
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '611'
ht-degree: 2%

---

# Grupos de usuarios de la cola de consulta{#query-queue-user-groups}

{{eol}}

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
   <td colname="col3"> <p>Un nombre definido por el usuario del grupo de usuarios, como los analistas. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Políticas </p> </td> 
   <td colname="col2"> <p>vector </p> </td> 
   <td colname="col3"> <p>Especifica un tipo de directiva. Haga clic con el botón derecho para elegir Política estándar o Programación diaria. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Política estándar </p> </td> 
   <td colname="col2"> </td> 
   <td colname="col3"> <p>Una directiva estándar garantiza que los usuarios con una prioridad baja se muevan gradualmente hacia arriba en la cola y se programen, incluso si los usuarios con mayor prioridad entran en la cola. Puede agregar varias directivas del mismo tipo en un grupo y su efecto es acumulativo. 
     <ul id="ul_F7F60D23DC934F61AF2183177A11FA65"> 
      <li id="li_805ED3E740814FAEBFF2B411BAB3D248"><b>Límite de prioridad:</b> Límite por encima del cual no se incrementa la prioridad. El valor de prioridad máximo. Puede utilizar este valor para mantener las prioridades generadas por esta política en un rango específico (por ejemplo, para que las prioridades de otros grupos de usuarios siempre sean más altas, o para que no superen la Prioridad intocable. </li> 
     </ul> </p> <p> <b>Incrementos de directiva estándar</b> </p> <p>La configuración de incremento de la directiva estándar aumenta la prioridad de un grupo de consultas a medida que pasa el tiempo. Esto no obliga a que los paquetes se programen, pero puede utilizar esta configuración para priorizar a los usuarios que han estado esperando durante mucho tiempo. Los parámetros en cola afectan a las consultas que están en cola actualmente (por ejemplo, en espera debido a que no hay recursos suficientes para completarlas). Los parámetros programados afectan a las consultas a las que se está respondiendo. La prioridad de una consulta aumenta por el número especificado en los campos de incremento e intervalo de incremento correspondientes: 
     <ul id="ul_7A5EE18CE10E4484A203B938525C806C"> 
      <li id="li_4B5CD827AF3848DA811A96C851340518"><b>Incremento en cola:</b> Establece el incremento de prioridad por actualización mientras se pone en cola. Esta configuración garantiza que los usuarios de baja prioridad se muevan hacia arriba en la cola de programación. </li> 
      <li id="li_91CA798235234A1CAC7AB32A7FB1CE84"><b>Intervalo de aumento en cola:</b> Define el número de segundos entre actualizaciones mientras se ponen en cola. </li> 
      <li id="li_079275E21ABA43B796A853624A6BDC29"><b>Incremento programado:</b> Establece el incremento de prioridad por actualización mientras está programado. </li> 
      <li id="li_3AE2EC3EBE6C4670BA0FA1BBD03FEBBD"><b>Intervalo de incremento programado:</b> Define el número de segundos entre actualizaciones mientras se programan. <p> <p>Nota: Configurar las tasas de actualización de incrementos e intervalos más altas para los paquetes en cola que para los paquetes programados puede causar oscilación. (Por ejemplo, supongamos que establece el valor Incremento en cola en 100 y el Incremento programado en 0, y establece el valor Intervalo de incremento en cola en 1 y la Prioridad intocable en alta. Si hay dos paquetes de consulta que tienen una prioridad base de 0 y no hay suficientes recursos para ejecutar ambas consultas al mismo tiempo, entonces uno de ellos está programado. Después de un segundo, la consulta que no se programó tiene una prioridad de 100, y prevalece sobre la que se programó. Después de dos segundos más, el que estaba prevenido ahora tiene una prioridad de 200, y los dos switches se colocan de nuevo. Ninguna de las consultas finaliza, ya que cada dos segundos la consulta que se está calculando tiene preferencia para que se pueda ejecutar la otra consulta). </p> </p> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Política de programación diaria </p> </td> 
   <td colname="col2"> </td> 
   <td colname="col3"> <p>Permite cambiar la prioridad en momentos específicos del día. Esta programación resulta útil para los clientes automatizados, como <span class="wintitle"> Servidor de informes</span>y cuando los usuarios del sistema viven en diferentes zonas horarias. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Cambios </p> </td> 
   <td colname="col2"> <p>int </p> </td> 
   <td colname="col3"> <p>Haga clic con el botón derecho para añadir un cambio de prioridad programado. La hora de cambio es la hora del día en que se produce el cambio. El formato es hora:minutos AM/PM. Si AM o PM no ingresan, el sistema usa tiempo militar. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Límite de prioridad </p> </td> 
   <td colname="col2"> <p>int </p> </td> 
   <td colname="col3"> <p>El valor de prioridad máximo resultante de un cambio. El cambio de prioridad es la cantidad añadida a la prioridad. Por ejemplo, un valor de 0 devuelve a una prioridad predeterminada. Cualquier otro valor resulta en una prioridad de la prioridad predeterminada más este número. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Usuarios </p> </td> 
   <td colname="col2"> <p>vector </p> </td> 
   <td colname="col3"> <p>Enumera los usuarios que son miembros del grupo. </p> <p> <b>Nombre:</b> El nombre del usuario tal como aparece en el campo Nombre común del certificado del usuario. </p> <p> <b>Prioridad adicional:</b> Proporciona prioridad adicional a la prioridad base del grupo de usuarios para determinar la prioridad de inicio de ese usuario. </p> </td> 
  </tr> 
 </tbody> 
</table>
