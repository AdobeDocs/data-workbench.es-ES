---
description: Explicación de los contadores en el área de trabajo de datos (DWB) para diseñar e implementar el esquema.
title: Estructuras contables de diseño de Esquema
uuid: 2530980d-1c6b-4a96-b9c1-431fc75678bb
translation-type: tm+mt
source-git-commit: 8b0e9c8855a7c7228393dfab4bf78645f1953794

---


# Estructuras contables de diseño de Esquema{#schema-design-countable-structures}

Explicación de los contadores en el área de trabajo de datos (DWB) para diseñar e implementar el esquema.

## Explicación de los contadores en el área de trabajo de datos {#section-6e6b8d1c17634d669e62c91a80a0bc62}

En el nivel más alto hay un recuento de las dimensiones. Las dimensiones contables cumplen dos funciones principales. En primer lugar, son dimensiones cuyos elementos desea contar. En otras palabras, los contadores responden a preguntas como:

* ¿Cuántos visitantes visitaron la página principal?

* ¿Cuántas visitas provienen de Google.com?

`<discoiqbr>`Las dimensiones contables generalmente se utilizan para crear métricas de suma que devuelven el recuento, o suma, de todos los elementos de la dimensión. Puede definir dimensiones contables para contar instancias como reservaciones o pedidos de productos. Por ejemplo, puede definir los pedidos de dimensión contables cuyos elementos (entradas de registro correspondientes a pedidos de la tienda en línea) se pueden contar. Si desea mostrar un recuento de pedidos dentro de una visualización, debe definir la métrica de la suma de pedidos, que se puede evaluar a lo largo de una dimensión o que tiene filtros aplicados.

Las dimensiones contables pueden ser principales con respecto a otras dimensiones o secundarias con respecto a otras dimensiones contables.

Aunque la dimensión contable raíz no tiene que estar asociada con los ID de seguimiento de los datos, Adobe recomienda configurar la dimensión contable raíz del conjunto de datos para utilizar el campo de ID de seguimiento (x-trackingid) como Clave. Como resultado, cada elemento de la tabla raíz está asociado con un valor único de x-trackingid, y todos los datos de cada elemento se agrupan juntos.

Las dimensiones contables se definen mediante los siguientes parámetros:

<table id="table_5E00B72CFDD645368ADCC25AB9B5E53D"> 
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
   <td colname="col2"> Nombre descriptivo de la dimensión tal como aparece el usuario en el área de trabajo de datos. El nombre de la dimensión no puede incluir un guión (-). </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Comentarios </p> </td> 
   <td colname="col2"> <p>Opcional. Notas sobre la dimensión extendida.

    &lt;/p> &lt;/td>
<td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Condición </p> </td> 
   <td colname="col2"> <p>Condiciones en las que el campo de entrada contribuye a la creación de la dimensión contable. Si se especifica, una condición restringe el conjunto de entradas de registro visibles para la dimensión y todos sus elementos secundarios en el esquema del conjunto de datos. </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Oculto </td> 
   <td colname="col2"> Determina si la dimensión aparece en la interfaz del área de trabajo de datos. De forma predeterminada, este parámetro se establece en false. Si, por ejemplo, la dimensión se va a utilizar solo como base de una métrica, puede establecer este parámetro en true para ocultar la dimensión de la visualización del área de trabajo de datos. </td> 
   <td colname="col3"> false </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Clave </td> 
   <td colname="col2"> <p>Opcional. Nombre del campo que se va a utilizar como clave. Si define este parámetro, existe un elemento de la dimensión contable para cada combinación de un elemento del elemento principal de la dimensión contable y un valor definido del campo especificado como clave. </p> <p>Cada elemento de la dimensión contable es necesario para relacionarse con un conjunto contiguo de entradas de registro. Por lo tanto, si la clave no ordena las entradas de registro, se crea un elemento de la dimensión contable cada vez que cambia el campo clave. Para evitar esta situación, Adobe recomienda utilizar una clave única que sea contigua en el orden de tiempo. </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Principal </td> 
   <td colname="col2"> <p> Nombre de la dimensión principal. Cualquier dimensión contable puede ser una dimensión principal. Para que una dimensión sea la dimensión de nivel superior en el esquema del conjunto de datos, establezca el parámetro en "root". La dimensión definida se convierte en la dimensión contable raíz del conjunto de datos. Por ejemplo: si trabaja con el sitio, la dimensión de Visitante es la dimensión contable raíz del conjunto de datos. </p> <p>Nota: Aunque la dimensión contable raíz no tiene que estar asociada con los ID de seguimiento de los datos, Adobe recomienda configurar la dimensión contable raíz del conjunto de datos para utilizar el campo de ID de seguimiento (x-trackingid) como su Clave. Como resultado, cada elemento de la tabla raíz está asociado con un valor único de x-trackingid, y todos los datos de cada elemento se agrupan juntos. Si desea configurar el conjunto de datos de forma diferente, póngase en contacto con Adobe. </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
 </tbody> 
