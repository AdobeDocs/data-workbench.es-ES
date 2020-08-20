---
description: Las expresiones de Dimension nunca se utilizan solas, sino que se pueden utilizar en cualquier lugar donde se llame a una dimensión en una métrica o expresión de filtro.
solution: Analytics
title: Sintaxis para expresiones de dimensión
topic: Data workbench
uuid: c437cc52-4eb3-4202-a0b4-e23889f9c8a2
translation-type: tm+mt
source-git-commit: a276b16565634fea9b693206c8a55b528fada977
workflow-type: tm+mt
source-wordcount: '1855'
ht-degree: 0%

---


# Sintaxis para expresiones de dimensión{#syntax-for-dimension-expressions}

Las expresiones de Dimension nunca se utilizan solas, sino que se pueden utilizar en cualquier lugar donde se llame a una dimensión en una métrica o expresión de filtro.

1. Las palabras subrayadas deben escribirse literalmente en el texto de la expresión.
1. El formulario `{TEXT}?` representa texto opcional.
1. El formulario `{TEXT}*` representa texto que puede aparecer cero o más veces.
1. El formulario `{A | B | C |...}` representa texto que consta exactamente de una de las opciones dadas, como A, B o C....
1. El formulario `[A,B)` representa un rango de números, desde A hasta B, pero no incluido.

