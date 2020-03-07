---
description: Si está trabajando con datos recopilados a partir del tráfico del sitio web, puede utilizar la transformación Sesión para determinar cómo se definen las sesiones.
solution: Analytics
title: Sesionize
topic: Data workbench
uuid: c6e2487a-80e5-4e00-b4d4-2ce013fac3ea
translation-type: tm+mt
source-git-commit: 27600561841db3705f4eee6ff0aeb8890444bbc9

---


# Sesionize{#sessionize}

Si está trabajando con datos recopilados a partir del tráfico del sitio web, puede utilizar la transformación Sesión para determinar cómo se definen las sesiones.

La transformación toma como entrada una marca de tiempo y un ID de seguimiento y genera un número de sesión para cada entrada de registro. El número de sesión es &quot;1&quot; para la primera sesión con un ID de seguimiento determinado, &quot;2&quot; para la segunda sesión con el mismo ID de seguimiento, etc. El resultado se puede utilizar directamente como clave de sesión porque tiene un valor único para cada sesión.

>[!NOTE]
>
>Para que funcione, la [!DNL Sessionize] transformación requiere que los datos se ordenen a tiempo y se agrupen por la ID de seguimiento en los datos de origen. Por lo tanto, [!DNL Sessionize] solo funciona cuando se define en el [!DNL Transformation.cfg] archivo o en un [!DNL Transformation Dataset Include] archivo.

<table id="table_34984DF9340149C0A5016F08EABAD158"> 
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
   <td colname="col1"> Marca de hora de entrada </td> 
   <td colname="col2"> Campo que contiene los valores de la marca de tiempo que se va a utilizar. </td> 
   <td colname="col3"> x-timestamp </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ID de seguimiento de entrada </td> 
   <td colname="col2"> <p>Campo que contiene los valores de la ID de seguimiento que se va a utilizar. El valor debe ser un número hexadecimal de 64 bits (16 dígitos) o menor, o un número decimal de 16 dígitos o menos. </p> <p> <p>Nota: Si desea utilizar un campo que no sea x-trackingid para la ID de seguimiento, primero debe hash en el campo. Consulte <a href="../../../../../home/c-dataset-const-proc/c-data-trans/c-transf-types/c-standard-transf/c-hash.md#concept-9c353923264941c3aea4428fed66d369"> Hash</a>. </p> </p> </td> 
   <td colname="col3"> x-trackingid </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Duración máxima de la sesión </p> </td> 
   <td colname="col2">Duración más larga de la sesión antes de que se inicie una nueva. (Esto evita que las páginas web con contenido automático se actualicen a partir de la creación de sesiones que son arbitrariamente largas). Si se cumple la condición <span class="wintitle"></span> de tiempo de espera y el referente de un clic se establece en una de las entradas del parámetro Dominios internos, se utiliza la duración máxima de sesión para definir el final de una sesión. Ninguna sesión puede ser mayor que la duración máxima de sesión especificada, independientemente de cuántos clics contenga. El valor recomendado es de 48 horas. Para obtener más información sobre los parámetros Duración máxima de sesión y Dominios internos, consulte Configuración de configuración para datos <a href="../../../../../home/c-dataset-const-proc/c-config-web-data/c-config-web-data.md#concept-9a306b65483a484bb3f6f3c1d7e77519"></a>web. </td> 
   <td colname="col3"> 48 horas </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Número de sesión de salida </td> 
   <td colname="col2"> Campo en el que se almacena el número de sesión. Este campo tiene un valor único para cada sesión de cada visitante. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Tiempo de espera de la sesión </td> 
   <td colname="col2"> <p>Cantidad de tiempo que debe transcurrir entre las entradas de registro de un visitante determinado para determinar el final de una sesión y el inicio de una nueva (es decir, el tiempo de espera habitual que se utiliza para definir una sesión de usuario). El valor recomendado de este parámetro es de 30 minutos. Si no se cumple la condición de tiempo de espera y el referente de un clic no está establecido en uno de los referentes del parámetro Dominios internos, se utiliza Tiempo de espera de sesión para definir la sesión. </p> <p> Si se cumple la condición de tiempo de espera y cs(dominio-referente) para una entrada de registro está en la lista de dominios internos, la duración máxima de sesión determina si la entrada de registro actual es parte de una sesión existente o el inicio de una nueva sesión. </p> <p> Para obtener más información sobre el parámetro Tiempo de espera de sesión, consulte Configuración de configuración para datos <a href="../../../../../home/c-dataset-const-proc/c-config-web-data/c-config-web-data.md#concept-9a306b65483a484bb3f6f3c1d7e77519"></a>web. </p> </td> 
   <td colname="col3"> 30 minutos </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Condición de tiempo de espera </td> 
   <td colname="col2"> Condición que debe cumplirse para que una entrada de registro se considere el inicio de una nueva sesión. Tenga en cuenta que la cantidad de tiempo que transcurre entre la entrada de registro y la entrada de registro anterior debe ser al menos el valor del parámetro Tiempo de espera de sesión. </td> 
   <td colname="col3"> </td> 
  </tr> 
 </tbody> 
</table>

Una nueva sesión comienza cuando se produce cualquiera de las situaciones siguientes:

* El ID de seguimiento cambia.
* El tiempo transcurrido desde la última entrada de registro es al menos igual al valor del parámetro Tiempo de espera de sesión y se cumple la condición de tiempo de espera.
* El tiempo transcurrido desde la primera entrada de registro de la última sesión supera el valor del parámetro de duración máxima de sesión.

>[!NOTE]
>
>Si ya ha definido Duración máxima de sesión y Tiempo de espera de sesión como parámetros en el [!DNL Session Parameters.cfg] archivo, no introduzca valores para ellos en la configuración. Puede hacer referencia a los parámetros escribiendo *$(nombre del parámetro)* como se muestra en el siguiente ejemplo. Para obtener más información sobre estos parámetros, consulte Configuración [de configuración para datos](../../../../../home/c-dataset-const-proc/c-config-web-data/c-config-web-data.md#concept-9a306b65483a484bb3f6f3c1d7e77519)web.

La [!DNL Sessionize] transformación de este ejemplo toma como entrada los campos x-timestamp y x-trackingid y registra el número de sesión para cada entrada de registro en el campo x-session-key. La transformación [!DNL Timeout Condition] se basa en una [!DNL Neither] condición: Si el campo cs(referrer-domain) de una entrada de registro coincide con un miembro del parámetro Dominios internos, la condición se evalúa como false. Observe las referencias a los parámetros Dominios internos y Tiempo de espera de sesión.

Para obtener más información sobre el [!DNL NeitherCondition], consulte [Condiciones](../../../../../home/c-dataset-const-proc/c-conditions/c-abt-cond.md). Para obtener información sobre los parámetros Dominios internos y Tiempo de espera de sesión, consulte Configuración [de configuración para datos](../../../../../home/c-dataset-const-proc/c-config-web-data/c-config-web-data.md#concept-9a306b65483a484bb3f6f3c1d7e77519)web.

![](assets/cfg_TransformationType_Sessionize.png)

