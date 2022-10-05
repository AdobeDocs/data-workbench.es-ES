---
description: En esta sección se explican los distintos tipos de Dimension y cómo configurarlos en DWB.
title: Configuración de la dimensión
uuid: 5b40cb43-7790-4b87-a0bb-be395a420157
exl-id: 04afd773-e938-49f7-83c9-1d706a6dc525
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '1324'
ht-degree: 4%

---

# Configuración de la dimensión{#dimension-setup}

{{eol}}

En esta sección se explican los distintos tipos de Dimension y cómo configurarlos en DWB.

## ¿Qué son los Dimension? {#section-dac631943df24706827cedc6f0641543}

En el nivel más básico, las dimensiones son categorías en las que se pueden desglosar los datos del conjunto de datos.

Práctica recomendada: Se puede proporcionar cualquier nombre a los Dimension del esquema de datos. Los nombres de Dimension utilizados y explicados en este curso se consideran una práctica recomendada. Los Dimension pueden tener nombres diferentes. A medida que vaya recibiendo exposición a otros conjuntos de datos, empezará a ver diferencias en los conjuntos de datos. Es importante comprender el propósito de las dimensiones en lugar de su nombre. Por ejemplo, tanto si se llama &quot;Visitante&quot;, &quot;Cliente&quot;, &quot;Persona&quot;, &quot;Consumidor&quot; o &quot;Usuario&quot;, es importante comprender que estos son términos que normalmente se utilizan para hacer referencia a la dimensión contable de nivel más alto que se utiliza para recopilar información sobre una persona concreta.

Para obtener información completa, consulte la [Configuración de conjunto de datos](https://experienceleague.adobe.com/docs/data-workbench/using/dataset/c-dataset-constr.html) guía.

## Tipos de Dimension en DWB {#section-a4fbb7bf2bde44528ac0f94a96465862}

Hay dos tipos de dimensiones en la Data Workbench: Dimension extendidos y Dimension derivados.

Los Dimension extendidos se crean a partir de campos de los archivos de datos &quot;sin procesar&quot;. Las dimensiones extendidas se utilizan para categorizar los datos &quot;sin procesar&quot; y para especificar las relaciones que existen entre los datos. Las dimensiones extendidas las crean los arquitectos de Data Workbench.

Los Dimension derivados los crea un usuario &quot;en el lado del cliente&quot; después de que el conjunto de datos se haya procesado con las definiciones de dimensión extendidas existentes. Por ejemplo, en función de la dimensión URI existente, un usuario puede elegir crear una dimensión Nombre de página derivada, que muestra un nombre de página más fácil de usar en lugar de un URI determinado. Todas las dimensiones consisten en elementos o elementos que se han clasificado (agrupado) juntos para formar la dimensión. A continuación se muestran tres dimensiones y sus elementos.

Muchas dimensiones derivadas se crean automáticamente con el objetivo de impulsar distintos tipos de visualizaciones. Por ejemplo, cuando un usuario crea un sitio o procesa un mapa, los servidores DWB crean una dimensión Prefijo . Otras, como las dimensiones de tiempo de los informes, están definidas por archivos que se encuentran en el directorio Dimensiones de un perfil.

>[!NOTE]
>
>Los elementos que aparecen en cualquier dimensión dada solo reflejarán los valores que existen en registros que se han elegido para cargar en el conjunto de datos. Por ejemplo, si no hay datos para &quot;12 de mayo&quot;, ese mes no aparecerá en la dimensión &quot;Mes&quot;.

## Dimensiones extendidas {#section-5fc51fa539034941a30a2df606f7d727}

Tipos de dimensiones extendidas

**1) Dimension contables**

En el nivel más alto hay dimensiones contables. Las dimensiones contables cumplen dos funciones principales. En primer lugar, son dimensiones cuyos elementos desea contar. En otras palabras, los recuentos responden a preguntas como:

* &quot;¿Cuántos visitantes visitaron su página principal?&quot;
* &quot;¿Cuántas visitas vinieron de google.com?&quot;

Por este motivo, los recuentos suelen utilizarse como bloque de creación básico para crear métricas.

La segunda función principal de las tablas contables es que forman la columna vertebral de la estructura de esquema del conjunto de datos. El esquema de datos y todas las demás dimensiones se organizan para agruparse en y pertenecer a una cuenta. En otras palabras, si consideramos las dimensiones como &quot;categorías&quot;, entonces los recuentos son la forma en que organizamos estas &quot;categorías&quot; en grupos.

Cuando las dimensiones se agrupan en una dimensión contable, se dice que se encuentran en el &quot;nivel&quot; de la dimensión contable. Por ejemplo, la &quot;dirección de correo electrónico&quot; puede estar en el nivel del visitante y el &quot;explorador&quot; en el nivel de la visita. &quot;Principal&quot; y &quot;secundario&quot; se refieren a la relación entre la tabla contable y las dimensiones agrupadas debajo de ella. Por ejemplo, Visitante es un &quot;elemento principal&quot; de la dirección de correo electrónico. Por el contrario, la dirección de correo electrónico es un &quot;elemento secundario&quot; del visitante.

**2) Dimension simples**

Las dimensiones más comunes son las dimensiones simples. Las dimensiones simples tienen una relación &quot;uno a varios&quot; con una dimensión contable principal y se utilizan comúnmente en las visualizaciones para que pueda ver sus elementos. Esto significa que una dimensión contable puede tener un valor para una dimensión simple, pero la dimensión simple puede pertenecer a uno o más recuentos. Por ejemplo, un cliente tiene el nombre &quot;John&quot;: ese cliente solo puede tener un nombre, pero muchos otros clientes pueden tener el nombre &quot;John;. Otro ejemplo: solo se puede utilizar un navegador (por ejemplo, Firefox) para cualquier visita concreta a un sitio web, pero ese navegador puede utilizarse para muchas visitas diferentes.

Si las dimensiones contables responden &quot;¿Cuántas?&quot;, entonces las dimensiones simples responden &quot;¿Cuáles?&quot;. Uso del mismo ejemplo anterior utilizado en la sección de dimensión contable; Nombre de página es la dimensión simple. Con la tabla y la dimensión simple, Nombre de página, podemos responder preguntas como:

* &quot;¿Qué página tuvo la mayor cantidad de vistas de página?&quot;
* &quot;De todas las páginas del carro de compras, ¿cuál tuvo más visitas?&quot;.

**3) Dimension &quot;varios a varios&quot;**

Las dimensiones &quot;varios a varios&quot; tienen una relación &quot;varios a varios&quot; con respecto a una dimensión contable principal. Por ejemplo, si una dimensión denominada Término de búsqueda externa se encuentra en el nivel de visita; un término de búsqueda externa determinado se puede usar en una o varias visitas, y una visita determinada puede incluir uno o varios términos de búsqueda externa. Por lo tanto, Término de búsqueda externa es una dimensión de varios a varios.

**4) Dimension numéricos**

Las dimensiones numéricas son un tipo de dimensión simple que tiene un valor numérico. Las dimensiones numéricas suelen crearse para utilizarse en métricas. Algunos ejemplos de dimensiones numéricas son &quot;Ingresos&quot;, &quot;Pedidos&quot; y &quot;Unidades&quot;. En el ejemplo anterior, &quot;Pedidos de cliente&quot; es una dimensión numérica.
**5) Dimension denormales** Las dimensiones denormalizadas son dimensiones que tienen una relación &quot;uno a uno&quot; con una dimensión contable principal. Las dimensiones denormalizadas se utilizan a menudo con dimensiones que tienen una alta cardinalidad (muchos elementos únicos) como los datos de identificación. Por ejemplo, un visitante solo puede tener un ID de usuario y otro solo puede pertenecer a un visitante. Por lo tanto, esta es una relación uno a uno y puede ser una dimensión denormalizada.