<table id="table_2D9AE1E2397843C284E838330370A1EE"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Identificador </p> </td> 
   <td colname="col2"> <p>Un identificador hace referencia a una dimensión con nombre. Para ver las reglas que rigen los identificadores legales, consulte <a href="../../../home/c-get-started/c-qry-lang-syntx/c-syntx-id.md#concept-735fa36fc49643269b3646aaaa8f2fa8"> Sintaxis para los identificadores </a>. </p> <p>Ejemplo: Sessions[ Session_Number = "1" ] es el número de sesiones que tienen un número de sesión de "1". Número de sesión es una dimensión con nombre a la que hace referencia el identificador. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>(Dimensión) </p> </td> 
   <td colname="col2"> <p>El resultado de (Dimension) es el mismo que el resultado del Dimension. Los paréntesis especifican el orden de las operaciones en una expresión. </p> <p>Ejemplo: Sesiones[ (página) = "/inicio" ] es el número de Sesiones que visitan la página "/inicio". </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Atenuar por nivel </p> </td> 
   <td colname="col2"> <p>Define una dimensión que tiene los mismos elementos que la dimensión Dim, pero que se relaciona con otras dimensiones a través del nivel de dimensión. </p> <p>Concretamente, un elemento de la nueva dimensión se refiere a los mismos elementos de nivel que el mismo elemento de Dim y se refiere a los elementos de cualquier otra dimensión que se relacionen con cualquiera de esos elementos de nivel. </p> <p>Ejemplo: Sesiones[ (página por Visitante)="/inicio" ] es el número de Sesiones de Visitantes que visitaron la página "/inicio". </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>shift(Dim,Level,Group,N) </p> </td> 
   <td colname="col2"> <p>Define una dimensión que tiene los mismos elementos que la dimensión Dim. El elemento eth del nivel de dimensión se refiere al mismo elemento de la nueva dimensión que el elemento Dim relacionado con el elemento e+Nth del nivel, siempre que los elementos eth y e+Nth del nivel se refieran al mismo elemento del grupo de dimensiones. </p> <p>Ejemplo: Page_Vistas[ shift(Page, Page_Vista, Session, 1)="/home" ] es el número de Vistas de página para las que la siguiente página vista en la misma sesión es "/home". </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>next(Dim,Level,Group,N) </p> </td> 
   <td colname="col2"> <p>Similar a shift(Dim,Level,Group,N), excepto que si hay valores vacíos en la dimensión, se omiten. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>segment(Level {,String-&gt;Filter}*) </p> </td> 
   <td colname="col2"> <p> Define una dimensión que clasifica los elementos de Nivel en función de una lista de filtros. Los elementos de la nueva dimensión son las cadenas dadas como argumentos. Cada elemento de Nivel se relaciona con el primer elemento de la dimensión de segmento cuyo filtro admite el elemento de Nivel. Es similar a la visualización de segmentos. </p> <p>Ejemplo: segment(Visitante, "Visitantes únicos" -&gt; Visitante_Sessions = 1, "Visitantes muy fieles" -&gt; Visitante_Sessions &gt; 10, "Todos los demás" -&gt; True) crea una dimensión que clasifica los Visitantes en tres grupos: los Visitantes únicos son los que tienen una sola sesión, los Visitantes muy fieles son los que tienen más de diez sesiones y todos los demás Visitante tienen el valor "solo" Todos Los Demás". </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>bucket(Level, Metric, Count, Format {, Inicio {, Size}? }?) </p> </td> 
   <td colname="col2"> <p>Define una dimensión cuyos elementos son rangos de números (de tamaño fijo, por ejemplo: [0-9], [10-19],...). Los elementos de Nivel se relacionan con el elemento del dim del bloque cuyo rango contiene el valor de Métrica para ese elemento de nivel. Formato es la cadena de formato printf que se utiliza para dar formato a los elementos de Métrica. </p> <p>Ejemplo: Si Page_Duration_Minutes es una dimensión de nivel de Vista de página que representa el número de minutos empleados en cada página, luego bucket(Session, sum(Page_Duration_Minutes, Page_Vista), 100, "%0.0f minutos", 0, 5) es una dimensión de nivel de sesión que representa el número de minutos empleados en cada sesión; sus elementos son intervalos de 5 minutos <code>{[0-5), [5-10),...,[495-500)}</code>. </p> <p>Inicio es el valor inicial del primer intervalo (predeterminado: 0) y Tamaño es el tamaño del intervalo (predeterminado: 1). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>prefix(Level {,ElementName-&gt;(Prefix{,Prefix}* )}* ) </p> </td> 
   <td colname="col2"> <p>Define una dimensión cuyos elementos son las cadenas ElementName dadas y están asociados con los conjuntos correspondientes de cadenas Prefix. Los elementos de Nivel están relacionados con el elemento del dim del prefijo, que está asociado con el prefijo más largo que coincide con el nombre del elemento de nivel dado. Los prefijos que finalizan con el carácter especial '$' deben coincidir exactamente. </p> <p>Por ejemplo, prefix(URI, "Productos" -&gt; ("/products/"), "Servicios" -&gt; ("/services/", "/products/service/"), "Garantías" -&gt; ("/products/warranty.html$", "/services/warranty.html$", "Todo lo demás" -&gt; ("/") crea una dimensión que clasifica los URI en las cuatro categorías enumeradas. El efecto en varias páginas es el siguiente: </p> <p>/products/warranty.html entra en garantía, ya que coincide exactamente con el prefijo /products/warranty.html$. </p> <p>/products/cars/specialcar.html entra en los productos, ya que coincide con el prefijo /products/ y ya no tiene el prefijo </p> <p>/products/service/something.html entra en Servicios, ya que coincide con el prefijo /products/service/ que es más largo que el prefijo /products/. </p> <p>/companyinfo/aboutus.html entra en la categoría "Todo lo demás", ya que el único prefijo que coincide es "/". </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>latency(Level, Clip, Dim, Filter, MaxBefore, MaxAfter, FormatString) </p> </td> 
   <td colname="col2"> <p>Consulte <a href="../../../home/c-get-started/c-intf-anlys-ftrs/c-config-ltcy-tbls/t-create-ltncy-dims.md#task-6d46ea8c89a047318d9c71bf105ef64a"> Creación de Dimension de latencia </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>cartsian_product(Separator {,Dim}*) </p> </td> 
   <td colname="col2"> <p>Define una dimensión cuyos elementos son todas las combinaciones ("el producto cartesiano") de los elementos de las dimensiones dadas. El nombre de cada elemento está hecho a partir de la concatenación de los elementos correspondientes en las dimensiones de entrada, separados por la cadena de separador dada. </p> <p>Por ejemplo, si la dimensión D1 tiene elementos {"a", "b"} y la dimensión D2 tiene los elementos {"x", "y"}, entonces product("-", D1, D2) tiene los elementos {"a-x", "a-y", "b-x", "b-y"}. </p> <p>Tenga en cuenta que, internamente, cada una de las dimensiones de entrada se trata como si el número de sus elementos fuera la siguiente potencia superior de dos. Esto hace que el producto cartesiano tenga algunos elementos ficticios. Al utilizar la API de Data Workbench, según el formato de salida, estos elementos pueden omitirse o mostrarse como "#nnn", donde nnn es el ordinal del elemento (y el cliente debe ignorarlo). </p> <p>Por ejemplo, en el ejemplo anterior, si D2 tuviera los tres elementos {"x", "y", "z"}, se trataría como si tuviera cuatro elementos y el producto cartesiano tendría los elementos {"a-x", "a-y", "a-z", "#3", "b-x", "b-y", "b-z", "#7"}. </p> <p>Si no se dan dimensiones, el resultado es una dimensión con un elemento, "#0", que equivale a la dimensión Ninguno. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>most_countable(Dim) </p> </td> 
   <td colname="col2"> <p>Se refiere a una dimensión ya existente: el antecesor contable más cercano de Dim en el esquema. Por ejemplo, el contador (URI) más cercano es idéntico a Page_Vista. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>normalized(Dim,Count) </p> </td> 
   <td colname="col2"> <p>Define una dimensión normalizada desde la dimensión denormalizada Dim, con hasta elementos Count. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>last_n(Dim, TimeMetric, FormatString, Count, Offset, TrimToData {, WeekStart}?) </p> </td> 
   <td colname="col2"> <p>Define una dimensión que tiene un subconjunto de los elementos de la dimensión Dim, cuyos elementos representan sectores de tiempo (por ejemplo, días, semanas o años). </p> <p>El subconjunto es un intervalo alrededor de un tiempo especificado, el valor de la métrica constante TimeMetric, que se interpreta como un valor de tiempo en segundos desde la medianoche UTC del 1 de enero de 1970. El rango tiene elementos Count, el último de los cuales son elementos Offset después del elemento Dim dado cuyo nombre es el resultado de dar formato al valor de la métrica con la cadena FormatString dada. FormatString utiliza los mismos % escapes que la función estándar de la biblioteca C strftime. </p> <p>Si trimToData es true, se eliminan todos los elementos al principio de la dimensión resultante, que serían anteriores al principio de Dim. Cuando sea false, siempre habrá el número exacto de elementos especificado por Count. Tenga en cuenta que siempre puede haber elementos al final de la dimensión resultante que no estén realmente en Dim. </p> <p>El valor opcional WeekStart, si se especifica, debe ser uno de { "Sun", "Mon", "Tue", "Wed", "Thu", "Fri", "Sat" }. Modifica TimeMetric moviéndola hacia atrás hasta la aparición más reciente de ese día de la semana. </p> <p>Ejemplo: Si Semana tiene los elementos { "10/03/10", "10/10/10", ..., "12/12/10" } y la métrica integrada Con fecha tiene el valor 1292348109 (que representa un tiempo a mediados del 14 de diciembre de 2000 10), luego last n(Week, As_Of, "%m/%d/%y", 4, 0, false, "Sun") define la dimensión con elementos { "12/12/10", "12/19/10", "12/23/10", "12/30/10" }. </p> <p>Ejemplo 2: Si la dimensión Semana sólo tiene elementos {"12/19/10", "12/26/10", ..., "01/30/11"}, y la métrica A/A es la anterior, la última n(Semana, As_Of, "%m/%d/%y", 4, 0, true, "Sun") proporciona una dimensión con elementos con {"12/19/10", "23/12/10", "30/12/10"}. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>days_of_previous_month(Dim, TimeMetric, FormatString, nMonths, includeThisMonth, TrimToData) </p> </td> 
   <td colname="col2"> <p>Define una dimensión que tiene un subconjunto de los elementos de Dim, cuyos elementos representan días. El subconjunto es un intervalo alrededor de un tiempo especificado, el valor de la métrica constante TimeMetric, que se interpreta como un valor de tiempo en segundos desde la medianoche UTC del 1 de enero de 1970. El intervalo incluirá los elementos correspondientes a cada día en los n meses anteriores a la hora especificada. Si includeThisMonth es true, el intervalo también incluye cada día del mes que contenga la hora especificada. </p> <p>FormatString especifica el formato de los elementos de Dim, utilizando "%" escapes como en la función estándar de biblioteca C strftime. </p> <p>Si trimToData es true, se eliminan todos los elementos al principio de la dimensión resultante, que serían anteriores al principio de Dim. Cuando sea false, siempre habrá el número exacto de elementos especificado por Count. Tenga en cuenta que siempre puede haber elementos al final de la dimensión resultante que no estén realmente en Dim. </p> <p>Ejemplo: Si Day tiene los elementos { "01/01/10", "01/02/10", ..., "12/31/10" } y la métrica integrada Con fecha tiene el valor 1292348109 (que representa un tiempo a mediados del 14 de diciembre de 2000 10), entonces los días de meses anteriores (Día, Como_De, "%m/%d/%y", 2, false, false) tendrán elementos { "10/01/10", "10/02/10", ..., "11/30/10" }. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>days_of_current_month(Dim, TimeMetric, FormatString, allMonth, trimToData) </p> </td> 
   <td colname="col2"> <p>Similar a los días de meses anteriores, excepto que los elementos corresponden sólo a los días del mismo mes que la hora especificada por TimeMetric. Si allMonth es true, habrá un elemento para cada día del mes correspondiente; de lo contrario, solo los días desde el primero del mes correspondiente hasta el día que contenga la hora especificada formarán parte de la dimensión. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>days_of_future_month(Dim, TimeMetric, FormatString, nMonths, includeThisMonth, TrimToData) </p> </td> 
   <td colname="col2"> <p>Similar a los días de meses anteriores, excepto que los elementos corresponden a los días de meses posteriores, en lugar de anteriores, al mes que contiene la hora especificada por TimeMetric. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>hour_of_day(Dim, Métrica, TimeFormatString, nDaysForward, TrimData) </p> </td> 
   <td colname="col2"> <p>Define una dimensión que tiene un subconjunto de los elementos de Dim, cuyos elementos representan horas. El subconjunto es un intervalo alrededor de un tiempo especificado, el valor de la métrica constante TimeMetric, que se interpreta como un valor de tiempo en segundos desde la medianoche UTC del 1 de enero de 1970. El rango incluye los elementos correspondientes a cada hora del día nDaysForward después del día que contiene la hora especificada por TimeMetric. </p> <p>FormatString especifica el formato de los elementos de Dim, utilizando "%" escapes como en la función estándar de biblioteca C strftime. La cadena de formato siempre debe mostrar una cadena que represente la medianoche al principio del día de la hora pasada. </p> <p>Si trimToData es true, se eliminan todos los elementos al principio de la dimensión resultante, que serían anteriores al principio de Dim. Cuando sea false, siempre habrá el número exacto de elementos especificado por Count. Tenga en cuenta que siempre puede haber elementos al final de la dimensión resultante que no estén realmente en Dim. </p> <p>Ejemplo: Si Hour tiene los elementos { "01/01/10 00:00", "01/01/10 01:00", ..., "12/31/10 23:00" }, y la métrica integrada Con fecha tiene el valor 12923481 09 (que representa una hora a mediados del 14 de diciembre de 2010), entonces horas del día (Hora, As_Of, "%x 00:00", 0, false) tiene elementos { "12/10 00:00", "12/12/10 01:00", . ..., "12/12/10 23:00" }. </p> </td> 
  </tr> 
 </tbody> 
</table>

