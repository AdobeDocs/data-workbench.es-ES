---
description: La transformación RETransform (expresión regular) es una transformación que coincide con patrones que utiliza expresiones regulares para especificar un patrón que se debe buscar y capturar en la entrada y almacena la cadena capturada en un campo de salida designado.
solution: Analytics
title: RETransform
topic: Data workbench
uuid: 60b5b60e-678a-416d-b5c3-57b1bbefce7d
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# RETransform{#retransform}

La transformación RETransform (expresión regular) es una transformación que coincide con patrones que utiliza expresiones regulares para especificar un patrón que se debe buscar y capturar en la entrada y almacena la cadena capturada en un campo de salida designado.

Las expresiones regulares se evalúan con toda la cadena de entrada. Si la entrada no coincide con el patrón especificado en la expresión regular, no se capturan datos. Para obtener una breve guía sobre el uso de expresiones regulares, consulte Expresiones [regulares](../../../../../home/c-dataset-const-proc/c-reg-exp.md#concept-070077baa419475094ef0469e92c5b9c).

>[!NOTE]
>
>La [!DNL RETransform] transformación funciona de manera similar a la [!DNL REMatch] transformación (consulte [REMatch](../../../../../home/c-dataset-const-proc/c-data-trans/c-transf-types/c-standard-transf/c-rematch.md#concept-7f0b1caad1df46aabef4448f88261a8e)), que construye un campo de salida para cada subpatrón de captura en la expresión regular. Se puede pensar en [!DNL RETransform] como una combinación de [!DNL REMatch] y [!DNL Format] transformaciones. Si el parámetro Action (consulte Acción en la siguiente tabla) está establecido en &quot;RESULTADOS&quot;, entonces [!DNL RETransform] funciona como una combinación de [!DNL REMatch] y [!DNL Union] transformaciones.

<table id="table_51B7342E6A5E4E31913BD0F6A6ACC424"> 
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
   <td colname="col1"> Valor predeterminado </td> 
   <td colname="col2"> El valor predeterminado que se usará si se cumple la condición y el valor de entrada no está disponible o la expresión regular no coincide con el valor de entrada. </td> 
   <td colname="col3"></td> 
  </tr> 
  <tr> 
   <td colname="col1"> Acción </td> 
   <td colname="col2"> <p>Especifica cómo se trata el resultado. La configuración predeterminada de RESULTS simplemente toma los patrones coincidentes y crea un vector de cadenas a partir de los patrones que se extraen. </p> <p> De forma alternativa, la acción puede ser una cadena de formato para crear una salida de cadena simple con un formato concreto. Con esta técnica, se especifica el número correspondiente a la ubicación de cada patrón coincidente entre signos de %. Por ejemplo, el primer patrón coincidente sería %1% y el tercer patrón coincidente sería %3%. Podría especificar otros caracteres literalmente en la cadena de formato. </p> </td> 
   <td colname="col3"> RESULTADOS </td> 
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
   <td colname="col1"> Salida </td> 
   <td colname="col2"> Nombre de la cadena de salida. </td> 
   <td colname="col3"></td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>[!DNL RETransform] las transformaciones pueden ser muy lentas y representar gran parte del tiempo de procesamiento de los datos.

Este ejemplo aísla la versión del sistema operativo Windows que utiliza un visitante de un sitio web y crea un campo x-windows-version a partir de ese valor. El valor de salida en este caso sería simplemente el número de versión.

![](assets/cfg_TransformationType_RegularExpression.png)

Si desea incluir la cadena &quot;Versión&quot; delante del número de versión para que sea legible, debe cambiar el parámetro Acción de &quot;RESULTADOS&quot; a &quot;Versión %1%&quot;. Para incluir un signo de porcentaje literal (%) en la salida, escape con un signo de segundo porcentaje, como en &quot;%%&quot;.
