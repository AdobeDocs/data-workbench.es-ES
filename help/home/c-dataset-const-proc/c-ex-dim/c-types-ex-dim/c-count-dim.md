---
description: El sistema puede contar los elementos de una dimensión contable.
title: Dimensiones contables
uuid: 3312f5eb-69b9-43af-b32a-5c40e3050b29
exl-id: c607c15d-de85-4daf-af76-79b460f51b38
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '685'
ht-degree: 4%

---

# Dimensiones contables{#countable-dimensions}

El sistema puede contar los elementos de una dimensión contable.

Las dimensiones contables generalmente se utilizan para crear métricas de suma, que devuelven el recuento, o la suma, de todos los elementos de la dimensión. Puede definir dimensiones contables para contar instancias como reservaciones o pedidos de productos. Por ejemplo, puede definir la dimensión contable Pedidos cuyos elementos (entradas de registro correspondientes a pedidos de la tienda en línea) se puedan contar. Si desea mostrar un recuento de pedidos dentro de una visualización, debe definir la métrica de la suma Pedidos , que se puede evaluar sobre una dimensión o que tiene filtros aplicados.

Las dimensiones contables pueden ser principales con respecto a otras dimensiones o secundarias con respecto a otras dimensiones contables.

>[!NOTE]
>
>Si necesita una dimensión que solo proporcione un recuento de algo, debe utilizar una dimensión numérica con una operación de COUNT. Consulte [Dimension numéricos](../../../../home/c-dataset-const-proc/c-ex-dim/c-types-ex-dim/c-num-dim.md#concept-8513b9afaff447c8b334410b565b91ed).

Las dimensiones contables se definen con los siguientes parámetros:

<table id="table_9F3F093F5B074EA68CA4DCE731161F6C"> 
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
   <td colname="col2"> Nombre descriptivo de la dimensión tal como aparece al usuario en Data Workbench. El nombre de la dimensión no puede incluir un guión (-). </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Comentarios </td> 
   <td colname="col2"> Opcional. Notas sobre la dimensión extendida. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Condición </td> 
   <td colname="col2"> Condiciones en las que el campo de entrada contribuye a la creación de la dimensión contable. Si se especifica, una condición restringe el conjunto de entradas de registro visibles para la dimensión y todos sus elementos secundarios en el esquema del conjunto de datos. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Oculto </td> 
   <td colname="col2"> Determina si la dimensión aparece en la interfaz de Data Workbench. De forma predeterminada, este parámetro se establece en false. Si, por ejemplo, la dimensión se va a utilizar solo como base de una métrica, puede establecer este parámetro en true para ocultar la dimensión de la visualización del Data Workbench. </td> 
   <td colname="col3"> false </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Clave </td> 
   <td colname="col2"> <p>Opcional. Nombre del campo que se va a utilizar como clave. Si define este parámetro, existe un elemento de la dimensión contable para cada combinación de un elemento del elemento principal de la dimensión contable y un valor distinto del campo especificado como clave. </p> <p> Cada elemento de la dimensión contable es necesario para relacionarse con un conjunto contiguo de entradas de registro. Por lo tanto, si las entradas de registro no están ordenadas por la clave, se crea un elemento de la dimensión contable cada vez que cambia el campo clave. Para evitar esta situación, Adobe recomienda utilizar una clave única que sea contigua en el orden de tiempo. </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Principal </td> 
   <td colname="col2"> <p>Nombre de la dimensión principal. Cualquier dimensión contable puede ser una dimensión principal. Para que una dimensión sea la dimensión de nivel superior en el esquema del conjunto de datos, establezca el parámetro en "raíz". La dimensión definida se convierte en la dimensión contable raíz para el conjunto de datos. Por ejemplo, si está trabajando con el Sitio, la dimensión Visitante es la dimensión contable raíz del conjunto de datos. </p> <p> <p>Nota:  Aunque la dimensión contable raíz no tiene que estar asociada con los ID de seguimiento en los datos, Adobe recomienda configurar la dimensión contable raíz del conjunto de datos para que utilice el campo de ID de seguimiento (x-trackingid) como su Clave. Como resultado, cada elemento de la tabla raíz está asociado con un valor único de x-trackingid, y todos los datos de cada elemento se agrupan. Si desea configurar el conjunto de datos de forma diferente, póngase en contacto con el Adobe. </p> </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
 </tbody> 
</table>

Este ejemplo ilustra la definición de una dimensión contable mediante los datos de evento recopilados a partir del tráfico del sitio web. La dimensión contable cuenta los eventos de campaña web dentro de una sesión determinada. Se supone que todos los recursos de campaña de correo electrónico se solicitan desde el servidor web con &quot;email=&quot; como parte de cs-uri-query. En el ejemplo, el número de veces que el visitante responde a una campaña de correo electrónico durante una sesión determinada es de interés, no el valor real del campo cs-uri-query(email) .

![](assets/cfg_Transformation_Dim_Countable.png)

Este ejemplo también ilustra la definición de una dimensión contable mediante los datos de evento recopilados del tráfico del sitio web, pero tiene un parámetro de clave definido. La dimensión Session count utiliza el campo x-session-key como clave. (El campo x-session-key es el resultado de la transformación [!DNL Sessionize] y tiene un valor único para cada sesión). Cada combinación única de un elemento de la dimensión Visitante (el principal) y el campo x-session-key es un elemento de la dimensión Sesión .

![](assets/cfg_Transformation_Dim_Countable2.png)
