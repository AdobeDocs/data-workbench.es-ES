---
description: Las siguientes dimensiones están disponibles para su uso en el perfil de estado del perfil de Data Workbench.
title: Dimensiones en el perfil de estado del perfil de Data Workbench
uuid: bd84a3e5-d1ea-4768-9dac-62f5dfbad49a
exl-id: 57b3ff16-26db-4292-819b-f6cd8e024c2a
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '1047'
ht-degree: 2%

---

# Dimensiones en el perfil de estado del perfil de Data Workbench{#dimensions-in-the-data-workbench-profile-status-profile}

Las siguientes dimensiones están disponibles para su uso en el perfil de estado del perfil de Data Workbench.

<table id="table_DD143B4F15FF446DAD24BD2473B485B9"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <b>Bloque</b> </td> 
   <td colname="col2"> Este es el único recuento de esta configuración y existe como raíz para todas las dimensiones. Un bloque puede considerarse un servidor. Se utiliza el campo x-trackingid . El ID de bloque es un hash del nombre de servidor más el nombre de host, por lo que habrá aproximadamente un bloque por servidor por perfil. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>A partir de minutos de retraso</b> </td> 
   <td colname="col2"> cs-uri-query(bi) se coloca en el campo x-as-of-delay-minutes y se redondea al minuto más cercano. En minutos de retraso es una dimensión numérica que toma la última fila de x-como minutos de retraso para un bloque. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Entorno</b> </td> 
   <td colname="col2"> El valor cs-uri-query(c) se utiliza para el ID de entorno. La última fila de un bloque se utiliza como valor de la dimensión. Este Dimension simple mostrará el Entorno en el que se ejecutan los servidores (siempre que esté configurado correctamente). <p>Esto se puede establecer en el archivo insight_monitor_agent.cfg </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>MegaBytes de entrada rápida por minuto</b> </td> 
   <td colname="col2"> El valor cs-uri-query(bj) se utiliza para esta dimensión. La última fila de un bloque se utiliza como valor de la dimensión. Si el conjunto de datos está en Entrada rápida, el valor de este Dimension numérico mostrará los MB por minuto a los que el sistema está ingresando datos. <p>Nota:  Esta dimensión está oculta porque solo es útil cuando se promedia en una métrica. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>MegaBytes de fusión rápida por minuto</b> </td> 
   <td colname="col2">El valor cs-uri-query(bk) se utiliza para esta dimensión. La última fila de un bloque se utiliza como valor de la dimensión. Si el conjunto de datos está en Fusión rápida, el valor de este Dimension numérico mostrará los MB por minuto en los que se está fusionando el sistema. <p>Nota:  Esta dimensión está oculta porque solo es útil cuando se promedia en una métrica. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Field GigaBytes</b> </td> 
   <td colname="col2"> El valor cs-uri-query(bg) se utiliza para esta dimensión. El valor se divide entre 1000 y se redondea al número entero más cercano. El valor de este Dimension numérico mostrará la cantidad de espacio que están utilizando los campos en el conjunto de datos. <p>Nota:  Esta dimensión está oculta porque solo es útil cuando se promedia en una métrica. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Host</b> </td> 
   <td colname="col2"> El valor cs-uri-query(b) se utiliza para esta dimensión. El valor de la dimensión Simple es la última fila de un bloque. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Último ping</b> </td> 
   <td colname="col2">x-last-ping es x-unixtime dividido por 10 (para admitir restricciones de tamaño de dimensiones numéricas). Último ping es la última fila de un bloque determinado y representa la última vez que el agente de supervisión registró el estado del sistema. <p>Nota:  Esta dimensión está oculta porque solo es útil cuando se promedia en una métrica. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Porcentaje de lectura de registros</b> </td> 
   <td colname="col2">el valor cs-uri-query(be) se utiliza para esta dimensión numérica. Es la última fila de un bloque determinado. Esta dimensión se utiliza para calcular el porcentaje de registros que se están leyendo. <p>Nota:  Esta dimensión está oculta porque solo es útil cuando se promedia en una métrica. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>ID del modo de procesamiento</b> </td> 
   <td colname="col2"> El valor cs-uri-query(bb) se utiliza para este Dimension simple. Es la última fila de un bloque determinado. El ID del modo de procesamiento permite ver en qué modo de procesamiento se encuentra el sistema (Entrada rápida, Fusión rápida, Tiempo real). <p>Nota:  Esta dimensión se oculta y se vuelve a exponer con valores prácticos en el modo de procesamiento de la dimensión del lado del cliente. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Procesamiento demorado</b> </td> 
   <td colname="col2"> El campo x-processing-stalled se crea mediante varias condiciones para indicar si el perfil se está ejecutando o no. Es una dimensión simple. <p>Nota:  Esta dimensión funciona mejor cuando hay un gran número de registros de entrada para distribuirlos equitativamente entre las DPU. Si hay, por ejemplo, un solo archivo grande cargado por día, Data Workbench puede parecer que está "paralizado" durante una hora o más, lo que resulta en una lectura de falso positivo de esta dimensión. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Perfil</b> </td> 
   <td colname="col2"> El valor cs-uri-query(ba) se utiliza para este Dimension simple. Esta dimensión muestra los nombres de los perfiles que se supervisan actualmente. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Fuente más detrás</b> </td> 
   <td colname="col2"> La última fila de cs-uri-query(bl) se copia en el campo x-source-far-back. El Dimension simple utiliza la última fila para un bloque determinado. Esta dimensión muestra el momento en el que se produjo el último contacto con un origen de datos. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Porcentaje de transformación</b> </td> 
   <td colname="col2"> el valor cs-uri-query(bf) se utiliza para esta dimensión numérica. Es la última fila de un bloque determinado. Esta dimensión se utiliza para calcular el porcentaje de transformación de datos completa. <p>Nota:  Esta dimensión está oculta porque solo es útil cuando se promedia en una métrica. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Dimensiones temporales</b> </td> 
   <td colname="col2"> La hora, el día, la semana, el mes, la hora del día y el día de la semana se derivan del campo x-timestamp . </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Grupo</b> </td> 
   <td colname="col2"> Palabra de agrupamiento que le ofrece otra forma de filtrar el conjunto de datos resultante. Se establece en el archivo insight_monitor_agent.cfg. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Métricas</b> </td> 
   <td colname="col2"> A continuación se enumeran las métricas incluidas en el perfil de supervisión de perfiles de Data Workbench y cómo se derivan. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Con retraso en minutos</b> </td> 
   <td colname="col2"> Esta métrica es la suma de los minutos con fecha de retraso para cada bloque y luego dividida por la métrica Bloques. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Con retraso en segundos</b> </td> 
   <td colname="col2"> Esta métrica es la suma del valor Con fecha de retraso en segundos para cada bloque y dividido por el número total de bloques. (Con retraso en segundos, el Dimension no está configurado de forma predeterminada) </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Bloques</b> </td> 
   <td colname="col2"> Sume uno para cada bloque. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Entrada rápida MB por minuto</b> </td> 
   <td colname="col2"> La suma de MegaBytes de Entrada Rápida por Minuto para cada Bloque dividido por el número de Bloques cuando MegaBytes de Entrada Rápida por Minuto es buena a cero. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Fusión rápida MB por minuto</b> </td> 
   <td colname="col2"> La suma de MegaBytes de Fusión Rápida por Minuto para cada Bloque dividido por el número de Bloques cuando MegaBytes de Fusión Rápida por Minuto es buena a cero. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Field GigaBytes</b> </td> 
   <td colname="col2"> La suma de Gigabytes de campo para cada Bloque dividido por la métrica Bloques. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Última edad de ping</b> </td> 
   <td colname="col2"> El Con respecto al tiempo menos el último ping. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Última hora de ping</b> </td> 
   <td colname="col2"> La suma de Último ping para cada bloque dividido por bloques y luego multiplicado por 10. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Lectura de registros</b> </td> 
   <td colname="col2"> Cuando el porcentaje de lectura de registros es bueno a cero, la lectura de registros es la suma del porcentaje de lectura de registros para cada bloque, dividido por la métrica Bloques, todos los cuales están divididos por 10. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Procesamiento demorado</b> </td> 
   <td colname="col2"> La suma del Dimension Procesamiento demorado para cada bloque, dividido por la métrica Bloques. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Transformación</b> </td> 
   <td colname="col2"> La suma de porcentaje de transformación para cada bloque dividido por la métrica Bloques, cuando el porcentaje de transformación es bueno a cero, todos divididos por 10. </td> 
  </tr> 
 </tbody> 
</table>
