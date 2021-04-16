---
description: El vector del monitor de recursos contiene el Monitor de presupuesto de memoria y el Monitor de número de consultas.
title: Monitores de recursos de cola de Consulta
uuid: 6b516bed-7f9a-4821-869e-19e720f20313
exl-id: 6d445a4d-a415-41ce-9d45-1bdd0e726edd
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '399'
ht-degree: 2%

---

# Monitores de recursos de cola de Consulta{#query-queue-resource-monitors}

El vector del monitor de recursos contiene el Monitor de presupuesto de memoria y el Monitor de número de consultas.

En la tabla siguiente se describen los campos del monitor de recursos utilizados para la consulta en cola.

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
   <td colname="col3"> <p>Supervisa la memoria de consulta utilizada por el grupo de usuarios actual. Si el uso actual está entre el umbral bajo y el alto, no se programan nuevos paquetes hasta que el uso de memoria vuelva a estar por debajo del valor de umbral bajo, por ejemplo, como resultado de que los usuarios cerraran sus espacios de trabajo. Los paquetes programados pueden crecer. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Umbral alto </p> </td> 
   <td colname="col2"> <p>double </p> </td> 
   <td colname="col3"> <p>El umbral alto para el uso de la memoria (bytes). Si el uso de la memoria está por encima de este valor, no se produce ninguna programación y los paquetes programados con prioridad más baja no están programados de a uno, durante un período de tiempo, hasta que el uso de la memoria se sitúe por debajo de este valor. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Umbral bajo </p> </td> 
   <td colname="col2"> <p>double </p> </td> 
   <td colname="col3"> <p>El umbral bajo para uso de memoria (bytes). Si el valor <span class="wintitle"> Monitor de presupuesto de memoria</span> está por debajo de este valor, se permite programar nuevos paquetes y aumentar los paquetes programados. Por ejemplo, los paquetes aumentan cuando un usuario agrega una visualización a un espacio de trabajo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Tiempo de reacción </p> </td> 
   <td colname="col2"> <p>double </p> </td> 
   <td colname="col3"> <p>Constante de tiempo para suavizar la estimación del uso de memoria. Los valores de suavizado evitan la reacción a los picos de uso. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Supervisión de número de consultas </p> </td> 
   <td colname="col2"> </td> 
   <td colname="col3"> <p>Supervisa el número total de consultas que están programadas actualmente para el perfil. Este monitor de recursos le permite programar paquetes si el número total de consultas permanece por debajo del valor del campo Umbral bajo . Este monitor permite que los paquetes programados actualmente aumenten si el número total de consultas se mantiene por debajo del valor del campo Alto umbral . Además, este monitor elimina los paquetes de prioridad baja para permitir que los paquetes de prioridad más alta se programen o crezcan. Sin embargo, esta configuración no es preferible a los paquetes con una prioridad buena que la especificada en el campo Prioridad intocable . </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Umbral alto </p> </td> 
   <td colname="col2"> </td> 
   <td colname="col3"> <p>El umbral alto para el uso de la memoria (bytes). Si el uso de la memoria está por encima de este valor, no se produce ninguna programación y los paquetes programados de prioridad más baja no están programados de a uno, durante un período de tiempo, hasta que el uso de la memoria llegue a estar por debajo de este valor. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Umbral bajo </p> </td> 
   <td colname="col2"> </td> 
   <td colname="col3"> <p>El umbral bajo para uso de memoria (bytes). Si el valor <span class="wintitle"> Monitor de presupuesto de memoria</span> está por debajo de este valor, se pueden programar nuevos paquetes y los paquetes programados pueden crecer. </p> </td> 
  </tr> 
 </tbody> 
</table>
