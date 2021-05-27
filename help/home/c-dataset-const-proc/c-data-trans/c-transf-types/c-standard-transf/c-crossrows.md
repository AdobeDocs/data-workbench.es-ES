---
description: Al igual que otras transformaciones, la transformación CrossRows se aplica a las filas de datos (entradas de registro) de los orígenes de registro.
title: CrossRows
uuid: 5910c150-6bec-4d98-b116-9b382fd54d3c
exl-id: 321f986e-44a9-454c-9311-0ae37a11a088
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '1137'
ht-degree: 1%

---

# CrossRows{#crossrows}

Al igual que otras transformaciones, la transformación CrossRows se aplica a las filas de datos (entradas de registro) de los orígenes de registro.

Para cada fila de datos, la transformación toma el valor del campo de entrada especificado, realiza un conjunto de pasos de procesamiento y registra el resultado en el campo de salida especificado. Sin embargo, cuando la transformación [!DNL CrossRows] funciona en una fila de datos (esta fila se denomina fila de salida), tiene en cuenta esa fila más una o más filas de datos (estas filas se denominan filas de entrada) que están asociadas con el mismo ID de seguimiento. Por lo tanto, para un ID de seguimiento determinado, el valor del campo de salida para cada fila de salida se basa en los valores del campo de entrada para una o más filas de entrada.

La transformación proporciona varias condiciones y restricciones que permiten limitar las filas de entrada para la transformación. Puede expresar estos límites en términos de las condiciones del servidor de Data Workbench (consulte [Conditions](../../../../../home/c-dataset-const-proc/c-conditions/c-abt-cond.md)), un rango de filas de entrada relativas a la fila de salida o un intervalo de veces relativo al tiempo de la fila de salida. Para las filas de entrada que cumplan las condiciones y restricciones de la transformación, puede aplicar una operación (como SUM) que determine el valor del campo de salida.

>[!NOTE]
>
>Para que funcione, la transformación [!DNL CrossRows] requiere que los datos se ordenen a tiempo y se agrupen por el ID de seguimiento en los datos de origen. Por lo tanto, [!DNL CrossRows] solo funciona cuando se define en el archivo [!DNL Transformation.cfg] o en un archivo [!DNL Transformation Dataset Include].

Al revisar las descripciones de los parámetros en la siguiente tabla, recuerde lo siguiente:

* La fila de salida es la fila de datos en la que está trabajando la transformación en un momento dado.
* Las filas de entrada son todas las demás filas de datos (antes, después o incluyendo la fila de salida) cuyos valores del campo de entrada sirven como entradas para la transformación. Las filas de entrada están sujetas a los parámetros Condición de entrada, Clave, Inicio de fila, Fin de fila, Inicio de tiempo y Fin de tiempo.

