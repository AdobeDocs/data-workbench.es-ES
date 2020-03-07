---
description: Una dimensión denormalizada tiene una relación uno a uno con su dimensión contable principal.
solution: Analytics
title: Dimensiones denormales
topic: Data workbench
uuid: f172fbce-e967-41ce-9958-9062561ecbcc
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Dimensiones denormales{#denormal-dimensions}

Una dimensión denormalizada tiene una relación uno a uno con su dimensión contable principal.

Debe definir una dimensión denormalizada siempre que la dimensión deseada contenga un elemento único para cada elemento de su elemento principal. Por ejemplo, [!DNL EMail Address] es una dimensión denormalizada con un elemento principal de Visitante. Cada visitante tiene una dirección de correo electrónico y cada elemento de la dimensión Dirección de correo electrónico es la dirección de correo electrónico de un único visitante. Aunque dos visitantes tengan la misma dirección de correo electrónico, las direcciones son elementos distintos de la dimensión Dirección de correo electrónico.

Puede utilizar dimensiones denormalizadas en cualquier visualización de tabla, en tablas de detalles o para crear filtros. Además, puede utilizar dimensiones denormalizadas con la funcionalidad de exportación de segmentos del servidor del área de trabajo de datos para exportar valores de campos (como [!DNL Tracking ID] o [!DNL EMail Address]) que tengan muchos valores. Dado que los datos de segmentos que desee exportar deben definirse como una dimensión dentro del perfil, debe crear una dimensión denormalizada que almacene las cadenas sin procesar de los datos del campo.

>[!NOTE]
>
>Cuando se utiliza una dimensión denormalizada en una tabla u otra visualización que espera una dimensión normal, se crea automáticamente una dimensión denormalizada derivada. La dimensión denormalizada derivada tiene una relación uno a varios con la dimensión principal.

Para obtener información sobre la visualización y los filtros de la tabla de detalles, consulte el capítulo Visualizaciones de análisis en la Guía del usuario *del área de trabajo de datos*. Para obtener información sobre la exportación de segmentos, consulte el capítulo Configuración de interfaz y características de análisis en la Guía *del usuario de Área de trabajo de* datos.

>[!NOTE]
>
>Las dimensiones denormalizadas pueden ser muy costosas en tiempo de consulta y espacio en disco. Una dimensión denormalizada con una cadena de entrada principal [!DNL Page View]y una cadena de entrada media de 50 bytes podría agregar 25 GB de datos a los búferes en un conjunto de datos grande típico, equivalente a unas 13 dimensiones de vista de página simples o numéricas, o unas 125 dimensiones de nivel de sesión. Nunca agregue una dimensión denormalizada a un conjunto de datos sin una evaluación cuidadosa del impacto en el rendimiento.

Las dimensiones denormalizadas se definen con los parámetros siguientes:

<table id="table_532AD791E39B4CF296FFA1C33FB8302E"> 
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
   <td colname="col1"> Condición </td> 
   <td colname="col2"> Condiciones en las que se debe crear la relación entre el valor del campo Principal y el valor del campo de entrada. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Oculto </td> 
   <td colname="col2"> Determina si la dimensión aparece en la interfaz del área de trabajo de datos. De forma predeterminada, este parámetro se establece en false. Si, por ejemplo, la dimensión se va a utilizar solo como base de una métrica, puede establecer este parámetro en true para ocultar la dimensión de la visualización del área de trabajo de datos. </td> 
   <td colname="col3"> true </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Entrada </td> 
   <td colname="col2"> Valor relacionado con la dimensión principal (Principal). </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Elementos normalizados </td> 
   <td colname="col2"> Parámetro de ajuste de rendimiento que especifica el número de elementos de dimensión cuyos nombres se almacenarán en la memoria del sistema. Si se establece este parámetro en un valor mayor, una dimensión denormalizada usará más RAM pero resultará en consultas más rápidas. El valor predeterminado es 16383. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Operación </td> 
   <td colname="col2"> <p>Las operaciones disponibles son las siguientes: </p> <p> 
     <ul id="ul_CCDC45838A3941BD949B6D21EA0492B3"> 
      <li id="li_F33898192A82437692B5C15684EFCF64"> PRIMERA NO BLANCA: Se utiliza el primer valor de entrada no en blanco, independientemente de si procede de la primera entrada de registro. Si <span class="wintitle"> Input</span> es un campo vectorial, se utiliza la primera fila del vector para la entrada de registro correspondiente. </li> 
      <li id="li_4ADD0A368BB74B64AD29126C8E7B333F"> PRIMERA FILA: Se utiliza el valor de la primera entrada de registro relacionada con el elemento de dimensión principal, aunque la entrada esté en blanco. Si <span class="wintitle"> Input</span> es un campo vectorial, se utiliza la primera fila del vector para la entrada de registro correspondiente. Si este valor está en blanco o no es un número, o si la entrada de registro pertinente no cumple la condición de la dimensión, no se utiliza ningún valor. </li> 
      <li id="li_C93CA22ADA634F21A6488BB3BEE7CB23"> ÚLTIMO NO EN BLANCO: Se utiliza el último valor de entrada que no está en blanco, independientemente de si procede de la última entrada de registro. Si <span class="wintitle"> Input</span> es un campo vectorial, se utiliza la primera fila del vector para la entrada de registro correspondiente. </li> 
      <li id="li_2FFE585521B14FE5ABBF66AAC47F22C4"> ÚLTIMA FILA: Se utiliza el valor de la última entrada de registro relacionada con el elemento de dimensión principal, aunque la entrada esté en blanco. Si <span class="wintitle"> Input</span> es un campo vectorial, se utiliza la primera fila del vector para la entrada de registro correspondiente. Si este valor está en blanco o no es un número, o si la entrada de registro pertinente no cumple la condición de la dimensión, no se utiliza ningún valor. </li> 
     </ul> </p> <p> <p>Nota:  Si Operación no arroja ningún valor, se utiliza un valor en blanco (""). </p> </p> <p> Debe especificar una operación para asegurarse de que la dimensión se define de la forma prevista. </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Principal </td> 
   <td colname="col2"> Nombre de la dimensión principal. Cualquier dimensión contable puede ser una dimensión principal. </td> 
   <td colname="col3"> </td> 
  </tr> 
 </tbody> 
</table>

La dimensión denormalizada que se muestra en este ejemplo toma todos los datos del campo x-trackingid como entrada e los incluye en una dimensión denominada ID del visitante. Para un segmento de visitantes que haya creado, puede exportar los datos en la dimensión ID del visitante (así como cualquier otra dimensión definida).

![](assets/cfg_Transformation_Dim_Denormal.png)

