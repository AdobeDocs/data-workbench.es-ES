---
description: La transformación REMatch es una transformación de coincidencia de patrones que utiliza expresiones regulares para especificar uno o más patrones que se van a buscar y capturar en la entrada.
solution: Analytics
title: REMatch
topic: Data workbench
uuid: 8ef80bfa-aea2-45a1-a7d9-38ad33043886
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# REMatch{#rematch}

La transformación REMatch es una transformación de coincidencia de patrones que utiliza expresiones regulares para especificar uno o más patrones que se van a buscar y capturar en la entrada.

La transformación construye un campo de salida para cada subpatrón de captura en la expresión regular. Si la expresión regular no coincide con el campo de entrada, las salidas están en blanco y, si el campo de salida ya existe, los valores se sustituyen por los valores en blanco. Para obtener una breve guía sobre el uso de expresiones regulares, consulte Expresiones [regulares](../../../../../home/c-dataset-const-proc/c-reg-exp.md#concept-070077baa419475094ef0469e92c5b9c).

>[!NOTE]
>
>La [!DNL REMatch] transformación funciona de forma similar a la [!DNL RETransform] transformación (consulte [RETransform](../../../../../home/c-dataset-const-proc/c-data-trans/c-transf-types/c-standard-transf/c-retransform.md#concept-23f80aa0bc204565b337e5c4931f6a74)), que utiliza expresiones regulares para capturar una cadena y almacena dicha cadena en un único campo de salida.

[!DNL REMatch] analiza una cadena de forma más eficaz que varias [!DNL RETransform] transformaciones o una sola [!DNL RETransform] transformación seguida de una [!DNL Flatten] transformación. Consulte [Acoplar](../../../../../home/c-dataset-const-proc/c-data-trans/c-transf-types/c-standard-transf/c-flatten.md#concept-7acd351a6d2444bd960ca412ae3333ce).

<table id="table_7077578512B249E986BC79AE770CBD9A"> 
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
   <td colname="col3"></td> 
  </tr> 
  <tr> 
   <td colname="col1"> Distinción entre mayúsculas y minúsculas </td> 
   <td colname="col2"> True o false. Especifica si la coincidencia distingue entre mayúsculas y minúsculas. </td> 
   <td colname="col3"></td> 
  </tr> 
  <tr> 
   <td colname="col1"> Comentarios </td> 
   <td colname="col2"> Opcional. Notas sobre la transformación. </td> 
   <td colname="col3"></td> 
  </tr> 
  <tr> 
   <td colname="col1"> Condición </td> 
   <td colname="col2"> Condiciones en las que se aplica esta transformación. </td> 
   <td colname="col3"></td> 
  </tr> 
  <tr> 
   <td colname="col1"> Expresión </td> 
   <td colname="col2"> Expresión regular utilizada para la coincidencia. </td> 
   <td colname="col3"></td> 
  </tr> 
  <tr> 
   <td colname="col1"> Entrada </td> 
   <td colname="col2"> Campo con el que se evalúa la expresión regular. </td> 
   <td colname="col3"></td> 
  </tr> 
  <tr> 
   <td colname="col1"> Salidas </td> 
   <td colname="col2"> <p>Nombre de la cadena de salida o del vector. En el caso de los vectores de cadena como entrada, las salidas también son vectores de cadena. </p> <p> Debe existir un campo de salida para cada subpatrón de captura en la expresión. </p> </td> 
   <td colname="col3"></td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>[!DNL REMatch] las transformaciones pueden ser muy lentas y representar gran parte del tiempo de procesamiento de los datos.

En este ejemplo, una [!DNL REMatch] transformación analiza una fecha con el formato AAAA-MM-DD en los campos x-año, x-mes y x-día. Para la fecha 2007-01-02, los valores de x-año, x-mes y x-día serían 2007, 01 y 02, respectivamente.

![](assets/cfg_TransformationType_REMatch.png)
