---
description: La transformación Dividir divide una cadena en un vector de subcadenas basado en un carácter delimitador determinado.
solution: Analytics
title: Dividir
topic: Data workbench
uuid: 116e8465-8fb1-41eb-9a28-412cee54ab87
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Split{#split}

La transformación Dividir divide una cadena en un vector de subcadenas basado en un carácter delimitador determinado.

[!DNL Split] resulta especialmente útil para extraer valores individuales de una colección de valores asociados a un único valor de nombre de consulta URI.

<table id="table_C97DA4E45DA844FAB8D61AABA22FF809"> 
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
   <td colname="col2"> Nombre descriptivo de la transformación. Aquí puede introducir cualquier nombre. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Comentarios </td> 
   <td colname="col2"> Opcional. Notas sobre la transformación. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Condición </td> 
   <td colname="col2"> Condiciones en las que se aplica esta transformación. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Delimitador </td> 
   <td colname="col2"> <p>Cadena que se utiliza para separar la cadena de entrada en subcadenas. Debe tener un solo carácter de longitud. </p> <p> Si mantiene pulsada la tecla Ctrl y hace clic con el botón derecho en el parámetro Delimitador, aparecerá un menú Insertar. Este menú contiene una lista de caracteres especiales que a menudo se utilizan como delimitadores. </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Entrada </td> 
   <td colname="col2"> Nombre del campo cuyo valor se divide para crear el vector de cadena de salida. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Salida </td> 
   <td colname="col2"> Nombre del campo de salida. </td> 
   <td colname="col3"> </td> 
  </tr> 
 </tbody> 
</table>

Considere un sitio web en el que los productos comprados por un cliente se incluyen como parte del valor cs-uri-query cuando se accede a la página de confirmación asociada con una compra correcta. El siguiente es un ejemplo de una cadena de este tipo:

* /checkout/confirmed.asp?prod_selected=B57481,C46355,Z97123

El campo cs-uri-stem se utiliza para determinar si la página solicitada por la entrada de registro es la página de confirmación. Los códigos de los productos que compró el cliente se enumeran como valores separados por comas del nombre prod_selected en la consulta cs-uri. La [!DNL Split] transformación puede utilizarse para extraer esta información dividiendo los códigos de producto en la coma si el valor de cs-uri-stem coincide con el valor especificado en la [!DNL String Match] condición. Consulte Coincidencia [de cadena](../../../../../home/c-dataset-const-proc/c-conditions/c-test-ops/c-test-op-con.md#section-f8d132085c6b4500bfbe4515b848142f). La siguiente transformación detalla la solución a este problema.

![](assets/cfg_TransformationType_Split.png)

Aquí, el campo de salida es x-products, que se utilizaría para crear la dimensión extendida deseada que asigna los productos comprados a las sesiones durante las cuales se realizó la compra.
