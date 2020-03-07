---
description: Si está trabajando con datos web, puede utilizar la transformación ExtractValue para extraer un valor de una cadena de consulta, cookie o campo codificado de forma similar en los datos del sitio web.
solution: Analytics
title: ExtractValue
topic: Data workbench
uuid: 305827a2-04e6-421f-82cb-923d62b02e70
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# ExtractValue{#extractvalue}

Si está trabajando con datos web, puede utilizar la transformación ExtractValue para extraer un valor de una cadena de consulta, cookie o campo codificado de forma similar en los datos del sitio web.

Tenga en cuenta que los nombres correspondientes al valor que se va a extraer pueden ser diferentes en cada entrada de registro.

<table id="table_D16A39BE035043628A4D6F7452952304"> 
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
   <td colname="col1"> Nombre de entrada </td> 
   <td colname="col2"> <p>Los nombres de los campos que se van a extraer de la consulta de entrada. </p> <p> <p>Nota:  Si el Nombre de entrada es un vector (es decir, hay varios nombres presentes), solo se extrae un valor. </p> </p> </td> 
   <td colname="col3"></td> 
  </tr> 
  <tr> 
   <td colname="col1"> Consulta de entrada </td> 
   <td colname="col2"> Asignación codificada (cadena de consulta, cookie, etc.) desde la que se extrae el valor. </td> 
   <td colname="col3"></td> 
  </tr> 
  <tr> 
   <td colname="col1"> Valor de salida </td> 
   <td colname="col2"> Nombre del campo utilizado para capturar el valor descodificado extraído. </td> 
   <td colname="col3"></td> 
  </tr> 
 </tbody> 
</table>

Si desea extraer una frase de búsqueda, puede extraer toda la frase y, si lo desea, dividirla en términos de búsqueda mediante una [!DNL Tokenize] transformación. Para obtener información sobre la [!DNL Tokenize] transformación, consulte [Tokenize](../../../../../home/c-dataset-const-proc/c-data-trans/c-transf-types/c-standard-transf/c-tokenize.md#concept-f460aa5df3a7476e971af29cf5d9b32c).

En este ejemplo se configura una [!DNL ExtractValue] transformación para extraer los valores del campo x-v-search-querynames de cs(referrer-query) y almacenarlos en el campo x-search-phrase.

![](assets/cfg_TransformationType_ExtractValue.png)

