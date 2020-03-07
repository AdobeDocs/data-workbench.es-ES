---
description: Hay varios tipos de dimensiones disponibles en el servidor del área de trabajo de datos. Como tal, es importante conocer el tipo de dimensión al usar una dimensión para crear métricas, filtros o dimensiones derivadas.
solution: Analytics
title: Tipos de dimensiones
topic: Data workbench
uuid: 07659373-8d9b-473d-8daa-ca8e7ac4afe8
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Tipos de dimensiones{#dimension-types}

Hay varios tipos de dimensiones disponibles en el servidor del área de trabajo de datos. Como tal, es importante conocer el tipo de dimensión al usar una dimensión para crear métricas, filtros o dimensiones derivadas.

Insight Server puede crear y mantener los siguientes tipos de dimensiones:

<table id="table_1A79B6C57ED145B6AA3BB05DD37AAD1B"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Tipos de dimensiones </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Contable </td> 
   <td colname="col2">Tipo de dimensión en el que el sistema puede contar el número de elementos de la dimensión. Las dimensiones contables deben derivarse de otras dimensiones del mismo tipo. Las dimensiones contables pueden ser principales con respecto a otras dimensiones o secundarias con respecto a otras dimensiones contables. <p>Ejemplos: visitante, sesión, vista de página, registro y pedido. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> Simple </td> 
   <td colname="col2">dimensión que tiene una relación "uno a varios" con respecto a una dimensión contable principal. Una dimensión simple puede considerarse como la representación de una propiedad de elementos de su dimensión principal. <p>Ejemplo: Referente de visitante es una dimensión simple cuya dimensión principal es Visitante. Los visitantes solo pueden tener un referente de visitante (su primer referente HTTP), pero puede haber varios visitantes que tengan el mismo referente de visitante. Por lo tanto, Referente de visitante tiene una relación “uno a varios” con la dimensión Visitante. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> Numéricos </td> 
   <td colname="col2">Dimensión que tiene valores numéricos ordenados y una relación uno a varios con una dimensión contable principal. Una dimensión numérica puede considerarse como la representación de una propiedad numérica de elementos de su dimensión principal. Las dimensiones numéricas se utilizan frecuentemente para definir métricas “sum”. <p>Ejemplo: la dimensión numérica Ingreso por sesión define los ingresos, en dólares, de cada sesión. Cada sesión posee una cantidad única de ingresos, pero puede haber varias sesiones con los mismos ingresos y, por lo tanto, tiene una relación “uno a varios” con la dimensión Sesión. A metric “Revenue” might be defined as <span class="filepath"> sum(Session_Revenue, Session)</span>, giving the total amount of revenue for the selected Sessions. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> De varios a muchos </td> 
   <td colname="col2">Dimensión que tiene una relación de varios a varios con una dimensión contable principal. Una dimensión “varios a varios” se puede considerar como la representación de un “conjunto” de valores para cada elemento de su dimensión principal. Este tipo de dimensión sería el equivalente a una dimensión contable (anónima) con su dimensión principal, y a una dimensión simple que tenga una dimensión principal de tipo contable anónima.  <p>Ejemplo: la dimensión “varios a varios” Frase de búsqueda tiene una dimensión principal Sesión. Cada sesión puede utilizar cero o más frases de búsqueda y una frase de búsqueda puede usarse en cualquier número de sesiones. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> Denormal </td> 
   <td colname="col2">Dimensión que tiene una relación uno a uno con una dimensión contable principal. Los nombres de elementos de la dimensión denormalizada pueden contener información acerca de los elementos correspondientes de la dimensión principal. Una dimensión denormalizada puede considerarse como el almacenamiento de un valor de cadena arbitrario para cada elemento de la dimensión principal. Las dimensiones denormalizadas pueden utilizarse con la capacidad de exportación de segmentos del servidor de Insight con el objetivo de informar sobre un subconjunto o “segmento” de una dimensión contable. Además, se puede hacer referencia a las dimensiones denormalizadas en fórmulas de métricas y visualizaciones de hojas de cálculo, y se pueden usar (con ciertas restricciones) para definir filtros.  <p>Ejemplo: la dimensión denormalizada Dirección de correo electrónico tiene una dimensión principal Visitante. Cada visitante tiene una dirección de correo electrónico y cada elemento de la dimensión Correo electrónico está asociado a un único visitante. Aunque dos visitantes tengan la misma dirección de correo electrónico, sus direcciones serán elementos diferentes de la dimensión Dirección de correo electrónico. Una Exportación de segmentos puede hacer referencia a la dimensión Dirección de correo electrónico para generar la dirección de correo de cada visitante en un segmento. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> Fecha </td> 
   <td colname="col2">Dimensión que permite crear un conjunto de dimensiones de tiempo local periódicas o absolutas (como día, día de la semana, hora, hora del día, etc.) en función de un campo de marca de hora que se especifique. Al definir dimensiones de tiempo, también se puede elegir como primer día de la semana un día distinto al lunes. Para ello, debe especificarse el parámetro Día de inicio de la semana. <p>Ejemplo: la dimensión de tiempo Tiempo de sesión tiene como principal la dimensión Sesión. Por lo tanto, la dimensión define un conjunto de dimensiones de tiempo (día, día de la semana, hora, hora del día, mes y semana) cuyos elementos se corresponden a los tiempos en que se iniciaron las sesiones de los usuarios en el sitio.  </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> Derivado </td> 
   <td colname="col2">Las dimensiones derivadas, en lugar de definirse en la configuración del conjunto de datos en función de los datos que se procesan, se definen en el perfil en función de otras dimensiones o métricas. Muchas dimensiones derivadas se crean automáticamente con el objetivo de impulsar distintos tipos de visualizaciones. <p>Por ejemplo, cuando un usuario crea un sitio o un mapa de procesos, Insight Server crea de forma silenciosa una dimensión "Prefijo". Otras, como las dimensiones de tiempo de los informes, están definidas por archivos que se encuentran en el directorio Dimensiones de un perfil. </p></td> 
  </tr> 
 </tbody> 
</table>

