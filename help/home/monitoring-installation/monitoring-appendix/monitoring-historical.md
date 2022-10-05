---
description: Las siguientes dimensiones están disponibles para su uso en el perfil histórico de Data Workbench.
title: Dimensiones en el perfil histórico de Data Workbench
uuid: 6d93fba4-986b-46a4-9479-aeb54853dff5
exl-id: 9df1f317-a985-4132-b32e-f2263e0c23b2
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '1698'
ht-degree: 1%

---

# Dimensiones en el perfil histórico de Data Workbench{#dimensions-in-the-data-workbench-historic-profile}

{{eol}}

Las siguientes dimensiones están disponibles para su uso en el perfil histórico de Data Workbench.

## Dimensiones en el perfil histórico de Data Workbench {#section-96f1b64f5cb84411b630f97f227d888d}

Las siguientes dimensiones están disponibles para su uso en el perfil histórico de Data Workbench.

<table id="table_3EAEA68E73BE431D841F7F2E83EDD6AC"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <b>Bloque</b> </td> 
   <td colname="col2">Este es el único recuento de esta configuración, es la raíz de todas las dimensiones. Un bloque puede considerarse un servidor. Se utiliza el campo x-trackingid . <p>Nota: El ID de bloque es un hash del nombre de servidor más el nombre de host, por lo que habrá aproximadamente un bloque por servidor por perfil. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Ping</b> </td> 
   <td colname="col2"> Esta es una dimensión contable construida a partir del recuento de Bloques. Cada fila de datos del perfil es un ping del agente de supervisión. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Alerta crítica</b> </td> 
   <td colname="col2"> Dimension numérico creado a partir del valor cs-uri-query(ad) . Se crea en el nivel Ping condicionado a que cs-uri-query(a) coincida con "1". </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Alerta abajo</b> </td> 
   <td colname="col2"> Dimension numérico creado a partir del valor cs-uri-query(ac) . Se crea en el nivel Ping, con la condición de que cs-uri-query(a) coincida con "1". </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Advertencia</b> </td> 
   <td colname="col2"> Dimension numérico creado a partir del valor cs-uri-query(ae) . Se crea en el nivel Ping condicionado a que cs-uri-query(a) coincida con "1". </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Cualquier reprocesamiento de perfiles</b> </td> 
   <td colname="col2"> Dimension numérico creado a partir del valor cs-uri-query(aa) . Se crea en el nivel Ping condicionado que cs-uri-query(a) coincide con "1" y cs-uriquery(k) no está vacío. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>A partir de minutos de retraso</b> </td> 
   <td colname="col2"> cs-uri-query(bi) se coloca en el campo x-as-of-delay-minutes y se redondea al minuto más cercano. Se crea en el nivel Ping condicionado a que cs-uri-query(a) coincida con "1". </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Porcentaje de fila de capacidad</b> </td> 
   <td colname="col2"> Dimension numérico creado a partir del valor cs-uri-query(r) . Se crea en el nivel Ping condicionado que cs-uri-query(a) coincide con "1" y cs-uriquery(k) no está vacío. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Porcentaje de tamaño de capacidad</b> </td> 
   <td colname="col2"> Dimension numérico creado a partir del valor cs-uri-query(n) . Se crea en el nivel Ping condicionado que cs-uri-query(a) coincide con "1" y cs-uriquery(k) no está vacío. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Éxito en la comprobación de componentes</b> </td> 
   <td colname="col2"> Dimension simple creado a partir del valor cs-uri-query(v) . Se crea en el nivel Ping y se condiciona que cs-uri-query(a) coincida con "1". </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Componentes en error</b> </td> 
   <td colname="col2"> cs-uri-query(ao) se divide por el delimitador "|" y se copia en el campo x-components-in-error . Muchos a varios Dimension creados a partir del campo x-components-in-error . Construido en el nivel Ping. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Segundos de comprobación detallados</b> </td> 
   <td colname="col2"> Dimension numérico creado a partir del valor cs-uri-query(l) . Se crea en el nivel Ping condicionado que cs-uri-query(k) no esté vacío. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Éxito de comprobación detallada</b> </td> 
   <td colname="col2"> Dimension simple creado a partir del valor cs-uri-query(k) . Se crea en el nivel Ping condicionado a que cs-uri-query(a) coincida con "1". </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Dimension GigaBytes</b> </td> 
   <td colname="col2"> cs-uri-query(bc) se copia en el campo x-dimension-gigabytes . El campo x-dimension-gigabytes es el usuario para este Dimension simple, condicionado a cs-uri-query(a) que coincida con "2". </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Porcentaje de uso del disco "x"</b> </td> 
   <td colname="col2"> Estos Dimension numéricos están configurados a partir de los valores cs-uri-query(ah, ai, aj, ak, al). Se crean en el nivel Ping y se condicionan a que cs-uri-query(a) coincida con "1" y cs-uri-query(k) no esté vacío. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Segundos de barridos estimados</b> </td> 
   <td colname="col2"> El campo x-estimated-sweep-dekaseconds se utiliza en este Dimension numérico. Este es el tiempo de barrido estimado de los servidores dividido por diez (resolución reducida de medición de barrido para hacer que la dimensión tenga un tamaño más razonable). <p>Nota: Esta dimensión está oculta porque solo es útil cuando se promedia en una métrica. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>MegaBytes de entrada rápida por minuto</b> </td> 
   <td colname="col2"> El valor cs-uri-query(bj) se utiliza para esta dimensión. La última fila de un bloque se utiliza como valor de la dimensión. Si el conjunto de datos está en Entrada rápida, el valor de este Dimension numérico mostrará los MB por minuto a los que el sistema está ingresando datos. <p>Nota: Esta dimensión está oculta porque solo es útil cuando se promedia en una métrica. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>MegaBytes de fusión rápida por minuto</b> </td> 
   <td colname="col2">El valor cs-uri-query(bk) se utiliza para esta dimensión. La última fila de un bloque se utiliza como valor de la dimensión. Si el conjunto de datos está en Fusión rápida, el valor de este Dimension numérico mostrará los MB por minuto en los que se está fusionando el sistema. <p><p>Nota: Esta dimensión está oculta porque solo es útil cuando se promedia en una métrica. </p></p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Field GigaBytes</b> </td> 
   <td colname="col2">El valor cs-uri-query(bg) se utiliza para esta dimensión. El valor se divide entre 1000 y se redondea al número entero más cercano. El valor de este Dimension numérico mostrará la cantidad de espacio que están utilizando los campos en el conjunto de datos. <p>Nota: Esta dimensión está oculta porque solo es útil cuando se promedia en una métrica. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Grupo</b> </td> 
   <td colname="col2"> Dimension simple creado en el nivel Ping a partir del valor cs-uri-query(x) . </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Host</b> </td> 
   <td colname="col2"> El valor cs-uri-query(b) se utiliza para esta dimensión. El valor de la dimensión Simple es la última fila de un bloque. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Último ping</b> </td> 
   <td colname="col2"> el campo x-unixtime se copia en x-last-ping y se divide entre 10 para reducir la cardinalidad. El Dimension numérico se crea en el nivel de bloque y utiliza el campo x-last-ping . </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Media de carga</b> </td> 
   <td colname="col2"> Se trata de una dimensión numérica que utiliza la última fila para un valor cs-uri-query(i) de un servidor determinado. Está condicionado a que cs-uri-query(k) no esté vacío. Esta dimensión se utiliza para calcular la carga promedio en los servidores del sistema que se está monitorizando. <p><p>Nota: Esta dimensión está oculta porque solo es útil cuando se promedia en una métrica. </p></p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Porcentaje de lectura de registros</b> </td> 
   <td colname="col2">el valor cs-uri-query(be) se utiliza para esta dimensión numérica, creada en el nivel Ping. Esta dimensión se utiliza para calcular el porcentaje de registros que se están leyendo. <p>Nota: Esta dimensión está oculta porque solo es útil cuando se promedia en una métrica. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Porcentaje de archivos de la página de memoria</b> </td> 
   <td colname="col2"> Se trata de una dimensión numérica que utiliza el valor cs-uri-query(o) , creado en el nivel Ping. Está condicionado a que cs-uri-query(k) no esté vacío y cs-uri-query(a) que coincida con "1". Esta dimensión se utiliza para calcular el porcentaje de uso de memoria de archivos de página. <p>Nota: Esta dimensión está oculta porque solo es útil cuando se promedia en una métrica. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Memoria MegaBytes físicos en total</b> </td> 
   <td colname="col2">Se trata de una dimensión numérica que utiliza el valor cs-uri-query(ag) , creado en el nivel Ping. Está condicionado a que cs-uri-query(k) no esté vacío y cs-uri-query(a) que coincida con "1. <p>Nota: Esta dimensión está oculta porque solo es útil cuando se promedia en una métrica. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Porcentaje físico de memoria</b> </td> 
   <td colname="col2">Se trata de una dimensión numérica que utiliza el valor cs-uri-query(ag) , creado en el nivel Ping. Está condicionado a que cs-uri-query(k) no esté vacío y cs-uri-query(a) que coincida con "1. Esta dimensión se utiliza para calcular el porcentaje de uso de memoria física de cada servidor. <p>Nota: Esta dimensión está oculta porque solo es útil cuando se promedia en una métrica. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Porcentaje de consulta de memoria</b> </td> 
   <td colname="col2"> Se trata de una dimensión numérica que utiliza el valor cs-uri-query(s) en el nivel Ping. Está condicionado a que cs-uri-query(k) no esté vacío y cs-uri-query(a) que coincida con "1. Esta dimensión se utiliza para calcular el porcentaje de uso de memoria de consulta de cada Servidor. <p>Nota: Esta dimensión está oculta porque solo es útil cuando se promedia en una métrica. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Conexiones de red</b> </td> 
   <td colname="col2"> Se trata de una dimensión numérica que utiliza el valor cs-uri-query(q) creado en el nivel Ping. Está condicionado a que cs-uri-query(k) no esté vacío y cs-uri-query(a) que coincida con "1. Se utiliza para mostrar el número de conexiones de red que hay para un servidor determinado. <p>Nota: Esta dimensión está oculta porque solo es útil cuando se promedia en una métrica. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Filas de salida</b> </td> 
   <td colname="col2"> cs-uri-query(bh) se divide entre 100000 y se copia en el campo x-output-rows para reducir el tamaño de la dimensión. X-output-rows se utiliza en un Dimension numérico creado en el nivel Ping, condicionado a que cs-uri-query(a) coincida con "2". </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>ID de tipo de ping</b> </td> 
   <td colname="col2"> Dimension simple creado utilizando el valor cs-uri-query(a) en el nivel Ping. Esto muestra qué tipo de Ping se grabó. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Centisegundos de latencia de encuesta</b> </td> 
   <td colname="col2">El valor cs-uri-query(m) se divide entre 10 para reducir el tamaño de dimensión y se copia en el campo x-poll-latency-centiseconds . Se trata de una dimensión numérica creada en el nivel Ping, con el condición de que cs-uri-query(k) no esté vacía y cs-uri-query(a) coincida con "1"/ Esta dimensión se utiliza para calcular la latencia de la encuesta. <p>Nota: Esta dimensión está oculta porque solo es útil cuando se promedia en una métrica. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>ID del modo de procesamiento</b> </td> 
   <td colname="col2"> El valor cs-uri-query(bb) se utiliza para este Dimension simple, construido en el nivel Ping. Se ha condicionado que cs-uri-query(bb) no esté vacío y que cs-uri-query(a) coincida con el ID del modo de procesamiento "2" permite ver en qué modo de procesamiento se encuentra el sistema (Entrada rápida, Fusión rápida, Tiempo real). <p>Nota: Esta dimensión se oculta y se vuelve a exponer con valores prácticos en el modo de procesamiento de la dimensión del lado del cliente. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Perfil</b> </td> 
   <td colname="col2"> El valor cs-uri-query(ba) se utiliza para este Dimension simple, se crea en el nivel Ping. Esta dimensión muestra los nombres de los perfiles que se están monitorizando. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Comprobación rápida en segundos</b> </td> 
   <td colname="col2"> El valor cs-uri-query(h) se utiliza para este Dimension numérico. Se crea en el nivel Ping condicionado a que cs-uri-query(a) coincida con "1". </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Comprobación rápida correcta</b> </td> 
   <td colname="col2"> Se trata de una dimensión simple creada a partir del valor cs-uri-query(g) creado en el nivel Ping. Se utiliza para calcular la métrica de comprobación rápida. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Porcentaje de procesamiento en tiempo real</b> </td> 
   <td colname="col2"> Dimension numérico utilizando el valor cs-uri-query(t) creado en el nivel Ping. Se ha condicionado que cs-uri-query(a) coincida con "1". </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Fuente más detrás</b> </td> 
   <td colname="col2"> Dimension simple creado a partir del valor cs-uri-query(bl) construido en el nivel Ping. Esta dimensión muestra el momento en el que se produjo el último contacto con un origen de datos. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Porcentaje de espacio de base de datos temporal</b> </td> 
   <td colname="col2">Dimension numérico creado con el valor cs-uri-query(an) , construido en el nivel Ping. Se ha condicionado que cs-uri-query(k) no esté vacío y cs-uri-query(a) coincida con "1". Se utiliza para calcular el porcentaje de espacio de base de datos temporal utilizado en un servidor determinado. <p>Nota: Esta dimensión está oculta porque solo es útil cuando se promedia en una métrica. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Porcentaje de transformación</b> </td> 
   <td colname="col2">el valor cs-uri-query(bf) se utiliza para esta dimensión numérica. Está construido en el nivel Ping. Esta dimensión se utiliza para calcular el porcentaje de transformación de datos completa. <p><p>Nota: Esta dimensión está oculta porque solo es útil cuando se promedia en una métrica. </p></p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Versión de Data Workbench</b> </td> 
   <td colname="col2"> El valor cs-uri-query(ab) se utiliza para este Dimension simple. Se crea en el nivel Ping y se condiciona que cs-uri-query(ab) no esté vacío y cs-uri-query(a) coincide con "1". Se muestran las versiones del servidor de Data Workbench que se ejecutan en cada servidor. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Versión de Data Workbench mayor</b> </td> 
   <td colname="col2"> El valor cs-uri-query(ab) se divide y el valor de versión principal se copia en el campo x-insight-version-major . Es un Dimension simple creado en el nivel Ping y condicionado a que x-insight-version-major no esté vacío, y cs-uri-query(a) coincida con "1". </td> 
  </tr> 
 </tbody> 
</table>

<!-- <a id="section_76D8A4B07BB947558EBED1123EA203D5"></a> -->
