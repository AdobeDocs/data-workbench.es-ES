---
description: Las siguientes dimensiones están disponibles para su uso en el perfil histórico del área de trabajo de datos.
solution: Analytics
title: Dimensiones en el perfil histórico del área de trabajo de datos
topic: Data workbench
uuid: 6d93fba4-986b-46a4-9479-aeb54853dff5
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Dimensiones en el perfil histórico del área de trabajo de datos{#dimensions-in-the-data-workbench-historic-profile}

Las siguientes dimensiones están disponibles para su uso en el perfil histórico del área de trabajo de datos.

## Dimensiones en el perfil histórico del área de trabajo de datos {#section-96f1b64f5cb84411b630f97f227d888d}

Las siguientes dimensiones están disponibles para su uso en el perfil histórico del área de trabajo de datos.

<table id="table_3EAEA68E73BE431D841F7F2E83EDD6AC"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <b>Bloque</b> </td> 
   <td colname="col2">Este es el único contador de esta configuración, es la raíz de todas las dimensiones. Un bloque puede considerarse un servidor. Utiliza el campo x-trackingid. <p>Nota:  El ID de bloque es un hash del nombre del servidor más el nombre del host, por lo que habrá aproximadamente un bloque por servidor por perfil. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Ping</b> </td> 
   <td colname="col2"> Se trata de una dimensión contable creada a partir del recuento de bloques. Cada fila de datos del perfil es un ping del agente de supervisión. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Alerta crítica</b> </td> 
   <td colname="col2"> Dimensión numérica creada a partir del valor cs-uri-query(ad). Está construido en el nivel Ping condicionado que cs-uri-query(a) coincide con "1". </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Alerta abajo</b> </td> 
   <td colname="col2"> Dimensión numérica creada a partir del valor cs-uri-query(ac). Se construye en el nivel Ping, condicionado a que cs-uri-query(a) coincida con "1". </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Advertencia de alerta</b> </td> 
   <td colname="col2"> Dimensión numérica creada a partir del valor cs-uri-query(ae). Está construido en el nivel Ping condicionado que cs-uri-query(a) coincide con "1". </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Cualquier reprocesamiento de perfil</b> </td> 
   <td colname="col2"> Dimensión numérica creada a partir del valor cs-uri-query(aa). Se genera en el nivel Ping condicionado que cs-uri-query(a) coincide con "1" y cs-uriquery(k) no está vacío. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>A partir de minutos de retraso</b> </td> 
   <td colname="col2"> cs-uri-query(bi) se coloca en el campo x-as-of-delay-minutes y se redondea al minuto más cercano. Está construido en el nivel Ping condicionado que cs-uri-query(a) coincide con "1". </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Porcentaje de fila de capacidad</b> </td> 
   <td colname="col2"> Dimensión numérica creada a partir del valor cs-uri-query(r). Se genera en el nivel Ping condicionado que cs-uri-query(a) coincide con "1" y cs-uriquery(k) no está vacío. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Porcentaje de tamaño de capacidad</b> </td> 
   <td colname="col2"> Dimensión numérica creada a partir del valor cs-uri-query(n). Se genera en el nivel Ping condicionado que cs-uri-query(a) coincide con "1" y cs-uriquery(k) no está vacío. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Éxito de comprobación de componentes</b> </td> 
   <td colname="col2"> Dimensión simple generada a partir del valor cs-uri-query(v). Se construye en el nivel Ping y se condiciona que cs-uri-query(a) coincide con "1". </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Componentes en error</b> </td> 
   <td colname="col2"> cs-uri-query(ao) se divide por el delimitador "|" y se copia en el campo x-components-in-error. Dimensión de varios a varios generada a partir del campo x-components-in-error. Construido a nivel Ping. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Segundos de comprobación detallados</b> </td> 
   <td colname="col2"> Dimensión numérica creada a partir del valor cs-uri-query(l). Se crea en el nivel Ping condicionado a que cs-uri-query(k) no esté vacío. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Éxito detallado de la comprobación</b> </td> 
   <td colname="col2"> Dimensión simple creada a partir del valor cs-uri-query(k). Está construido en el nivel Ping condicionado que cs-uri-query(a) coincide con "1". </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Bytes GigaBytes de dimensión</b> </td> 
   <td colname="col2"> cs-uri-query(bc) se copia en el campo x-dimension-gigabytes. El campo x-dimension-gigabytes es el usuario de esta dimensión simple, condicionado a que cs-uri-query(a) coincida con "2". </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Porcentaje de uso del disco "x"</b> </td> 
   <td colname="col2"> Estas dimensiones numéricas se configuran a partir de los valores cs-uri-query(ah, ai, aj, ak, al). Se crean en el nivel Ping y se condicionan en cs-uri-query(a) coincide con "1" y cs-uri-query(k) no está vacío. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Segundos de profundidad de barrido estimados</b> </td> 
   <td colname="col2"> El campo x-calculated-sweep-dekaseconds se utiliza en esta dimensión numérica. Este es el tiempo de barrido estimado de los servidores dividido por diez (resolución reducida de medición de barrido para que la dimensión tenga un tamaño más razonable). <p>Nota:  Esta dimensión está oculta porque solo es útil cuando se promedia en una métrica. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>MegaBytes de entrada rápida por minuto</b> </td> 
   <td colname="col2"> El valor cs-uri-query(bj) se utiliza para esta dimensión. La última fila de un bloque se utiliza como valor para la dimensión. Si el conjunto de datos está en Entrada rápida, el valor de la dimensión numérica mostrará el MB por minuto en el que el sistema está ingresando datos. <p>Nota:  Esta dimensión está oculta porque solo es útil cuando se promedia en una métrica. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>MegaBytes de combinación rápida por minuto</b> </td> 
   <td colname="col2">El valor cs-uri-query(bk) se utiliza para esta dimensión. La última fila de un bloque se utiliza como valor para la dimensión. Si el conjunto de datos está en Combinación rápida, el valor de esta dimensión numérica mostrará el MB por minuto en el que se está combinando el sistema. <p><p>Nota:  Esta dimensión está oculta porque solo es útil cuando se promedia en una métrica. </p></p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>GigaBytes de campo</b> </td> 
   <td colname="col2">El valor cs-uri-query(bg) se utiliza para esta dimensión. El valor se divide por 1000 y se redondea al número entero más próximo. El valor de esta dimensión numérica mostrará la cantidad de espacio que utilizan los campos en el conjunto de datos. <p>Nota:  Esta dimensión está oculta porque solo es útil cuando se promedia en una métrica. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Grupo</b> </td> 
   <td colname="col2"> Dimensión simple creada en el nivel Ping a partir del valor cs-uri-query(x). </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Host</b> </td> 
   <td colname="col2"> El valor cs-uri-query(b) se utiliza para esta dimensión. El valor de la dimensión Simple es la última fila de un bloque. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Último ping</b> </td> 
   <td colname="col2"> el campo x-unixtime se copia en x-last-ping y se divide por 10 para reducir la cardinalidad. La dimensión numérica se crea en el nivel de bloque y utiliza el campo x-last-ping. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Promedio de carga</b> </td> 
   <td colname="col2"> Se trata de una dimensión numérica que utiliza la última fila para el valor cs-uri-query(i) de un servidor determinado. Está condicionado a que cs-uri-query(k) no esté vacío. Esta dimensión se utiliza para calcular la carga media en los servidores del sistema que se está supervisando. <p><p>Nota:  Esta dimensión está oculta porque solo es útil cuando se promedia en una métrica. </p></p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Porcentaje de lectura de registros</b> </td> 
   <td colname="col2">el valor cs-uri-query(be) se utiliza para esta dimensión numérica, creada en el nivel Ping. Esta dimensión se utiliza para calcular el porcentaje de registros leídos. <p>Nota:  Esta dimensión está oculta porque solo es útil cuando se promedia en una métrica. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Porcentaje de archivos de la página de memoria</b> </td> 
   <td colname="col2"> Es una dimensión numérica que utiliza el valor cs-uri-query(o), creado en el nivel Ping. Está condicionado a que cs-uri-query(k) no esté vacío y cs-uri-query(a) que coincida con "1". Esta dimensión se utiliza para calcular el porcentaje de uso de memoria de archivos de página. <p>Nota:  Esta dimensión está oculta porque solo es útil cuando se promedia en una métrica. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Memoria MegaBytes físicos Total</b> </td> 
   <td colname="col2">Es una dimensión numérica que utiliza el valor cs-uri-query(ag), creado en el nivel Ping. Está condicionado a que cs-uri-query(k) no esté vacío y cs-uri-query(a) que coincida con "1. <p>Nota:  Esta dimensión está oculta porque solo es útil cuando se promedia en una métrica. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Porcentaje físico de memoria</b> </td> 
   <td colname="col2">Es una dimensión numérica que utiliza el valor cs-uri-query(ag), creado en el nivel Ping. Está condicionado a que cs-uri-query(k) no esté vacío y cs-uri-query(a) que coincida con "1. Esta dimensión se utiliza para calcular el porcentaje de uso de memoria física de cada servidor. <p>Nota:  Esta dimensión está oculta porque solo es útil cuando se promedia en una métrica. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Porcentaje de consulta de memoria</b> </td> 
   <td colname="col2"> Es una dimensión numérica que utiliza el valor cs-uri-query(s) en el nivel Ping. Está condicionado a que cs-uri-query(k) no esté vacío y cs-uri-query(a) que coincida con "1. Esta dimensión se utiliza para calcular el porcentaje de uso de memoria de consulta de cada servidor. <p>Nota:  Esta dimensión está oculta porque solo es útil cuando se promedia en una métrica. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Conexiones de red</b> </td> 
   <td colname="col2"> Es una dimensión numérica que utiliza el valor cs-uri-query(q) generado en el nivel Ping. Está condicionado a que cs-uri-query(k) no esté vacío y cs-uri-query(a) que coincida con "1. Se utiliza para mostrar el número de conexiones de red que hay para un servidor determinado. <p>Nota:  Esta dimensión está oculta porque solo es útil cuando se promedia en una métrica. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Filas de salida</b> </td> 
   <td colname="col2"> cs-uri-query(bh) se divide por 100000 y se copia en el campo x-output-rows para reducir el tamaño de la dimensión. X-output-rows se utiliza en una dimensión numérica creada en el nivel Ping, condicionada que cs-uri-query(a) coincide con "2". </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Id. de tipo de ping</b> </td> 
   <td colname="col2"> Dimensión simple creada con el valor cs-uri-query(a) en el nivel Ping. Esto muestra qué tipo de Ping se grabó. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Centisegundos de latencia de encuesta</b> </td> 
   <td colname="col2">El valor cs-uri-query(m) se divide por 10 para reducir el tamaño de dimensión y se copia en el campo x-poll-latency-centiseconds. Se trata de una dimensión numérica creada en el nivel Ping, condicionada por que cs-uri-query(k) no está vacía y cs-uri-query(a) coincide con "1"/ Esta dimensión se utiliza para calcular la latencia de la encuesta. <p>Nota:  Esta dimensión está oculta porque solo es útil cuando se promedia en una métrica. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>ID del modo de procesamiento</b> </td> 
   <td colname="col2"> El valor cs-uri-query(bb) se utiliza para esta dimensión simple, creada en el nivel Ping. Está condicionado que cs-uri-query(bb) no esté vacío y que cs-uri-query(a) coincida con "2" el ID del modo de procesamiento permite ver en qué modo de procesamiento se encuentra el sistema (Entrada rápida, Combinación rápida, Tiempo real). <p>Nota:  Esta dimensión se oculta y se vuelve a exponer con valores prácticos en el modo de procesamiento de dimensión del cliente. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Perfil</b> </td> 
   <td colname="col2"> El valor cs-uri-query(ba) se utiliza para esta dimensión simple, se genera en el nivel Ping. Esta dimensión muestra los nombres de los perfiles que se supervisan actualmente. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Segundos de comprobación rápida</b> </td> 
   <td colname="col2"> El valor cs-uri-query(h) se utiliza para esta dimensión numérica. Está construido en el nivel Ping condicionado que cs-uri-query(a) coincide con "1". </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Comprobación rápida correcta</b> </td> 
   <td colname="col2"> Es una dimensión simple creada a partir del valor cs-uri-query(g) generado en el nivel Ping. Se utiliza para calcular la métrica de comprobación rápida. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Porcentaje de procesamiento en tiempo real</b> </td> 
   <td colname="col2"> Dimensión numérica que utiliza el valor cs-uri-query(t) generado en el nivel Ping. Está condicionado que cs-uri-query(a) coincida con "1". </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Origen más atrás</b> </td> 
   <td colname="col2"> Dimensión simple creada a partir del valor cs-uri-query(bl) generado en el nivel Ping. Esta dimensión muestra el momento en que se produjo el último contacto con un origen de datos. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Porcentaje de espacio de base de datos temporal</b> </td> 
   <td colname="col2">Dimensión numérica creada con el valor cs-uri-query(an), creada en el nivel Ping. Está condicionado que cs-uri-query(k) no esté vacío y cs-uri-query(a) coincida con "1". Se utiliza para calcular el porcentaje de espacio de base de datos temporal utilizado en un servidor determinado. <p>Nota:  Esta dimensión está oculta porque solo es útil cuando se promedia en una métrica. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Porcentaje de transformación</b> </td> 
   <td colname="col2">el valor cs-uri-query(bf) se utiliza para esta dimensión numérica. Está construido a nivel Ping. Esta dimensión se utiliza para calcular el porcentaje de transformación de datos completa. <p><p>Nota:  Esta dimensión está oculta porque solo es útil cuando se promedia en una métrica. </p></p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Versión de Área de trabajo de datos</b> </td> 
   <td colname="col2"> El valor cs-uri-query(ab) se utiliza para esta dimensión simple. Se crea en el nivel Ping y se condiciona que cs-uri-query(ab) no está vacío y cs-uri-query(a) coincide con "1". Muestra las versiones del servidor del área de trabajo de datos que se ejecutan en cada servidor. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Versión de Área de trabajo de datos principal</b> </td> 
   <td colname="col2"> El valor cs-uri-query(ab) se divide y el valor de versión principal se copia en el campo x-insight-version-major. Es una dimensión simple creada en el nivel Ping y condicionada de que x-insight-version-major no está vacío y cs-uri-query(a) coincide con "1". </td> 
  </tr> 
 </tbody> 
</table>

<!-- <a id="section_76D8A4B07BB947558EBED1123EA203D5"></a> -->

