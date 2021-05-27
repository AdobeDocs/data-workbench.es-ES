---
description: Si trabaja con datos web, puede utilizar la transformación ExtractValue para extraer un valor de una cadena de consulta, cookie o campo codificado de forma similar en los datos del sitio web.
title: ExtractValue
uuid: 305827a2-04e6-421f-82cb-923d62b02e70
exl-id: 5bafe64f-081a-49ec-997e-68e8f6915a71
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '235'
ht-degree: 3%

---

# ExtractValue{#extractvalue}

Si trabaja con datos web, puede utilizar la transformación ExtractValue para extraer un valor de una cadena de consulta, cookie o campo codificado de forma similar en los datos del sitio web.

Tenga en cuenta que los nombres correspondientes al valor que se va a extraer pueden ser diferentes en cada entrada de registro.

<table id="table_D16A39BE035043628A4D6F7452952304"> 
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
   <td colname="col2"> <p>Los nombres de los campos que se extraerán de la consulta de entrada. </p> <p> <p>Nota:  Si el Nombre de entrada es un vector (es decir, hay varios nombres presentes), solo se extrae un valor. </p> </p> </td> 
   <td colname="col3"></td> 
  </tr> 
  <tr> 
   <td colname="col1"> Consulta de entrada </td> 
   <td colname="col2"> La asignación codificada (cadena de consulta, cookie, etc.) desde la que se extraerá el valor. </td> 
   <td colname="col3"></td> 
  </tr> 
  <tr> 
   <td colname="col1"> Valor de salida </td> 
   <td colname="col2"> Nombre del campo utilizado para capturar el valor descodificado extraído. </td> 
   <td colname="col3"></td> 
  </tr> 
 </tbody> 
</table>

Si desea extraer una frase de búsqueda, puede extraer la frase completa y, si lo desea, dividirla en términos de búsqueda mediante una transformación [!DNL Tokenize]. Para obtener información sobre la transformación [!DNL Tokenize], consulte [Tokenize](../../../../../home/c-dataset-const-proc/c-data-trans/c-transf-types/c-standard-transf/c-tokenize.md#concept-f460aa5df3a7476e971af29cf5d9b32c).

En este ejemplo se configura una transformación [!DNL ExtractValue] para extraer valores del campo x-v-search-querynames de cs(referrer-query) y almacenarlos en el campo x-search-rase-rase.

![](assets/cfg_TransformationType_ExtractValue.png)