<table id="table_152851484AFF4C50AF736DC62FAA43E3"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parámetro </th> 
   <th colname="col2" class="entry"> Descripción </th> 
   <th colname="col3" class="entry"> Predeterminado </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Nombre </td> 
   <td colname="col2"> Nombre descriptivo de la transformación. Puede introducir cualquier nombre aquí. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Comentarios </td> 
   <td colname="col2"> Opcional. Notas sobre la transformación. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Condición </td> 
   <td colname="col2"> Limita el resultado de la transformación a ciertas entradas de registro. Si no se cumple la condición para una entrada de registro determinada, el campo en el parámetro Output se deja sin cambios. La entrada puede utilizarse para afectar a otras entradas de registro. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Entrada </td> 
   <td colname="col2"> Nombre del campo de la fila de entrada que se va a utilizar como entrada. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Condición de entrada </td> 
   <td colname="col2"> Acepta la entrada para la transformación desde solo ciertas filas de entrada. Si no se cumple la condición de entrada para una fila de entrada determinada, se ignora el campo de entrada de esa fila y no afecta a otras filas de salida. Sin embargo, el campo de salida de esa fila se sigue modificando según la condición especificada. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Clave </td> 
   <td colname="col2"> <p>Opcional. Nombre del campo que se va a utilizar como clave. </p> <p> Si se especifica una clave, las filas de entrada de una fila de salida determinada se limitan al bloque contiguo de filas que tienen el mismo valor de clave que la fila de salida. Esta restricción se suma a todas las demás limitaciones colocadas en las filas de entrada por otros parámetros de la transformación <span class="wintitle"> CrossRows</span>. </p> <p> Por ejemplo, si trabaja con datos web y convierte el campo x-session-key (que tiene un valor único para cada sesión) en la clave, las filas de entrada para la transformación se limitan a aquellas filas que tienen el mismo valor x-session-key que la fila de salida. Por lo tanto, solo está considerando las filas de entrada que representan vistas de página que se producen durante la misma sesión que la fila de salida. </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Operación </td> 
   <td colname="col2"> <p>Operación que, para cada fila de salida, se aplica a todas las filas de entrada que cumplan todas las condiciones definidas por los parámetros Condición de entrada, Clave, Inicio de fila, Fin de fila, Inicio de tiempo y Fin de tiempo para generar una salida: 
     <ul id="ul_C01CCF73A9544BCFB7B1105042FEF2DD"> 
      <li id="li_2D1A192970904499AB9F4431D51106D7"> ALL toma todos los valores del campo de entrada de las filas de entrada y los genera como un vector. </li> 
      <li id="li_B8863724AD924DE5BDBC987143548257"> SUM interpreta los valores del campo de entrada de las filas de entrada como números y los suma. </li> 
      <li id="li_BF930069DCEA4E0B80893C3C06CAE100"> LA PRIMERA FILA genera el valor del campo de entrada desde la primera fila de entrada. </li> 
      <li id="li_04B9E2D88C0847E28101FC830C18D8E2"> ÚLTIMA FILA genera el valor del campo de entrada desde la última fila de entrada. </li> 
     </ul> </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Salida </td> 
   <td colname="col2"> Nombre del campo de salida. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Inicio de fila/Final de fila </td> 
   <td colname="col2"> <p>Opcional. Especifica un rango de filas de entrada relativas a la fila de salida. Por ejemplo, un valor Comenzar fila de "0" excluye todas las filas que hay antes de la fila de salida. Un valor de inicio de fila de "1" también excluye la fila de salida. Los intervalos comunes incluyen: 
     <ul id="ul_B030F32A5146430BA50DD4FAB4A527B0"> 
      <li id="li_30DFB8C0265349C295943A1CB8077B86"> Comenzar 0: Esta fila y todas las posteriores. </li> 
      <li id="li_9090C2E94E394351867BC5B78F27B41C"> Comenzar 1: Todas las filas siguientes. </li> 
      <li id="li_F870DC913E3F45BA94EE2EC04D344DE0"> Fin 0: Esta fila y todas las anteriores. </li> 
      <li id="li_B8A576E419744D84AB1298E5155B583E"> Fin -1: Todas las filas anteriores. </li> 
      <li id="li_CD2307A262D34542A2860FF07005CAD7"> Comienzo -1, Final -1: La fila anterior. </li> 
      <li id="li_6BF30B7BB7CC40A68B2332A3C11DD3B5"> Comienzo 1, Fin 1: La siguiente fila. </li> 
     </ul> </p> </td> 
   <td colname="col3"> Todas las filas </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Hora de inicio/fin de hora </td> 
   <td colname="col2"> <p>Opcional. Especifica un intervalo de veces relativo al tiempo de la fila de salida. Por ejemplo, un Time End de 30 minutos incluye todas las filas que se producen en los 30 minutos siguientes a la fila de salida. Un valor Comenzar de tiempo de -30 minutos incluye todas las filas que se producen en los 30 minutos anteriores a la fila de salida. </p> <p> Las unidades de tiempo disponibles son días, semanas, horas, minutos, ms (milisegundos), garrapatas (100 nanosegundos) y ns (nanosegundos). </p> </td> 
   <td colname="col3"> Todas las horas </td> 
  </tr> 
 </tbody> 
</table>

La transformación [!DNL CrossRows] de este ejemplo se aplica a filas de datos web para encontrar para cada vista de página la hora de la siguiente vista de página. Como sabemos que [!DNL CrossRows] solo se aplica durante la fase de transformación del proceso de construcción del conjunto de datos, las filas de datos se ordenan por visitante (cada visitante tiene un ID de seguimiento único) y por hora.

El campo de entrada, x-timestamp, solo se considera para aquellas filas de entrada en las que se rellena el campo x-is-page-view (indicando que la fila de datos representa una vista de página). El campo x-session-key (que tiene un valor único para cada sesión) se especifica para el parámetro Key . Por lo tanto, las filas de entrada (entradas de registro) para la transformación se limitan al bloque contiguo de filas que tienen el mismo valor de x-session-key que la fila de salida. En otras palabras, para que se considere la transformación, una fila de entrada debe representar una vista de página que se produzca durante la misma sesión que la vista de página en la fila de salida. La primera operación de fila toma el valor del campo de salida de la primera fila de entrada que cumple la condición [!DNL Input] y tiene el mismo valor de clave de sesión x que la fila de salida.

![](assets/cfg_TransformationType_CrossRows.png)

[!DNL CrossRows] se ejecuta en una cantidad de tiempo proporcional al tamaño de sus entradas más el tamaño de sus salidas. Esto significa que para las operaciones SUMA, PRIMERA FILA y ÚLTIMA FILA, no es menos eficiente que otras transformaciones. Para ALL, la situación es más compleja porque es posible configurar [!DNL CrossRows] para generar una cantidad de datos para cada fila de datos (entrada de registro) que sea proporcional al número total de filas (entradas de registro) para un ID de seguimiento determinado.