Por ejemplo, el ID de usuario web de Geometrixx es una dimensión denormalizada a nivel de cliente. Como es normal, tiene una relación &quot;uno a uno&quot; con su dimensión principal, lo que significa que cada ID de usuario web tiene un cliente y cada cliente solo tiene un ID de usuario web. Por lo tanto, la métrica &quot;Clientes&quot; solo puede ser &quot;1&quot; para cada elemento del ID de usuario web de Geometrixx.

**6) Dimension de tiempo**

Las dimensiones de tiempo le permiten crear un conjunto de dimensiones de tiempo locales periódicas o absolutas basadas en el campo de marca de tiempo que especifique. Algunos ejemplos de dimensiones temporales son &quot;Día&quot;, &quot;Hora&quot;, &quot;Semana&quot; y &quot;Hora del día&quot;. En el ejemplo anterior, la tabla &quot;Hora del día&quot; muestra cuántas visitas y vistas de página se recibieron durante las diferentes horas de los días.

>[!NOTE]
>
>Los % de escapes utilizados para el formato de visualización son los mismos que la biblioteca C estándar *strftime*.

## Definición de dimensiones extendidas {#section-38ee124ec74b43fb95f13194a9582b97}

Pasos para definir el Dimension extendido:

1. Mientras trabaja en el perfil del conjunto de datos, abra el Administrador de perfiles y haga clic en Conjunto de datos para mostrar su contenido.
1. Abra el archivo Transformation.cfg o el archivo Incluir conjunto de datos de transformación en el que desea definir la dimensión ampliada.
1. Haga clic con el botón derecho en Transformaciones y haga clic en Agregar nuevo > `<Extended dimension type>`.
1. Introduzca la información adecuada para su dimensión extendida. Para obtener descripciones de los tipos de transformación e información sobre sus parámetros, consulte las secciones siguientes:

   * [Dimensiones contables](https://experienceleague.adobe.com/docs/data-workbench/using/dataset/extended-dimensions/extended-dimensions-types/c-count-dim.html)
   * [Dimensiones simples](https://experienceleague.adobe.com/docs/data-workbench/using/dataset/extended-dimensions/extended-dimensions-types/c-simple-dim.html)
   * [Dimensión “varios a varios”](https://experienceleague.adobe.com/docs/data-workbench/using/dataset/extended-dimensions/extended-dimensions-types/c-many-dim.html)
   * [Dimensiones numéricas](https://experienceleague.adobe.com/docs/data-workbench/using/dataset/extended-dimensions/extended-dimensions-types/c-num-dim.html)
   * [Dimensiones denormales](https://experienceleague.adobe.com/docs/data-workbench/using/dataset/extended-dimensions/extended-dimensions-types/c-denormal-dim.html)
   * [Dimensiones temporales](https://experienceleague.adobe.com/docs/data-workbench/using/dataset/extended-dimensions/extended-dimensions-types/c-time-dim.html)

1. Para cualquier dimensión ampliada que defina, puede agregar una o más líneas de comentario al parámetro Comentarios para describir aún más la dimensión o agregar notas sobre su uso. Para añadir un comentario, haga clic con el botón derecho en el *Comentarios* y haga clic en* Agregar nuevo > Línea de comentario*.

1. Una vez definidas las dimensiones ampliadas en el archivo de configuración, guarde el archivo localmente y guárdelo en el perfil del conjunto de datos en el servidor DWB.

## Ocultar dimensiones extendidas {#section-02339fb51658418eabc10186cd5957d7}

Los Dimension extendidos se pueden ocultar para que no aparezcan en el menú Dimension del DWB. Para ocultar la dimensión, establezca la propiedad Hidden en &quot;True&quot; en la definición de la dimensión.
