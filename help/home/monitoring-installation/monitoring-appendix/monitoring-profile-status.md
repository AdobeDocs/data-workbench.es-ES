---
description: Las siguientes dimensiones están disponibles para su uso en el perfil de estado de perfil del área de trabajo de datos.
solution: Analytics
title: Dimensiones en el perfil Estado del perfil del área de trabajo de datos
topic: Data workbench
uuid: bd84a3e5-d1ea-4768-9dac-62f5dfbad49a
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Dimensiones en el perfil Estado del perfil del área de trabajo de datos{#dimensions-in-the-data-workbench-profile-status-profile}

Las siguientes dimensiones están disponibles para su uso en el perfil de estado de perfil del área de trabajo de datos.

<table id="table_DD143B4F15FF446DAD24BD2473B485B9"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <b>Bloque</b> </td> 
   <td colname="col2"> Este es el único contador de esta configuración y existe como raíz para todas las dimensiones. Un bloque puede considerarse un servidor. Utiliza el campo x-trackingid. El ID de bloque es un hash del nombre del servidor más el nombre del host, por lo que habrá aproximadamente un bloque por servidor por perfil. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>A partir de minutos de retraso</b> </td> 
   <td colname="col2"> cs-uri-query(bi) se coloca en el campo x-as-of-delay-minutes y se redondea al minuto más cercano. En minutos de retraso es una dimensión numérica que toma la última fila de x-como-minutos-de-retraso para un bloque. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Entorno</b> </td> 
   <td colname="col2"> El valor cs-uri-query(c) se utiliza para el ID de entorno. La última fila de un bloque se utiliza como valor para la dimensión. Esta dimensión simple mostrará el entorno en el que se ejecutan los servidores (siempre que esté configurado correctamente). <p>Esto se puede establecer en el archivo insight_monitor_agent.cfg </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>MegaBytes de entrada rápida por minuto</b> </td> 
   <td colname="col2"> El valor cs-uri-query(bj) se utiliza para esta dimensión. La última fila de un bloque se utiliza como valor para la dimensión. Si el conjunto de datos está en Entrada rápida, el valor de la dimensión numérica mostrará el MB por minuto en el que el sistema está ingresando datos. <p>Nota:  Esta dimensión está oculta porque solo es útil cuando se promedia en una métrica. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>MegaBytes de combinación rápida por minuto</b> </td> 
   <td colname="col2">El valor cs-uri-query(bk) se utiliza para esta dimensión. La última fila de un bloque se utiliza como valor para la dimensión. Si el conjunto de datos está en Combinación rápida, el valor de esta dimensión numérica mostrará el MB por minuto en el que se está combinando el sistema. <p>Nota:  Esta dimensión está oculta porque solo es útil cuando se promedia en una métrica. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>GigaBytes de campo</b> </td> 
   <td colname="col2"> El valor cs-uri-query(bg) se utiliza para esta dimensión. El valor se divide por 1000 y se redondea al número entero más próximo. El valor de esta dimensión numérica mostrará la cantidad de espacio que utilizan los campos en el conjunto de datos. <p>Nota:  Esta dimensión está oculta porque solo es útil cuando se promedia en una métrica. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Host</b> </td> 
   <td colname="col2"> El valor cs-uri-query(b) se utiliza para esta dimensión. El valor de la dimensión Simple es la última fila de un bloque. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Último ping</b> </td> 
   <td colname="col2">x-last-ping es x-unixtime dividido por 10 (para dar cabida a restricciones de tamaño de dimensiones numéricas). El último ping es la última fila de un bloque determinado y representa la última vez que el agente de supervisión registró el estado del sistema. <p>Nota:  Esta dimensión está oculta porque solo es útil cuando se promedia en una métrica. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Porcentaje de lectura de registros</b> </td> 
   <td colname="col2">el valor cs-uri-query(be) se utiliza para esta dimensión numérica. Es la última fila de un bloque determinado. Esta dimensión se utiliza para calcular el porcentaje de registros leídos. <p>Nota:  Esta dimensión está oculta porque solo es útil cuando se promedia en una métrica. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>ID del modo de procesamiento</b> </td> 
   <td colname="col2"> El valor cs-uri-query(bb) se utiliza para esta dimensión simple. Es la última fila de un bloque determinado. La ID del modo de procesamiento permite ver en qué modo de procesamiento se encuentra el sistema (entrada rápida, combinación rápida, tiempo real). <p>Nota:  Esta dimensión se oculta y se vuelve a exponer con valores prácticos en el modo de procesamiento de dimensión del cliente. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Procesamiento detenido</b> </td> 
   <td colname="col2"> El campo x-processing-stalled se crea mediante varias condiciones para indicar si el perfil se está ejecutando o no. Es una dimensión simple. <p>Nota:  Esta dimensión funciona mejor cuando hay un gran número de registros de entrada para distribuirlos equitativamente entre las DPU. Si, por ejemplo, solo hay un archivo grande cargado por día, el área de trabajo de datos puede aparecer como "estancado" durante una hora o más, lo que resulta en una lectura falsa positiva de esta dimensión. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Perfil</b> </td> 
   <td colname="col2"> El valor cs-uri-query(ba) se utiliza para esta dimensión simple. Esta dimensión muestra los nombres de los perfiles que se supervisan actualmente. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Origen más atrás</b> </td> 
   <td colname="col2"> La última fila de cs-uri-query(bl) se copia en el campo x-source-furthest-hind. La dimensión simple utiliza la última fila para un bloque determinado. Esta dimensión muestra el momento en que se produjo el último contacto con un origen de datos. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Porcentaje de transformación</b> </td> 
   <td colname="col2"> el valor cs-uri-query(bf) se utiliza para esta dimensión numérica. Es la última fila de un bloque determinado. Esta dimensión se utiliza para calcular el porcentaje de transformación de datos completa. <p>Nota:  Esta dimensión está oculta porque solo es útil cuando se promedia en una métrica. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Dimensiones temporales</b> </td> 
   <td colname="col2"> La hora, el día, la semana, el mes, la hora del día y el día de la semana se derivan del campo x-timestamp. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Grupo</b> </td> 
   <td colname="col2"> Agrupación de palabras que le proporciona otra manera de filtrar el conjunto de datos resultante. Se establece en el archivo insight_monitor_agent.cfg. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Métricas</b> </td> 
   <td colname="col2"> A continuación se muestran las métricas incluidas en el perfil de supervisión de perfil del área de trabajo de datos y cómo se obtienen. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>A Los Minutos De Demora</b> </td> 
   <td colname="col2"> Esta métrica es la suma de los Minutos con retraso para cada bloque y luego dividida por la métrica Bloques. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Con retraso en segundos</b> </td> 
   <td colname="col2"> Esta métrica es la suma de los segundos de retraso con respecto a cada bloque y se divide por el número total de bloques. (Dimensión A partir de segundos de retraso no configurada de forma predeterminada) </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Bloques</b> </td> 
   <td colname="col2"> Suma una para cada bloque. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Entrada rápida MB por minuto</b> </td> 
   <td colname="col2"> La suma de MegaBytes de entrada rápida por minuto para cada bloque dividido por el número de bloques cuando MegaBytes por minuto de entrada rápida es buena a cero. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Combinación rápida MB por minuto</b> </td> 
   <td colname="col2"> La suma de megaBytes de combinación rápida por minuto para cada bloque dividido por el número de bloques cuando MegaBytes por minuto de combinación rápida es buena a cero. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>GigaBytes de campo</b> </td> 
   <td colname="col2"> La suma de los gigabytes de campo para cada bloque dividido por la métrica Bloques. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Última edad de ping</b> </td> 
   <td colname="col2"> El valor Con El Tiempo Menos La Última Hora De Ping. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Último tiempo de ping</b> </td> 
   <td colname="col2"> La suma de Última ping para cada bloque dividido por bloques, luego multiplicada por 10. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Lectura de registro</b> </td> 
   <td colname="col2"> Cuando el porcentaje de lectura de registros es bueno a cero, la lectura de registros es la suma del porcentaje de lectura de registros para cada bloque, dividido por la métrica Bloques, todo lo cual se divide por 10. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Procesamiento detenido</b> </td> 
   <td colname="col2"> La suma de la dimensión de procesamiento detenido para cada bloque, dividida por la métrica Bloques. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Transformación</b> </td> 
   <td colname="col2"> Suma del porcentaje de transformación para cada bloque dividido por la métrica Bloques, cuando el porcentaje de transformación es bueno a cero, todo dividido por 10. </td> 
  </tr> 
 </tbody> 
</table>

