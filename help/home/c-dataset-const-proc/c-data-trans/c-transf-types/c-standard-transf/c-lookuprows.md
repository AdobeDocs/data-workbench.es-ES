---
description: La transformación LookupRows examina otras entradas de registro con el mismo ID de seguimiento y establece el valor del campo de salida en el valor de un campo designado en la fila de entrada.
title: LookupRows
uuid: 4cff7cf1-00c8-4ab1-8adc-3805518226d3
exl-id: caa9a311-b056-4fe8-bb11-1605cc690375
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '946'
ht-degree: 0%

---

# LookupRows{#lookuprows}

La transformación LookupRows examina otras entradas de registro con el mismo ID de seguimiento y establece el valor del campo de salida en el valor de un campo designado en la fila de entrada.

Debido a que la transformación [!DNL LookupRows] realiza su búsqueda en entradas de registro y no en archivos de búsqueda, es muy similar a la transformación [!DNL CrossRows]. Consulte [CrossRows](../../../../../home/c-dataset-const-proc/c-data-trans/c-transf-types/c-standard-transf/c-crossrows.md#concept-fcace08804f54db397ed631cc13ff4f2).

Para que funcione, la transformación [!DNL LookupRows] requiere que los datos se ordenen a tiempo y se agrupen por el ID de seguimiento en los datos de origen. Por lo tanto, [!DNL LookupRows] solo funciona cuando se define en el archivo [!DNL Transformation.cfg] o en un archivo [!DNL Transformation Dataset Include].

Al revisar las descripciones de los parámetros en la siguiente tabla, recuerde lo siguiente:

* La fila de salida es la fila de datos en la que está trabajando la transformación en un momento dado.
* Las filas de entrada son todas las demás filas de datos (antes, después o incluyendo la fila de salida) cuyos valores del campo de entrada sirven como entradas para la transformación.

<table id="table_AB68A89ECD5C45F39B8433F994BBD7D8"> 
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
   <td colname="col2"> Limita el resultado de la transformación a ciertas entradas de registro. Si no se cumple la condición para una entrada de registro determinada, el campo del parámetro Salida de valor de fila de salida se deja sin cambiar. La entrada puede utilizarse para afectar a otras entradas de registro. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Condición de entrada </td> 
   <td colname="col2">Acepta la entrada para la transformación desde solo ciertas filas de entrada. Si la condición <span class="wintitle"> Entrada</span> no se cumple para una fila de entrada determinada, el campo de entrada de esa fila se ignora y no afecta a otras filas de salida. Sin embargo, el campo de salida de esa fila se sigue modificando según la condición especificada. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Entrada de clave de fila de entrada </td> 
   <td colname="col2"> Nombre del campo que se utilizará como clave para las filas de entrada. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Entrada de valor de fila de entrada </td> 
   <td colname="col2"> Nombre del campo de la fila de entrada cuyo valor se copia en el campo del parámetro Salida de valor de fila de salida si se cumplen todas las condiciones. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Operación </td> 
   <td colname="col2"> <p>Operación que, para cada fila de salida, se aplica a todas las filas de entrada que cumplan todas las condiciones definidas por los parámetros <span class="wintitle"> Input</span> Condition y Input Row Key Input para producir una salida: 
     <ul id="ul_16FB152CB558497794DDED72A2F05CDD"> 
      <li id="li_22DA9F814E4E42D0B21E90B63A2A7A0E"> PRIMERO genera el valor del campo en el parámetro Entrada de valor de fila de entrada desde la primera fila de entrada coincidente de los datos (no la primera fila coincidente después de la fila de salida). </li> 
      <li id="li_45E00C3DE0494A1CB5C09B942088F161"> LAST genera el valor del campo en el parámetro Entrada de valor de fila de entrada desde la última fila de entrada de los datos (no la última fila coincidente antes de la fila de salida). </li> 
     </ul> </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Entrada de clave de fila de salida </td> 
   <td colname="col2"> Nombre del campo que se va a utilizar como clave para la fila de salida. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Salida de valor de fila de salida </td> 
   <td colname="col2">Nombre del campo de la fila de salida cuyo valor se copia desde el campo en el parámetro Entrada de valor de fila de entrada si se cumplen todas las condiciones. Todas las filas de salida con los mismos valores de entrada de clave de fila de salida x-trackingid y <span class="wintitle"> </span>tienen el mismo valor de salida de valor de fila de salida <span class="wintitle"></span>. </td> 
   <td colname="col3"> </td> 
  </tr> 
 </tbody> 
</table>

Los parámetros Entrada de clave de fila de entrada, Entrada de valor de fila de entrada y Condición de entrada definen juntos el archivo de búsqueda para cada ID de seguimiento, mientras que los parámetros Entrada de clave de fila de salida, Entrada de valor de fila de salida y Condición controlan lo que se busca en el archivo y qué valor se almacena en el campo especificado por Salida de valor de fila de salida.

Para comprender mejor el funcionamiento de la transformación, considere el siguiente esquema:

* Para cada fila de salida que cumpla la condición y que tenga una entrada de clave de fila de salida no vacía:

   * Busque la fila de entrada PRIMER o ÚLTIMO de forma que

      * la fila de entrada cumple la condición de entrada, y
      * x-trackingid de la fila de entrada es igual a x-trackingid de la fila de salida, y
      * La entrada de la clave de fila de entrada de la fila de entrada es igual a la entrada de la clave de fila de salida de la fila de salida,

* y establezca la Salida del valor de la fila de salida en la Entrada del valor de la fila de entrada.

Consideraciones para [!DNL LookupRows]

* Los valores de las claves en blanco nunca coinciden. Incluso si hay filas de entrada con claves en blanco y valores no vacíos que coinciden con [!DNL Input Condition], un [!DNL Output Row Key Input] de &quot;&quot; siempre producirá un [!DNL Output Row Value Output] de &quot;&quot;.

* Si no está prohibido por el [!DNL Input Condition], una fila puede buscarse si sus valores [!DNL Input Row Key Input] y [!DNL Output Row Key Input] son los mismos.

Si tiene varios valores de clave, puede combinarlos con una transformación [!DNL Format] (consulte [Formato](../../../../../home/c-dataset-const-proc/c-data-trans/c-transf-types/c-standard-transf/c-format.md#concept-3de04869181e4694ab072b092186684b)) antes de aplicar una transformación [!DNL LookupRows].

Supongamos que tiene un sitio web que tiene una página de registro de mascotas, donde se introducen el nombre y la raza, y una página posterior de &quot;comprar juguete&quot; donde solo se usa el nombre de la mascota. Le gustaría poder vincular el nombre de la mascota con la raza de mascotas introducida en la página de registro. Para ello, puede crear la siguiente transformación [!DNL LookupRows]:

![](assets/cfg_TransformationType_LookupRows.png)

Analicemos este ejemplo con el esquema anterior:

* Para cada fila de salida que cumpla con un valor no vacío de cs-uri-query(petname) :

   * Busque la fila de entrada ÚLTIMA de forma que

      * la fila de entrada contiene un valor no vacío de cs-uri-query(petbreed), y
      * x-trackingid de la fila de entrada es igual a x-trackingid de la fila de salida, y
      * el valor de cs-uri-query(petname) de la fila de entrada es igual al valor de cs-uri-query(petname) de la fila de salida,

* y establezca el valor de x-pet-breed de la fila de salida en el valor de cs-uri-query(petbreed) de la fila de entrada.

La transformación [!DNL LookupRows] utiliza el nombre de la mascota (la clave) para asegurarse de que la raza de mascotas esté vinculada tanto al registro de mascotas como a la compra de páginas de juguetes, de modo que pueda analizar los juguetes comprados para cada raza de mascotas, incluso para visitantes con varias mascotas.
