---
description: Esta sección explica los diferentes tipos de dimensiones y cómo configurarlas en DWB.
title: Configuración de dimensión
uuid: 5b40cb43-7790-4b87-a0bb-be395a420157
translation-type: tm+mt
source-git-commit: ded50c4eeadea80156c17a4cad985d0ceddd5500

---


# Configuración de dimensión{#dimension-setup}

Esta sección explica los diferentes tipos de dimensiones y cómo configurarlas en DWB.

## ¿Qué son las dimensiones? {#section-dac631943df24706827cedc6f0641543}

En el nivel más básico, las dimensiones son categorías en las que se pueden desglosar los datos del conjunto de datos.

Práctica recomendada: Las dimensiones del esquema de datos pueden proporcionarse con cualquier nombre. Los nombres de dimensión utilizados y explicados en este curso se consideran una práctica recomendada. Los nombres de las dimensiones pueden variar. A medida que se va exponiendo a otros conjuntos de datos, comenzará a ver diferencias en los mismos. Es importante comprender el propósito de las dimensiones en lugar de su nombre. Por ejemplo, ya se llame &quot;Visitante&quot;, &quot;Cliente&quot;, &quot;Persona&quot;, &quot;Consumidor&quot; o &quot;Usuario&quot;, es importante comprender que estos términos se utilizan comúnmente para referirse a la dimensión contable de nivel más alto que se utiliza para recopilar información sobre una persona en particular.

Para obtener más información, consulte la guía de configuración [de](https://docs.adobe.com/content/help/en/data-workbench/using/dataset/c-dataset-constr.html) conjuntos de datos.

## Tipos de dimensiones en DWB {#section-a4fbb7bf2bde44528ac0f94a96465862}

Existen dos tipos de dimensiones en el área de trabajo de datos: Dimensiones extendidas y dimensiones derivadas.

Las dimensiones extendidas se crean a partir de los campos de los archivos de datos &quot;sin procesar&quot;. Las dimensiones extendidas se utilizan para categorizar los datos &quot;sin procesar&quot; y especificar las relaciones que existen entre los datos. Las dimensiones extendidas las crean los arquitectos del área de trabajo de datos.

Las dimensiones derivadas las crea un usuario &quot;en el lado del cliente&quot; después de que el conjunto de datos se haya procesado con las definiciones de dimensión extendidas existentes. Por ejemplo, según la dimensión URI existente, un usuario puede elegir crear una dimensión Nombre de página derivada, que muestra un nombre de página más sencillo de usar en lugar de un URI determinado. Todas las dimensiones consisten en elementos o elementos que se han clasificado (agrupado) juntos para formar la dimensión. Debajo hay tres dimensiones y sus elementos.

Muchas dimensiones derivadas se crean automáticamente con el objetivo de impulsar distintos tipos de visualizaciones. Por ejemplo, cuando un usuario crea un sitio o un mapa de procesos, los servidores DWB crean una dimensión Prefijo. Otras, como las dimensiones de tiempo de los informes, están definidas por archivos que se encuentran en el directorio Dimensiones de un perfil.

>[!NOTE]
>
>Los elementos que aparecen en cualquier dimensión dada solo reflejarán los valores que existen en los registros que se han elegido para cargar en el conjunto de datos. Por ejemplo, si no hay datos para &quot;12 de mayo&quot;, ese mes no aparecerá en la dimensión &quot;Mes&quot;.

## Extended Dimensions {#section-5fc51fa539034941a30a2df606f7d727}

Tipos de dimensiones extendidas

**1) Dimensiones contables**

En el nivel más alto hay un recuento de las dimensiones. Las dimensiones contables cumplen dos funciones principales. En primer lugar, son dimensiones cuyos elementos desea contar. En otras palabras, los contadores responden a preguntas como:

* &quot;¿Cuántos visitantes visitaron la página principal?&quot;
* &quot;¿Cuántas visitas vinieron de google.com?&quot;

Por este motivo, los contadores se utilizan a menudo como el bloque de creación fundamental básico para crear métricas.

La segunda función principal de los contadores es que forman la columna vertebral de la estructura de esquema del conjunto de datos. El esquema de datos y todas las demás dimensiones se organizan para agruparse en un recuento y pertenecer a él. En otras palabras, si consideramos las dimensiones como &quot;categorías&quot;, entonces los contadores son la manera en que organizamos estas &quot;categorías&quot; en grupos.

Cuando las dimensiones se agrupan en una dimensión contable, se dice que se encuentran en el &quot;nivel&quot; de la dimensión contable. Por ejemplo: la &#39;dirección de correo electrónico&#39; puede estar en el nivel de visitante y el &quot;explorador&quot; en el nivel de visita. &quot;Principal&quot; y &quot;secundario&quot; se refieren a la relación entre el recuento y las dimensiones agrupadas debajo de él. Por ejemplo: Visitante es un &quot;padre&quot; de la dirección de correo electrónico. Por el contrario, la dirección de correo electrónico es un &quot;elemento secundario&quot; del visitante.

**2) Dimensiones simples**

Las dimensiones más comunes son las dimensiones simples. Las dimensiones simples tienen una relación uno a varios con una dimensión contable principal y se utilizan comúnmente en visualizaciones para que pueda ver sus elementos. Esto significa que una dimensión contable puede tener un valor para una dimensión simple, pero la dimensión simple puede pertenecer a uno o más contadores. Por ejemplo, un cliente tiene el nombre &#39;John&#39;, que el cliente solo puede tener un nombre, pero muchos otros clientes pueden tener el nombre &#39;John;.. Otro ejemplo es que sólo se puede utilizar un navegador (por ejemplo, Firefox) para cualquier visita concreta a un sitio web, pero ese navegador puede utilizarse para muchas visitas diferentes.

