---
description: Si trabaja con datos recopilados sobre el tráfico de sitios web, puede utilizar la transformación Sessionize para determinar cómo se definen las sesiones.
title: Sessionize
uuid: c6e2487a-80e5-4e00-b4d4-2ce013fac3ea
exl-id: bb25cb4b-7185-4524-8ff5-740b672e1cd9
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '773'
ht-degree: 1%

---

# Sessionize{#sessionize}

Si trabaja con datos recopilados sobre el tráfico de sitios web, puede utilizar la transformación Sessionize para determinar cómo se definen las sesiones.

La transformación toma como entrada una marca de tiempo y un ID de seguimiento y genera un número de sesión para cada entrada de registro. El número de sesión es &quot;1&quot; para la primera sesión con un ID de seguimiento determinado, &quot;2&quot; para la segunda sesión con el mismo ID de seguimiento, etc. El resultado se puede utilizar directamente como clave de sesión porque tiene un valor único para cada sesión.

>[!NOTE]
>
>Para que funcione, la transformación [!DNL Sessionize] requiere que los datos se ordenen a tiempo y se agrupen por el ID de seguimiento en los datos de origen. Por lo tanto, [!DNL Sessionize] solo funciona cuando se define en el archivo [!DNL Transformation.cfg] o en un archivo [!DNL Transformation Dataset Include].

<table id="table_34984DF9340149C0A5016F08EABAD158"> 
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
   <td colname="col2"> Condiciones en las que se aplica esta transformación. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Marca de tiempo de entrada </td> 
   <td colname="col2"> Campo que contiene los valores de la marca de tiempo que se van a utilizar. </td> 
   <td colname="col3"> x-timestamp </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ID de seguimiento de entrada </td> 
   <td colname="col2"> <p>El campo que contiene los valores del ID de seguimiento que se van a utilizar. El valor debe ser un número hexadecimal de 64 bits (16 dígitos) o menor o un número decimal entero de 16 dígitos o menos. </p> <p> <p>Nota: Si desea utilizar un campo que no sea x-trackingid para el ID de seguimiento, primero debe hash para el campo . Consulte <a href="../../../../../home/c-dataset-const-proc/c-data-trans/c-transf-types/c-standard-transf/c-hash.md#concept-9c353923264941c3aea4428fed66d369"> Hash</a>. </p> </p> </td> 
   <td colname="col3"> x-trackingid </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Duración máxima de la sesión </p> </td> 
   <td colname="col2">La duración más larga de la sesión antes de que se inicie una nueva sesión. (Esto evita que las páginas web con contenido automático se actualicen desde la creación de sesiones que son arbitrariamente largas). Si se cumple la <span class="wintitle"> condición de tiempo de espera</span> y el referente de un clic se establece en una de las entradas del parámetro Dominios internos, se utiliza la duración máxima de sesión para definir el final de una sesión. Ninguna sesión puede ser superior a la duración máxima de sesión especificada independientemente de la cantidad de clics que contenga. El valor recomendado es de 48 horas. Para obtener más información sobre los parámetros de Duración máxima de sesión y Dominios internos, consulte <a href="../../../../../home/c-dataset-const-proc/c-config-web-data/c-config-web-data.md#concept-9a306b65483a484bb3f6f3c1d7e77519"> Configuración de datos web</a>. </td> 
   <td colname="col3"> 48 horas </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Número de sesión de salida </td> 
   <td colname="col2"> Campo en el que se almacena el número de sesión. Este campo tiene un valor único para cada sesión de cada visitante. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Tiempo de espera de la sesión </td> 
   <td colname="col2"> <p>Cantidad de tiempo que debe transcurrir entre las entradas de registro de un visitante determinado para determinar el final de una sesión y el inicio de una nueva (es decir, el tiempo de espera habitual que se utiliza para definir una sesión de usuario). El valor recomendado de este parámetro es de 30 minutos. Si no se cumple la condición de tiempo de espera y el referente de un clic no está establecido en uno de los referentes del parámetro Dominios internos , se utiliza el tiempo de espera de sesión para definir la sesión. </p> <p> Si se cumple la condición de tiempo de espera y cs(dominio de referente) para una entrada de registro está en la lista de dominios internos, la duración máxima de la sesión determina si la entrada de registro actual es parte de una sesión existente o el inicio de una nueva sesión. </p> <p> Para obtener más información sobre el parámetro Tiempo de espera de sesión, consulte <a href="../../../../../home/c-dataset-const-proc/c-config-web-data/c-config-web-data.md#concept-9a306b65483a484bb3f6f3c1d7e77519"> Configuración de datos web</a>. </p> </td> 
   <td colname="col3"> 30 minutos </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Condición de tiempo de espera </td> 
   <td colname="col2"> Condición que debe cumplirse para que una entrada de registro se considere el inicio de una nueva sesión. Tenga en cuenta que la cantidad de tiempo que transcurre entre la entrada de registro y la entrada de registro anterior debe ser al menos el valor del parámetro Tiempo de espera de sesión . </td> 
   <td colname="col3"> </td> 
  </tr> 
 </tbody> 
</table>

Una nueva sesión comienza cuando se produce cualquiera de las siguientes situaciones:

* El ID de seguimiento cambia.
* El tiempo desde la última entrada de registro es al menos igual al valor del parámetro Tiempo de espera de sesión y se cumple la condición Tiempo de espera.
* El tiempo desde la primera entrada de registro de la última sesión supera el valor del parámetro Maximum Session Duration .

>[!NOTE]
>
>Si ya ha definido Duración máxima de sesión y Tiempo de espera de sesión como parámetros en el archivo [!DNL Session Parameters.cfg], no introduzca valores para ellos en la configuración. Puede hacer referencia a los parámetros escribiendo *$(nombre del parámetro)* como se muestra en el siguiente ejemplo. Para obtener más información sobre estos parámetros, consulte [Configuración de datos web](../../../../../home/c-dataset-const-proc/c-config-web-data/c-config-web-data.md#concept-9a306b65483a484bb3f6f3c1d7e77519).

La transformación [!DNL Sessionize] de este ejemplo toma como entrada los campos x-timestamp y x-trackingid y registra el número de sesión de cada entrada de registro en el campo x-session-key . El [!DNL Timeout Condition] de la transformación se basa en una condición [!DNL Neither]: Si el campo cs(referrer-domain) de una entrada de registro coincide con un miembro del parámetro Internal Domains , la condición se evalúa como false. Tenga en cuenta las referencias a los parámetros Dominios internos y Tiempo de espera de sesión .

Para obtener más información sobre [!DNL NeitherCondition], consulte [Condiciones](../../../../../home/c-dataset-const-proc/c-conditions/c-abt-cond.md). Para obtener información sobre los dominios internos y los parámetros de tiempo de espera de sesión, consulte [Configuración de los datos web](../../../../../home/c-dataset-const-proc/c-config-web-data/c-config-web-data.md#concept-9a306b65483a484bb3f6f3c1d7e77519).

![](assets/cfg_TransformationType_Sessionize.png)
