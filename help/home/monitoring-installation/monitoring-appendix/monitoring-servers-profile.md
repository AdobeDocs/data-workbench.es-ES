---
description: Las siguientes dimensiones están disponibles para su uso en el perfil de estado del servidor de Data Workbench.
title: Dimensiones en el perfil de estado del servidor de Data Workbench
uuid: 4cfe882a-2797-4af9-bd6d-75bc31ee909c
exl-id: 002f6b95-f151-41d9-ae28-9c01c1f621ee
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '1366'
ht-degree: 1%

---

# Dimensiones en el perfil de estado del servidor de Data Workbench{#dimensions-in-the-data-workbench-server-status-profile}

{{eol}}

Las siguientes dimensiones están disponibles para su uso en el perfil de estado del servidor de Data Workbench.

<table id="table_10DFAD7A0C5946B0A2458F6C08D04FC5"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <b>Servidor</b> </td> 
   <td colname="col2"> Creada a partir del campo x-trackingid , esta dimensión contable representa los Servidores que ejecutan actualmente Data Workbench. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Versión del agente</b> </td> 
   <td colname="col2"> El valor cs-uri-query(af) se utiliza para este Dimension simple. Es el último valor no vacío de un servidor. Esto muestra la fecha y hora de compilación de las versiones del agente de supervisión que se está ejecutando. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Cualquier reprocesamiento de perfiles</b> </td> 
   <td colname="col2"> El campo cs-uri-query(aa) se utiliza para este Dimension numérico, es el valor de la última fila para un servidor determinado, condicional a cs-uri-query(k) no está vacío. Esta dimensión se utiliza para indicar si algún perfil está reprocesando. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Porcentaje de fila de capacidad</b> </td> 
   <td colname="col2"> El campo cs-uri-query(r) se utiliza para este Dimension numérico, es el valor de la última fila para un servidor determinado, condicional a cs-uri-query(k) no está vacío. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Porcentaje de tamaño de capacidad</b> </td> 
   <td colname="col2"> El campo cs-uri-query(n) se utiliza para este Dimension numérico, es el valor de la última fila para un servidor determinado, condicional a cs-uri-query(k) no está vacío. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Nombre común</b> </td> 
   <td colname="col2"> El campo sc-ur-query(am) se utiliza para este Dimension simple, es el valor del valor Último no en blanco para un servidor determinado. Muestra el Nombre común de los servidores que se supervisan. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Éxito en la comprobación de componentes</b> </td> 
   <td colname="col2"> El campo cs-uri-query(v) se utiliza para este Dimension simple, es el valor de la última fila para un servidor determinado. Esta dimensión comprueba los componentes del servidor para verificar que funcionan correctamente. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Componentes en error</b> </td> 
   <td colname="col2"> Una transformación Crossrows toma el valor Última fila del cs-uri-query(ao) y la copia en el campo x-components-in-error . Esta dimensión Muchos a varios muestra cualquier componente por error en los servidores que se supervisan. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Entorno</b> </td> 
   <td colname="col2">El valor cs-uri-query(c) se utiliza para el ID de entorno. La última fila de un bloque se utiliza como valor de la dimensión. Este Dimension simple mostrará el Entorno en el que se ejecutan los servidores (siempre que esté configurado correctamente). <p><p>Nota: Esta dimensión se establece en insight_monitor_agent.cfg. </p></p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Segundos de barridos estimados</b> </td> 
   <td colname="col2"> El campo x-estimated-sweep-dekaseconds se utiliza en este Dimension numérico. Este es el tiempo de barrido estimado de los servidores dividido por diez (resolución reducida de medición de barrido para hacer que la dimensión tenga un tamaño más razonable). <p><p>Nota: Esta dimensión está oculta porque solo es útil cuando se promedia en una métrica. </p></p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Host</b> </td> 
   <td colname="col2"> El valor cs-uri-query(b) se utiliza para esta dimensión. El valor de la dimensión Simple es la última fila de un bloque. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Último ping</b> </td> 
   <td colname="col2"> x-last-ping es x-unixtime dividido por 10 (para admitir restricciones de tamaño de dimensiones numéricas). Último ping es la última fila de un bloque determinado y representa la última vez que el agente de supervisión registró el estado del sistema. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Media de carga</b> </td> 
   <td colname="col2"> Se trata de una dimensión numérica que utiliza la última fila para un valor cs-uri-query(i) de un servidor determinado. Está condicionado a que cs-uri-query(k) no esté vacío. Esta dimensión se utiliza para calcular la carga promedio en los servidores del sistema que se está monitorizando. <p>Nota: Esta dimensión está oculta porque solo es útil cuando se promedia en una métrica. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Porcentaje de archivos de la página de memoria</b> </td> 
   <td colname="col2"> Se trata de una dimensión numérica que utiliza la última fila para un valor cs-uri-query(o) de un servidor determinado. Está condicionado a que cs-uri-query(k) no esté vacío. Esta dimensión se utiliza para calcular el porcentaje de uso de memoria de archivos de página. <p>Nota: Esta dimensión está oculta porque solo es útil cuando se promedia en una métrica. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Memoria MegaBytes físicos en total</b> </td> 
   <td colname="col2"> Se trata de una dimensión numérica que utiliza la última fila para un valor cs-uri-query(ag) de un servidor determinado. Está condicionado a que cs-uri-query(k) no esté vacío. <p>Nota: Esta dimensión está oculta porque solo es útil cuando se promedia en una métrica. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Porcentaje físico de memoria</b> </td> 
   <td colname="col2"> Se trata de una dimensión numérica que utiliza la última fila para un valor cs-uri-query(ag) de un servidor determinado. Está condicionado a que cs-uri-query(k) no esté vacío. Esta dimensión se utiliza para calcular el porcentaje de uso de memoria física de cada servidor. <p>Nota: Esta dimensión está oculta porque solo es útil cuando se promedia en una métrica. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Porcentaje de consulta de memoria</b> </td> 
   <td colname="col2"> Se trata de una dimensión numérica que utiliza la última fila para un valor cs-uri-query(s) de un servidor determinado. Está condicionado a que cs-uri-query(k) no esté vacío. Esta dimensión se utiliza para calcular el porcentaje de uso de memoria de consulta de cada Servidor. <p>Nota: Esta dimensión está oculta porque solo es útil cuando se promedia en una métrica. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Conexiones de red</b> </td> 
   <td colname="col2"> Se trata de una dimensión numérica que utiliza la última fila para un valor cs-uri-query(q) de un servidor determinado. Está condicionado a que cs-uri-query(k) no esté vacío. Se utiliza para mostrar el número de conexiones de red que hay para un servidor determinado. <p>Nota: Esta dimensión está oculta porque solo es útil cuando se promedia en una métrica. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Centisegundos de latencia de encuesta</b> </td> 
   <td colname="col2"> Esta dimensión se utiliza para calcular la latencia de la encuesta. El valor cs-uri-query(m) se divide entre 10 para reducir el tamaño de dimensión y se copia en el campo x-poll-latency-centiseconds . Se trata de una dimensión numérica que toma la última fila para un servidor determinado. <p>Nota: Esta dimensión está oculta porque solo es útil cuando se promedia en una métrica. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Comprobación rápida correcta</b> </td> 
   <td colname="col2"> Se trata de una dimensión simple creada a partir del valor cs-uri-query(g) de la última fila para un servidor determinado. Se utiliza para calcular la métrica de comprobación rápida. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Porcentaje de espacio de base de datos temporal</b> </td> 
   <td colname="col2"> La última fila del valor cs-uri-query(an) se copia en el campo x-temp-db-space-percentage . Se trata de un Dimension numérico que se utiliza para calcular el porcentaje de espacio de base de datos temporal utilizado en un servidor determinado. <p>Nota: Esta dimensión está oculta porque solo es útil cuando se promedia en una métrica. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Versión de Insight</b> </td> 
   <td colname="col2"> El valor cs-uri-query(ab) se utiliza para este Dimension simple. Es el último valor no vacío de un servidor. Se muestran las versiones del servidor de Data Workbench que se ejecutan en cada servidor. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Grupo</b> </td> 
   <td colname="col2"> Palabra de agrupamiento que le ofrece otra forma de filtrar el conjunto de datos resultante. <p>Nota: Esta dimensión se establece en insight_monitor_agent.cfg. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Métricas</b> </td> 
   <td colname="col2"> A continuación se enumeran las métricas incluidas en el perfil de supervisión de perfiles de Data Workbench y cómo se derivan. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Capacidad general</b> </td> 
   <td colname="col2"> Esta es la métrica Tamaño de capacidad por dos veces más la métrica Fila de capacidad dividida por 3. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Fila de capacidad</b> </td> 
   <td colname="col2"> Esta es la suma del porcentaje de fila de capacidad para cada servidor dividido por la métrica Servidores . </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Tamaño de la capacidad</b> </td> 
   <td colname="col2"> Esta es la suma del porcentaje de tamaño de capacidad de cada servidor dividido por la métrica Servidores. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Comprobación de componentes</b> </td> 
   <td colname="col2"> Este es el número de servidores donde el éxito de comprobación de componentes es igual a uno, dividido por el servidor donde el servicio es DPU o FSU, todos multiplicados por 100 (para convertirlo en un porcentaje). </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Disco "x"</b> </td> 
   <td colname="col2"> Las métricas de disco se calculan tomando la suma de su Porcentaje de disco usado para cada servidor, dividido por la métrica Servidores. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Minutos de barrido estimados</b> </td> 
   <td colname="col2"> Esta es la suma de los segundos de barridos estimados para cada servidor, divididos por la métrica Servidores donde los segundos de barrido estimados son buenos a cero, todos divididos por 6. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Última hora de ping</b> </td> 
   <td colname="col2"> La suma de Último ping para cada bloque dividido por bloques y luego multiplicado por 10. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Carga</b> </td> 
   <td colname="col2"> Esta es la suma del promedio de carga de cada servidor, dividido por la métrica Servidores . </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Archivo de página de memoria</b> </td> 
   <td colname="col2"> Es la suma del porcentaje de archivo de página de memoria para cada servidor, dividido por la métrica Servidores. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Memoria física</b> </td> 
   <td colname="col2"> Esta es la suma del porcentaje físico de memoria para cada servidor, dividido por la métrica Servidores . </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Consulta de memoria</b> </td> 
   <td colname="col2"> Es la suma del porcentaje de consulta de memoria para cada servidor, dividido por la métrica Servidores. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Conexiones de red</b> </td> 
   <td colname="col2"> Esta es la suma de Conexiones de red para cada servidor dividido por la métrica Servidores . </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Milisegundos de latencia de encuesta</b> </td> 
   <td colname="col2"> Esta es la suma de los centísegundos de latencia de encuesta para cada servidor, dividida por la métrica Servidores, que se multiplica por 10. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Comprobación rápida</b> </td> 
   <td colname="col2"> Este es el número de servidores en los que el éxito de la comprobación rápida es igual a uno, dividido por la métrica Servidores, todo lo cual se multiplica por 100. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Servidores</b> </td> 
   <td colname="col2"> Es la suma de uno para cada servidor o el número total de servidores monitoreados. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Base de datos temporal</b> </td> 
   <td colname="col2"> Esta es la suma del porcentaje de espacio de base de datos temporal para cada servidor, dividido por la métrica Servidores. </td> 
  </tr> 
 </tbody> 
</table>