</table>

Este ejemplo ilustra la definición de una dimensión contable mediante los datos de evento recopilados a partir del tráfico del sitio web. La dimensión contable cuenta los eventos de campaña web dentro de una sesión determinada. Se supone que todos los recursos de campaña de correo electrónico se solicitan desde el servidor web con &quot;email=&quot; como parte de la consulta cs-uri. En el ejemplo, el número de veces que el visitante responde a una campaña de correo electrónico durante una sesión determinada es de interés, no el valor real del campo cs-uri-consulta (correo electrónico).

![](assets/dwb_impl_arch_1.png)

La segunda función principal de los contadores es que forman la columna vertebral de la estructura de esquema del conjunto de datos. El esquema de datos y todas las demás dimensiones están organizados para agruparse en y pertenecen a un recuento. En otras palabras, si consideramos las dimensiones como &quot;categorías&quot;, entonces los contadores son la manera en que organizamos estas &quot;categorías&quot; en grupos.
Cuando las dimensiones se agrupan en una dimensión contable, se dice que se encuentran en el &quot;nivel&quot; de la dimensión contable. Por ejemplo: en la figura de abajo puede ver que &#39;Dirección de correo electrónico&#39; está en el nivel de Visitante y que &quot;Explorador&quot; está en el nivel de visita. &quot;Principal&quot; y &quot;secundario&quot; se refieren a la relación entre el recuento y las dimensiones agrupadas debajo de él. Por ejemplo, Visitante es un &quot;elemento principal&quot; de la dirección de correo electrónico. Por el contrario, la dirección de correo electrónico es un &quot;elemento secundario&quot; del Visitante. ![](assets/dwb_impl_arch_2.png) ![](assets/dwb_impl_arch_3.png)

## Creación de un recuento en el área de trabajo de datos {#section-491f3e8e4fbc429e95d6c97f012a208e}

Realice los siguientes pasos para crear el recuento en el área de trabajo de datos:

1. Abrir Administrador de Perfiles
1. En la carpeta Transformation, cree un archivo de configuración y ábralo en la estación de trabajo.
1. En Dimensiones extendidas, haga clic con el botón derecho y elija Añadir nuevo -> Contable como se muestra a continuación: ![](assets/dwb_impl_arch_4.png)

1. Introduzca el nombre de la nueva tabla contable. En el ejemplo siguiente, se define la cuenta de clientes. Si es el Contable de nivel más alto, entonces en la Raíz de escritura principal. ![](assets/dwb_impl_arch_5.png)

   Si el Contable no es el nivel superior, en el campo principal proporcione el nombre del Contable principal. En el ejemplo siguiente, se crea la cuenta de participación y el elemento principal de esta cuenta es Cliente. ![](assets/dwb_impl_arch_5.png)

Para obtener información adicional sobre la arquitectura de Área de trabajo de datos para el diseño de esquemas, estructuras contables y configuraciones de fuentes de datos sin conexión, consulte la interfaz [de Esquema de](https://docs.adobe.com/content/help/en/data-workbench/using/client/admin-ui/c-dtst-sch-intrf.html)Dataset.
