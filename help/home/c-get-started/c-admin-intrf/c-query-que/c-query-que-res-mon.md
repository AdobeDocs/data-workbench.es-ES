---
description: El vector del monitor de recursos contiene el Monitor de presupuesto de memoria y el Monitor de número de consultas.
solution: Analytics
title: Monitores de recursos de cola de consultas
topic: Data workbench
uuid: 6b516bed-7f9a-4821-869e-19e720f20313
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Monitores de recursos de cola de consultas{#query-queue-resource-monitors}

El vector del monitor de recursos contiene el Monitor de presupuesto de memoria y el Monitor de número de consultas.

En la tabla siguiente se describen los campos del monitor de recursos que se utilizan en la cola de consultas.

<table id="table_9991EED2647A460FACA2DC80D4973A8E"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Campo </th> 
   <th colname="col2" class="entry"> Tipo </th> 
   <th colname="col3" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Monitor de presupuesto de memoria </p> </td> 
   <td colname="col2"> </td> 
   <td colname="col3"> <p>Supervisa la memoria de consulta utilizada por el grupo de usuarios actual. Si el uso actual está entre el umbral bajo y el umbral alto, no se programan nuevos paquetes hasta que el uso de memoria vuelva a estar por debajo del valor de umbral bajo, por ejemplo, como resultado del cierre de los espacios de trabajo por parte de los usuarios. Los paquetes programados pueden crecer. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Umbral alto </p> </td> 
   <td colname="col2"> <p>double </p> </td> 
   <td colname="col3"> <p>El umbral máximo para el uso de memoria (bytes). Si el uso de memoria es superior a este valor, no se produce ninguna programación y los paquetes programados con prioridad más baja no se programan de uno en uno, durante un período de tiempo, hasta que el uso de memoria se sitúa por debajo de este valor. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Umbral bajo </p> </td> 
   <td colname="col2"> <p>double </p> </td> 
   <td colname="col3"> <p>El umbral bajo para el uso de memoria (bytes). Si <span class="wintitle"> el valor del Monitor</span> de presupuesto de memoria está por debajo de este valor, se permite programar nuevos paquetes y aumentar los paquetes programados. Por ejemplo, los paquetes crecen cuando un usuario agrega una visualización a un espacio de trabajo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Tiempo de reacción </p> </td> 
   <td colname="col2"> <p>double </p> </td> 
   <td colname="col3"> <p>Constante de tiempo para suavizar la estimación de uso de memoria. Los valores de afinación evitan la reacción a los picos de uso. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Número del monitor de consultas </p> </td> 
   <td colname="col2"> </td> 
   <td colname="col3"> <p>Supervisa el número total de consultas programadas actualmente para el perfil. Este monitor de recursos permite programar paquetes si el número total de consultas permanece por debajo del valor en el campo Umbral bajo. Este monitor permite que los paquetes programados actualmente aumenten si el número total de consultas permanece por debajo del valor en el campo Umbral alto. Además, este monitor elimina los paquetes de prioridad baja para permitir que los paquetes de prioridad alta se programen o crezcan. Sin embargo, esta configuración no impide los paquetes con una prioridad buena que la especificada en el campo Prioridad intocable. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Umbral alto </p> </td> 
   <td colname="col2"> </td> 
   <td colname="col3"> <p>El umbral máximo para el uso de memoria (bytes). Si el uso de memoria es superior a este valor, no se produce ninguna programación y los paquetes programados de prioridad más baja no se programan de uno en uno, durante un período de tiempo, hasta que el uso de memoria se sitúa por debajo de este valor. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Umbral bajo </p> </td> 
   <td colname="col2"> </td> 
   <td colname="col3"> <p>El umbral bajo para el uso de memoria (bytes). Si <span class="wintitle"> el valor del Monitor</span> de presupuesto de memoria está por debajo de este valor, se pueden programar nuevos paquetes y los paquetes programados pueden aumentar. </p> </td> 
  </tr> 
 </tbody> 
</table>

