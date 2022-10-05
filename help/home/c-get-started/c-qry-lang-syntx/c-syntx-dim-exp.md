---
description: Las expresiones de Dimension nunca se utilizan solas, pero pueden utilizarse en cualquier lugar en el que se llame a una dimensión en una métrica o expresión de filtro.
title: Sintaxis para expresiones de dimensión
uuid: c437cc52-4eb3-4202-a0b4-e23889f9c8a2
exl-id: 58609e31-8ad8-418b-9a9f-40462d6443f7
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '1855'
ht-degree: 0%

---

# Sintaxis para expresiones de dimensión{#syntax-for-dimension-expressions}

{{eol}}

Las expresiones de Dimension nunca se utilizan solas, pero pueden utilizarse en cualquier lugar en el que se llame a una dimensión en una métrica o expresión de filtro.

1. Las palabras subrayadas deben introducirse literalmente en el texto de la expresión.
1. El formulario `{TEXT}?` representa texto opcional.
1. El formulario `{TEXT}*` representa el texto que puede aparecer cero o más veces.
1. El formulario `{A | B | C |...}` representa el texto que consta exactamente de una de las opciones dadas, como A, B o C....
1. El formulario `[A,B)` representa un rango de números, desde A hasta B, pero no incluye B.

<table id="table_2D9AE1E2397843C284E838330370A1EE"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Identificador </p> </td> 
   <td colname="col2"> <p>Un identificador hace referencia a una dimensión con nombre. Para ver las reglas que rigen los identificadores legales, consulte <a href="../../../home/c-get-started/c-qry-lang-syntx/c-syntx-id.md#concept-735fa36fc49643269b3646aaaa8f2fa8"> Sintaxis para identificadores </a>. </p> <p>Ejemplo: Sessions[ Session_Number = "1" ] es el número de sesiones que tuvieron un número de sesión de "1". Número de sesión es una dimensión con nombre a la que hace referencia el identificador. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>(Dimensión) </p> </td> 
   <td colname="col2"> <p>El resultado de (Dimension) es el mismo que el resultado del Dimension. Los paréntesis especifican el orden de las operaciones en una expresión. </p> <p>Ejemplo: Sesiones[ (página) = "/home" ] es el número de Sesiones que visitan la página "/home". </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>atenuar por nivel </p> </td> 
   <td colname="col2"> <p>Define una dimensión que tiene los mismos elementos que la dimensión Dim, pero se relaciona con otras dimensiones a través del nivel de dimensión. </p> <p>Concretamente, un elemento de la nueva dimensión se refiere a los mismos elementos de nivel que el mismo elemento de Dim y se refiere a los elementos de cualquier otra dimensión que se relacionen con cualquiera de esos elementos de nivel. </p> <p>Ejemplo: Sessions[ (Page by Visitor)="/home" ] es el número de sesiones de visitantes que visitaron la página "/home". </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>shift(Dim,Level,Group,N) </p> </td> 
   <td colname="col2"> <p>Define una dimensión que tiene los mismos elementos que la dimensión Dim. El elemento eth del nivel de dimensión se relaciona con el mismo elemento de la nueva dimensión que el elemento Dim relacionado con el elemento e+Nth del nivel, siempre que los elementos eth y e+Nth del nivel estén relacionados con el mismo elemento del grupo de dimensiones. </p> <p>Ejemplo: Page_Views[ shift(Page, Page_View, Session, 1)="/home" ] es el número de vistas de página para las que la siguiente página vista en la misma sesión es "/home". </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>next(Dim,Level,Group,N) </p> </td> 
   <td colname="col2"> <p>Similar a shift(Dim,Level,Group,N), excepto que si hay valores vacíos en la dimensión, se omiten. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>segment(Level {,String-&gt;Filter}*) </p> </td> 
   <td colname="col2"> <p> Define una dimensión que clasifica elementos de Level en función de una lista de filtros. Los elementos de la nueva dimensión son las cadenas dadas como argumentos. Cada elemento de Nivel está relacionado con el primer elemento de la dimensión de segmento cuyo filtro admite el elemento de Nivel. Esto es similar a la visualización de segmentos. </p> <p>Ejemplo: segment(Visitor, "Visitantes únicos" -&gt; Visitor_Sessions = 1, "Visitantes muy fieles" -&gt; Visitor_Sessions &gt; 10, "Todos los demás" -&gt; True) crea una dimensión que clasifica a los visitantes en tres grupos: Los visitantes únicos son los que tienen una sola sesión, los visitantes muy fieles son los que tienen más de diez sesiones y todos los demás visitantes tienen el valor "Un" Todos los demás". </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>bucket(Level, Metric, Count, Format {, Start {, Size}? }?) </p> </td> 
   <td colname="col2"> <p>Define una dimensión cuyos elementos son rangos de números (de tamaño fijo, por ejemplo, [0-9], [10-19],...). Los elementos de Nivel están relacionados con el elemento de la dim del bloque cuyo intervalo contiene el valor de Métrica para ese elemento de nivel. Formato es la cadena de formato printf que se utiliza para dar formato a los elementos de la métrica. </p> <p>Ejemplo: Si Page_Duration_Minutes es una dimensión de nivel de vista de página que representa el número de minutos empleados en cada página, bucket(Session, sum(Page_Duration_Minutes, Page_View), 100, "%0.0f minutes", 0, 5) es una dimensión de nivel de sesión que representa el número de minutos empleados en cada sesión; sus elementos son intervalos de 5 minutos <code>{[0-5), [5-10),...,[495-500)}</code>. </p> <p>Start es el valor inicial del primer intervalo (predeterminado: 0) y Size es el tamaño del intervalo (predeterminado: 1). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>prefix(Level {,ElementName-&gt;(Prefix{,Prefix}* )}* ) </p> </td> 
   <td colname="col2"> <p>Define una dimensión cuyos elementos son las cadenas ElementName dadas y están asociados a los conjuntos correspondientes de cadenas Prefix. Los elementos de Nivel están relacionados con el elemento del prefijo dim, que está asociado con el prefijo más largo que coincide con el nombre del elemento determinado del nivel. Los prefijos que terminen con el carácter especial '$' deben coincidir exactamente. </p> <p>Por ejemplo, prefix(URI, "Productos" -&gt; ("/products/"), "Servicios" -&gt; ("/services/", "/products/service/"), "Garantías" -&gt; ("/products/warranty.html$", "/services/warranty.html$", "Todo lo demás" -&gt; ("/") crea una dimensión que clasifica los URI en las cuatro categorías enumeradas. El efecto en varias páginas es el siguiente: </p> <p>/products/warranty.html entra en garantía, ya que coincide exactamente con el prefijo /products/warranty.html$ . </p> <p>/products/cars/specialcar.html Se introduce en Productos, ya que coincide con el prefijo /products/ y ya no se coloca el prefijo </p> <p>/products/service/something.html Entra en Servicios, ya que coincide con el prefijo /products/service/ que es más largo que el prefijo /products/ . </p> <p>/companyinfo/aboutus.html Accede a la categoría "Todo lo demás", ya que el único prefijo con el que coincide es "/". </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>latency(Level, Clip, Dim, Filter, MaxBefore, MaxAfter, FormatString) </p> </td> 
   <td colname="col2"> <p>Consulte <a href="../../../home/c-get-started/c-intf-anlys-ftrs/c-config-ltcy-tbls/t-create-ltncy-dims.md#task-6d46ea8c89a047318d9c71bf105ef64a"> Creación de Dimension de latencia </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>cartesiano_product(Separator {,Dim}*) </p> </td> 
   <td colname="col2"> <p>Define una dimensión cuyos elementos son todas las combinaciones ("el producto cartesiano") de los elementos de las dimensiones dadas. El nombre de cada elemento está formado por la concatenación de los elementos correspondientes en las dimensiones de entrada, separados por la cadena de separador dada. </p> <p>Por ejemplo, si la dimensión D1 tiene elementos {"a", "b"} y la dimensión D2 tiene los elementos {"x", "y"}, entonces el producto cartesiano("-", D1, D2) tiene los elementos {"a-x", "a-y", "b-x", "b-y"}. </p> <p>Tenga en cuenta que, internamente, cada una de las dimensiones de entrada se trata como si el número de sus elementos fuera la siguiente potencia superior de dos. Esto hace que el producto cartesiano tenga algunos elementos ficticios. Al utilizar la API de Data Workbench, según el formato de salida, estos elementos pueden omitirse o mostrarse como "#nn", donde nnn es el ordinal del elemento (y el cliente debe ignorarlo). </p> <p>Por ejemplo, en el ejemplo anterior, si D2 tuviera los tres elementos {"x", "y", "z"}, se trataría como si tuviera cuatro elementos y el producto cartesiano tendría los elementos {"a-x", "a-y", "a-z", "#3", "b-x", "b-y", "b-z", "#7"}. </p> <p>Si no se proporcionan dimensiones, el resultado es una dimensión con un elemento, "#0", que equivale a la dimensión Ninguno. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>near_countable(Dim) </p> </td> 
   <td colname="col2"> <p>Hace referencia a una dimensión ya existente: el antecesor contable más cercano de Dim en el esquema. Por ejemplo, la cuenta contable más cercana (URI) es idéntica a Page_View. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>normalized(Dim,Count) </p> </td> 
   <td colname="col2"> <p>Define una dimensión normalizada desde la dimensión denormalizada Dim, con hasta elementos Count . </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>last_n(Dim, TimeMetric, FormatString, Count, Offset, TrimToData {, WeekStart}?) </p> </td> 
   <td colname="col2"> <p>Define una dimensión que tiene un subconjunto de los elementos de la dimensión Dim, cuyos elementos representan fracciones de tiempo, por ejemplo, días, semanas o años. </p> <p>El subconjunto es un intervalo en torno a una hora especificada, el valor de la métrica constante TimeMetric, que se interpreta como un valor de tiempo en segundos desde la medianoche UTC del 1 de enero de 1970. El rango tiene elementos Count, el último de los cuales son elementos Offset después del elemento de Dim dado cuyo nombre es el resultado de dar formato al valor de la métrica con la cadena FormatString dada. FormatString utiliza los mismos % escapes que la función estándar de la biblioteca C durante el tiempo de espera. </p> <p>Si trimToData es verdadero, se elimina cualquier elemento al principio de la dimensión resultante, que sería antes del comienzo de Dim. Cuando sea false, siempre habrá el número exacto de elementos especificados por Count. Tenga en cuenta que siempre puede haber elementos al final de la dimensión resultante que no estén realmente en Dim. </p> <p>El WeekStart opcional, si se especifica, debe ser uno de { "Sun", "Mon", "Tue", "Wed", "Thu", "Fri", "Sat" }. Modifica TimeMetric moviéndola hacia atrás hasta la ocurrencia más reciente de ese día de la semana. </p> <p>Ejemplo: Si Week tiene los elementos { "10/03/10", "10/10/10", ..., "12/12/10" } y la métrica integrada Con fecha tiene el valor 1292348109 (que representa una hora a mediados del 14 de diciembre de 200 10), la última n(Week, As_Of, "%m/%d/%y", 4, 0, false, "Sun") define la dimensión con elementos { "12/12/10", "19/12/10", "23/12/10", "30/12/10" }. </p> <p>Ejemplo 2: Si la dimensión Semana solo tiene elementos {"12/19/10", "26/12/10", ..., "30/01/11"} y la métrica Con es la anterior, la última n(Semana, As_Of, "%m/%d/%y", 4, 0, true, "Sun") da una dimensión con {"19/12/10", "23/12/10", "30/12/10"}. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>days_of_previous_month(Dim, TimeMetric, FormatString, nMonths, includeThisMonth, TrimToData) </p> </td> 
   <td colname="col2"> <p>Define una dimensión que tiene un subconjunto de los elementos de Dim, cuyos elementos representan días. El subconjunto es un intervalo en torno a una hora especificada, el valor de la métrica constante TimeMetric, que se interpreta como un valor de tiempo en segundos desde la medianoche UTC del 1 de enero de 1970. El intervalo incluye los elementos correspondientes a cada día en los nMeses anteriores a la hora especificada. Si includeThisMonth es verdadero, el rango también incluye cada día del mes que contiene la hora especificada. </p> <p>FormatString especifica el formato de los elementos de Dim, utilizando "%" escapes como en la función estándar de la biblioteca C en el tiempo de espera. </p> <p>Si trimToData es verdadero, se elimina cualquier elemento al principio de la dimensión resultante, que sería antes del comienzo de Dim. Cuando sea false, siempre habrá el número exacto de elementos especificados por Count. Tenga en cuenta que siempre puede haber elementos al final de la dimensión resultante que no estén realmente en Dim. </p> <p>Ejemplo: Si Day tiene los elementos { "01/01/10", "01/02/10", ..., "31/12/10" } y la métrica integrada Con fecha tiene el valor 1292348109 (que representa una hora a mediados del 14 de diciembre de 200 10), entonces los días de meses anteriores (Día, As_Of, "%m/%d/%y", 2, false, false) tendrán elementos { "10/01/10", "10/02/10", ..., "30/11/10" }. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>days_of_current_month(Dim, TimeMetric, FormatString, allMonth, trimToData) </p> </td> 
   <td colname="col2"> <p>Similar a los días de meses anteriores, excepto que los elementos corresponden solo a días del mismo mes que la hora especificada por TimeMetric. Si allMonth es true, habrá un elemento para cada día del mes correspondiente; de lo contrario, solo los días desde el primer día del mes correspondiente hasta el día que contenga la hora especificada formarán parte de la dimensión. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>days_of_Future_month(Dim, TimeMetric, FormatString, nMonths, includeThisMonth, TrimToData) </p> </td> 
   <td colname="col2"> <p>Similar a los días de meses anteriores, excepto que los elementos corresponden a los días de meses después, en lugar de antes, del mes que contiene el tiempo especificado por TimeMetric. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>hours_of_day(Dim, Metric, TimeFormatString, nDaysForward, TrimData) </p> </td> 
   <td colname="col2"> <p>Define una dimensión que tiene un subconjunto de los elementos de Dim, cuyos elementos representan horas. El subconjunto es un intervalo en torno a una hora especificada, el valor de la métrica constante TimeMetric, que se interpreta como un valor de tiempo en segundos desde la medianoche UTC del 1 de enero de 1970. El rango incluye los elementos correspondientes a cada hora del día nDaysForward después del día que contiene la hora especificada por TimeMetric. </p> <p>FormatString especifica el formato de los elementos de Dim, utilizando "%" escapes como en la función estándar de la biblioteca C en el tiempo de espera. La cadena de formato siempre debe generar una cadena que represente la medianoche del principio del día en que se ha pasado el tiempo. </p> <p>Si trimToData es verdadero, se elimina cualquier elemento al principio de la dimensión resultante, que sería antes del comienzo de Dim. Cuando sea false, siempre habrá el número exacto de elementos especificados por Count. Tenga en cuenta que siempre puede haber elementos al final de la dimensión resultante que no estén realmente en Dim. </p> <p>Ejemplo: Si Hour tiene los elementos { "01/01/10 00:00", "01/01/10 01:00", ..., "31/12/10 23:00" }, y la métrica integrada Con fecha tiene el valor 12923481 09 (que representa una hora a mediados del 14 de diciembre de 2010), entonces horas del día (Hora, As_Of, "%x 00:00", 0, false) tiene elementos { "12/12/10 00:00", "12/12/10 01:00", . ..., "12/12/10 23:00" }. </p> </td> 
  </tr> 
 </tbody> 
</table>
