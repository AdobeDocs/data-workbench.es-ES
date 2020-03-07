---
description: Una dimensión de tiempo le permite crear un conjunto de dimensiones de tiempo local periódicas o absolutas (como Día, Día de la semana, Hora del día, Hora de la reserva, etc.) en función de cualquier campo de marca de hora que especifique para el parámetro Tiempo de entrada (1970 epoch).
solution: Analytics
title: Dimensiones temporales
topic: Data workbench
uuid: b633cf4f-0db4-4378-9e59-43b6ad8f772d
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Dimensiones temporales{#time-dimensions}

Una dimensión de tiempo le permite crear un conjunto de dimensiones de tiempo local periódicas o absolutas (como Día, Día de la semana, Hora del día, Hora de la reserva, etc.) en función de cualquier campo de marca de hora que especifique para el parámetro Tiempo de entrada (1970 epoch).

Al definir dimensiones de tiempo, también se puede elegir como primer día de la semana un día distinto al lunes. Para ello, debe especificarse el parámetro Día de inicio de la semana. Puede definir más de un conjunto de dimensiones de tiempo en el conjunto de datos siempre que las dimensiones tengan nombres diferentes.

Las dimensiones de tiempo se definen con los parámetros siguientes:

<table id="table_9734F6CD7ABA4661A2F9A5FB948A7282"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parámetro </th> 
   <th colname="col2" class="entry"> Descripción </th> 
   <th colname="col3" class="entry"> Valor predeterminado </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Nombre </td> 
   <td colname="col2"> Nombre descriptivo de la dimensión tal como aparece en el área de trabajo de datos. El nombre de la dimensión no puede incluir un guión (-). </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Comentarios </td> 
   <td colname="col2"> Opcional. Notas sobre la dimensión extendida. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Dimensiones </td> 
   <td colname="col2"> <p>Puede especificar nombres de dimensión para cualquiera de los siguientes períodos: </p> <p> 
     <ul id="ul_EB0837DD66BE4004A615A6029EEF4CD5"> 
      <li id="li_2E46E6DB004E443C8CC831DCEE743D60"> Día </li> 
      <li id="li_F59A27779EBE4E2A84E0972EE8BCDFA7"> Día de la semana </li> 
      <li id="li_7D74CD547ED1449091EF7B2E0E8C46DE"> Hora </li> 
      <li id="li_706AF9D385CB44C098DEBACA3BA2CD4B"> Hora del día </li> 
      <li id="li_76FBF69B25954885A0192D308A155E41"> Mes </li> 
      <li id="li_3C16955BE5C54291A25E25CD31259661"> Semana </li> 
     </ul> </p> <p> Los nombres que introduzca aquí son los que aparecen en los menús de dimensión y en las visualizaciones del área de trabajo de datos. Si deja en blanco el nombre de una dimensión de tiempo, la dimensión no se crea en el conjunto de datos. </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Oculto </td> 
   <td colname="col2"> Determina si la dimensión aparece en la interfaz del área de trabajo de datos. De forma predeterminada, este parámetro se establece en false. Si, por ejemplo, la dimensión se va a utilizar solo como base de una métrica, puede establecer este parámetro en true para ocultar la dimensión de la visualización del área de trabajo de datos. </td> 
   <td colname="col3"> true </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Tiempo de entrada (1970 epoch) </td> 
   <td colname="col2"> <p>Nombre del campo de marca de hora que se va a utilizar como entrada. </p> <p> <p>Nota:  Los valores del campo deben representar el número de segundos transcurridos desde el 1 de enero de 1970 a las 00:00:01. Si el tiempo de entrada no es un tiempo válido (1970 a 2037), el proceso de transformación fallará y el servidor del área de trabajo de datos generará un error. </p> </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Principal </td> 
   <td colname="col2"> Nombre de la dimensión principal. Cualquier dimensión contable puede ser una dimensión principal. Para datos web, el elemento principal es Session. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Día de inicio de semana </td> 
   <td colname="col2"> <p>El día que se utilizará como primer día de una semana. </p> <p> Este parámetro afecta a la dimensión Semana, a la dimensión Día de la semana y a cualquier dimensión de tiempo de informes definida en términos de semanas. </p> </td> 
   <td colname="col3"> Mon </td> 
  </tr> 
 </tbody> 
</table>

En este ejemplo se crea un conjunto de dimensiones de tiempo basadas en el campo de entrada definido por el usuario x-time-1970. El conjunto de dimensiones de tiempo se denomina &quot;Tiempo de sesión&quot;. Dado que el elemento principal de cada dimensión es la dimensión Sesión, cada elemento de las dimensiones de tiempo corresponde al tiempo en el que se inició una sesión. El parámetro Día de inicio de semana especifica que cada semana de la dimensión Semana comienza el lunes.

![](assets/cfg_Transformation_Dim_TimeDim.png)