Si las dimensiones contables responden &quot;¿Cuántas?&quot;, entonces las dimensiones simples responden &quot;¿Cuáles?&quot;. Utilizando el mismo ejemplo anterior utilizado en la sección de dimensiones contables; Nombre de página es la dimensión simple. Con la tabla y la dimensión simple, Nombre de página, podemos responder preguntas como:

* &quot;¿Qué página tuvo la mayor cantidad de vistas de página?&quot;
* &quot;De todas las páginas del carro de compras, ¿cuál tuvo la mayor cantidad de visitas?&quot;.

**3) Varias dimensiones a muchas**

Las dimensiones &quot;varios a varios&quot; tienen una relación &quot;varios a varios&quot; con una dimensión contable principal. Por ejemplo, si una dimensión denominada Término de búsqueda externa se encuentra en el nivel de visita; un término de búsqueda externa determinado puede utilizarse en una o varias visitas y una visita determinada puede incluir uno o varios términos de búsqueda externa. Por lo tanto, el término de búsqueda externa es una dimensión de muchos a muchos.

**4) Dimensiones numéricas**

Las dimensiones numéricas son un tipo de dimensión simple que tiene un valor numérico. Las dimensiones numéricas suelen crearse para utilizarse en métricas. Algunos ejemplos de dimensiones numéricas son &#39;Ingresos&#39;, &#39;Pedidos&#39; y &#39;Unidades&#39;. En el ejemplo anterior, &quot;Pedidos del cliente&quot; es una dimensión numérica.
**5) Dimensiones** denormalizadas Las dimensiones denormalizadas son dimensiones que tienen una relación uno a uno con una dimensión contable principal. Las dimensiones denormalizadas se utilizan a menudo con dimensiones que tienen alta cardinalidad (muchos elementos únicos) como los datos de identificación. Por ejemplo, un visitante solo puede tener un ID de usuario y un ID de usuario solo puede pertenecer a un visitante. Por lo tanto, esta es una relación uno a uno y puede ser una dimensión denormalizada.

Por ejemplo, el ID de usuario web de Geometrixx es una dimensión denormalizada a nivel de cliente. Dado que es denormalizada, tiene una relación uno a uno con su dimensión principal, lo que significa que cada ID de usuario web tiene un cliente y cada cliente solo tiene un ID de usuario web. Por lo tanto, la métrica &#39;Clientes&#39; solo puede ser &#39;1&#39; para cada elemento del ID de usuario web de Geometrixx.

**6) Dimensiones temporales**

Las dimensiones de tiempo le permiten crear un conjunto de dimensiones de tiempo locales periódicas o absolutas en función del campo de marca de hora que especifique. Algunos ejemplos de dimensiones de tiempo son &quot;Día&quot;, &quot;Hora&quot;, &quot;Semana&quot; y &quot;Hora del día&quot;. En el ejemplo anterior, la tabla &#39;Hora del día&#39; muestra cuántas visitas y vistas de página se recibieron durante las distintas horas de los días.

>[!NOTE]
>
>El % de escapes utilizado para el formato de visualización es el mismo que el *tiempo de espera* estándar de la biblioteca C.

## Definición de dimensiones extendidas {#section-38ee124ec74b43fb95f13194a9582b97}

Pasos para definir la dimensión ampliada:

1. Mientras trabaja en su perfil de conjunto de datos, abra el Administrador de perfiles y haga clic en Conjunto de datos para mostrar su contenido.
1. Abra el archivo Transformation.cfg o el archivo Transformation Dataset Include en el que desea definir la dimensión ampliada.
1. Haga clic con el botón secundario en Transformaciones y haga clic en Agregar nuevo > `<Extended dimension type>`.
1. Introduzca la información adecuada para la dimensión extendida. Para obtener descripciones de los tipos de transformación e información sobre sus parámetros, consulte las secciones siguientes:

   * [Dimensiones contables](https://docs.adobe.com/content/help/en/data-workbench/using/dataset/extended-dimensions/extended-dimensions-types/c-count-dim.html)
   * [Dimensiones simples](https://docs.adobe.com/content/help/en/data-workbench/using/dataset/extended-dimensions/extended-dimensions-types/c-simple-dim.html)
   * [Varias dimensiones a muchas](https://docs.adobe.com/content/help/en/data-workbench/using/dataset/extended-dimensions/extended-dimensions-types/c-many-dim.html)
   * [Dimensiones numéricas](https://docs.adobe.com/content/help/en/data-workbench/using/dataset/extended-dimensions/extended-dimensions-types/c-num-dim.html)
   * [Dimensiones denormales](https://docs.adobe.com/content/help/en/data-workbench/using/dataset/extended-dimensions/extended-dimensions-types/c-denormal-dim.html)
   * [Dimensiones temporales](https://docs.adobe.com/content/help/en/data-workbench/using/dataset/extended-dimensions/extended-dimensions-types/c-time-dim.html)

1. Para cualquier dimensión ampliada que defina, puede agregar una o más líneas de comentario al parámetro Comments para describir más la dimensión o agregar notas sobre su uso. Para agregar un comentario, haga clic con el botón secundario en la etiqueta *Comentarios* y haga clic en* Agregar nuevo > Línea de comentarios*.

1. Una vez definidas las dimensiones extendidas en el archivo de configuración, guarde el archivo localmente y guárdelo en el perfil del conjunto de datos en el servidor DWB.

## Ocultar dimensiones extendidas {#section-02339fb51658418eabc10186cd5957d7}

Las dimensiones extendidas se pueden ocultar para que no aparezcan en el menú Dimensión del DWB. Para ocultar la dimensión, establezca la propiedad Oculto en &quot;Verdadero&quot; en la definición de dimensión.
