---
description: Las expresiones regulares se utilizan en todos los campos de búsqueda del área de trabajo de datos, incluidos los paneles de entidades de consulta.
solution: Analytics
title: Expresiones regulares
topic: Data workbench
uuid: f3a0119d-6fac-4f63-8dca-4db32d2a737a
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Regular Expressions{#regular-expressions}

Las expresiones regulares se utilizan en todos los campos de búsqueda del área de trabajo de datos, incluidos los paneles de entidades de consulta.

* [Acerca de las expresiones regulares](../../home/c-dataset-const-proc/c-reg-exp.md#section-cc9dc7293bb04fc0b41fe8acdee708f0)
* [Terminología de expresiones regulares](../../home/c-dataset-const-proc/c-reg-exp.md#section-80b0d54f731e448391532ab3eb3c525c)
* [Acerca de la coincidencia literal](../../home/c-dataset-const-proc/c-reg-exp.md#section-ec4497e3160c47ba9b828d939761b3e0)
* [Uso de metacaracteres](../../home/c-dataset-const-proc/c-reg-exp.md#section-e29a804336304ea1ba33d40d60139aa2)
* [Extracción de patrones](../../home/c-dataset-const-proc/c-reg-exp.md#section-4389779653b64f6cb7c47615b25c1a79)

## Acerca de las expresiones regulares {#section-cc9dc7293bb04fc0b41fe8acdee708f0}

Una expresión regular es un patrón de texto, que consiste en una combinación de caracteres alfanuméricos y caracteres especiales conocidos como metacaracteres, que localiza patrones y extrae subcadenas del texto. Las expresiones regulares se utilizan ampliamente en la programación informática y son parte integrante de idiomas como Perl.

Para identificar y extraer patrones de cadena complejos, el servidor del área de trabajo de datos utiliza expresiones regulares en algunas de las transformaciones y condiciones. Lo que sigue es una breve guía de las expresiones regulares.

El presente apéndice no es una introducción completa de las expresiones regulares. Una referencia particularmente buena es la publicación de O&#39;Reilly *Mastering Regular Expressions, 2da edición* de Jeffrey E. F. Friedl.

## Terminología de expresiones regulares {#section-80b0d54f731e448391532ab3eb3c525c}

| Término | Definición |
|---|---|
| Literal | Un literal es un carácter que se utiliza en una expresión regular para localizar una secuencia específica de caracteres. Por ejemplo, para encontrar el producto en [!DNL shop/products.html], el producto de cadena es un literal o lo que estamos literalmente buscando en la cadena. |
| Metacarácter | Un metacarácter es un carácter especial que tiene una interpretación única en el contexto de las expresiones regulares. Por ejemplo, el punto (.) es un metacarácter que se utiliza para hacer coincidir cualquier carácter. |
| Secuencia de escape | Una secuencia de escape es simplemente una manera de decirle al motor de expresión regular que nos gustaría usar uno de los metacaracteres como literal. Las secuencias de escape siempre comienzan con el carácter de barra invertida (`\`). Al colocar la barra invertida (que también es un metacarácter) delante de un metacarácter, el motor de expresión regular interpreta el metacarácter escapado como literal. Por ejemplo, si desea coincidir con el punto del metacarácter (`.`), debe utilizar una secuencia de escape. Sin embargo, para coincidir con uno de los puntos de la cadena 168.196.0.11, puede utilizar la expresión regular consistente en una barra invertida y un punto (`\.`). |
| Patrón | Es una terminología abreviada para la expresión regular. En esencia, una expresión regular es un patrón que intenta comparar con la cadena de destino. |
| Cadena de destino | Este término hace referencia a la cadena en la que buscamos para localizar el patrón deseado. |

## Acerca de la coincidencia literal {#section-ec4497e3160c47ba9b828d939761b3e0}

La coincidencia literal toma una cadena literal sin caracteres de escape y busca en la cadena de destino para ver si es una subcadena de la cadena de destino.

En este ejemplo, se ve cómo funciona la coincidencia literal. Considere una situación en la que se recopilan datos del tráfico del sitio web y el campo cs(referrer) contiene el siguiente valor:

`http://www.abc.com/adventurenews/today.html?ad=123AZ45`

Para determinar si el referente representa a alguien que hizo clic en uno de los anuncios, debe ver si el referente contiene la publicidad de cadena. Simplemente puede utilizar la publicidad de cadena literal para buscar en la cadena de destino y determinar si se utilizó una publicidad para enrutar el tráfico al sitio. Aunque esto coincidiría con la cadena de destino, coincidiría en dos ubicaciones y, por lo tanto, sería ambiguo y podría dar lugar a falsos positivos.

La siguiente dirección URL contiene la publicidad de cadena en dos lugares diferentes:

`http://www.abc.com/ad vertnews/today.html?ad =123AZ45`

Por lo tanto, si intenta determinar qué sesiones se iniciaron como resultado de una campaña publicitaria en particular, el uso de la publicidad literal como expresión regular claramente no es suficiente. Cambiar el literal a &quot;ad=&quot; eliminaría esta ambigüedad y daría como resultado que la expresión realizara una sola coincidencia. Sin embargo, incluso esto puede no ser suficiente para garantizar que el referente formara parte de la campaña de publicidad. Considere el siguiente referente:

`http://www.xyz.com/hello.html?pad=something`

No tiene ningún control sobre las direcciones URL que otros usuarios estén utilizando para crear vínculos al sitio. La coincidencia literal es un mecanismo demasiado simple para encontrar las sesiones que comenzaron como resultado de la campaña de publicidad. En la siguiente sección se explica cómo se pueden utilizar los metacaracteres para lograr una coincidencia más flexible y potente.

## Uso de metacaracteres {#section-e29a804336304ea1ba33d40d60139aa2}

Un metacarácter es un carácter especial de un programa o campo de datos que proporciona información sobre otros caracteres.

| metacarácter | description |
|---|---|
| . (punto) | Coincide con un solo carácter, por ejemplo: `re:x.z` coincide con &quot;xyz&quot; o &quot;xxz&quot;. |
| * (estrella) | Coincide con uno o varios caracteres, por ejemplo: `re:Z*` coincide con &quot;ZZZ&quot;. |
| ? (comodín) | Coincide con 0 o 1 de la expresión anterior para forzar la coincidencia mínima, por ejemplo: `xy?z` coincide con &quot;xy&quot; y &quot;xyz&quot;. |

También se pueden utilizar expresiones regulares comunes adicionales para crear cadenas de búsqueda más complejas.

**Listas, rangos y O**

La coincidencia literal le permite buscar una sola cadena, pero los corchetes, guiones y tubos le permiten definir una lista de cosas que se deben buscar en la cadena de destino.

<table id="table_18B86955EC3748079E7C176273ADE92B"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Para este metacarácter... </th> 
   <th colname="col2" class="entry"> El procesador de expresiones regulares... </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Corchetes ([ ]) </td> 
   <td colname="col2"> Coincida con cualquiera de los caracteres dentro del corchete con una sola posición de carácter. Por ejemplo, [AB] es una instrucción para que coincida con la letra A o la letra B, y [0123456789] indica que coincide con cualquier carácter del rango de 0 a 9. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Guión (-) </td> 
   <td colname="col2"> <p>Haga coincidir un rango de caracteres. Por lo tanto, en lugar de escribir [0123456789] simplemente podríamos escribir [0-9]. </p> <p> Esto se puede ampliar a rangos de caracteres y a varios rangos dentro de un conjunto de corchetes. Por ejemplo, [0-9A-C] coincide con los caracteres de 0 a 9 y de A a C. </p> <p> <p>Nota:  Para probar un guión (-) como un literal dentro de los corchetes, debe aparecer primero o último. Por ejemplo, [-0-9] prueba para - y 0 a 9. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Barra vertical (|) </td> 
   <td colname="col2"> Haga coincidir una de las dos opciones con una cadena de destino determinada. Por ejemplo, b|nat coincide con bat o nat. </td> 
  </tr> 
 </tbody> 
</table>

Veamos los siguientes ejemplos:

| Patrón | Cadena | Coincidencias |
|---|---|---|
| Win9`[58]` | OS=Win95 | Win95 |
| Win95 | 8 | OS=Win98 | Win98 |
| `[0-9]` | Mozilla/3.0 | 3 |
| Lección`[A-Z]` | Lección a | No hay coincidencia porque la letra a minúscula no está en el rango de mayúsculas de A a Z. |

**Negación**

La negación es una forma de decir que le gustaría hacer coincidir cualquier cosa excepto los caracteres determinados. El metacarácter de negación, el circunflejo o acento circunflejo (`^`), se utiliza como primer carácter entre corchetes para indicar que desea que la coincidencia sea cualquier cosa excepto el resto de los caracteres entre corchetes. Por ejemplo, para que coincida con cualquier carácter que no sea un punto y coma (`;`), debe escribir

[`^;`]

Esto coincidiría con cualquier carácter excepto el punto y coma.

**Posicionamiento**

Para forzar una coincidencia al principio o al final de una cadena de destino, se utiliza uno de los dos metacaracteres.

| Para este metacarácter... | El procesador de expresiones regulares... |
|---|---|
| Circumflex o Caret (`^`) | Coincidir con el principio de la cadena. Por ejemplo, ^`[Tt]`coincidiría con la cadena de destino &quot;El principio&quot; pero no coincidiría con &quot;Este es el principio&quot;. |
| Símbolo del dólar (`$`) | Coincidir con el final de la cadena. Por ejemplo, `[Ee]`nd$ coincidiría con &quot;Este es el final&quot; pero no coincidiría con &quot;El final es una hora especial&quot;. |

>[!NOTE]
>
>Cuando la expresión regular contiene ^ al principio y $ al final, toda la cadena de destino debe coincidir con la expresión regular.

**Coincidencia de cualquier cosa**

El punto (.) es un metacarácter especial que coincide con cualquier carácter de la cadena de destino. Por ejemplo, la expresión regular `^…$` coincide con cualquier cadena de destino que tenga exactamente tres caracteres. La expresión regular &quot;...&quot; coincide con cualquier cadena de destino que contenga al menos tres caracteres.

**Patrones repetidos**

Los metacaracteres de iteración le permiten hacer coincidir un patrón más de una vez.

<table id="table_6A14333D6C264A48ADF1EBBAF687CADD"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Para este metacarácter... </th> 
   <th colname="col2" class="entry"> El procesador de expresiones regulares... </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Signo de interrogación (?) </td> 
   <td colname="col2"> No coincida ninguna instancia o instancia del carácter inmediatamente anterior al metacarácter (?). Por ejemplo, el parámetro rea?d coincide con rojo y leído. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Asterisco (*) </td> 
   <td colname="col2"> Coincida con cero o más incidencias del carácter inmediatamente antes del metacarácter (*). Por ejemplo, el patrón [0-9]* coincide con cualquier número de caracteres entre 0 y 9 (cualquier entero). </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Más (+) </td> 
   <td colname="col2"> Coincida con una o más incidencias del carácter o rango anterior. Por ejemplo, el patrón tres o más coincidiría con tres pero no con tres. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> {n} </td> 
   <td colname="col2"> <p>Coincida exactamente n veces con el carácter o el intervalo que sigue. El siguiente patrón coincide con los números de teléfono de Estados Unidos: [0-9]{3}-[0-9]{3}-[0-9]{4}. </p> <p> Aunque no es un patrón óptimo, determina si la cadena de destino tiene el formato adecuado. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> {n,m} </td> 
   <td colname="col2"> Haga coincidir el carácter anterior al menos n veces y como máximo m veces. Por ejemplo, para{1,2}d coincidiría con comida y comida, pero no comida. </td> 
  </tr> 
 </tbody> 
</table>

## Extracción de patrones {#section-4389779653b64f6cb7c47615b25c1a79}

La coincidencia de patrones es sólo parte de la potencia de las expresiones regulares. Las expresiones regulares también proporcionan un mecanismo para extraer partes clave de una cadena de destino. Esto se realiza mediante el uso de los paréntesis izquierdo y derecho. Estas extracciones se utilizan normalmente como entrada en otro proceso y se accede a ellas mediante el uso de *%position%*, donde position es un entero que hace referencia al número de paréntesis que coincidió.

Considere los siguientes ejemplos de extracción de patrones:

<table id="table_BC8D471B966844049FFFCDEC0F183941"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Patrón </th> 
   <th colname="col2" class="entry"> Cadena </th> 
   <th colname="col3" class="entry"> Coincidencias </th> 
   <th colname="col4" class="entry"> Extracción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Win(9[58]) </td> 
   <td colname="col2"> OS=Win95 </td> 
   <td colname="col3"> Win95 </td> 
   <td colname="col4"> %1% = 95 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> (Win)(95|8) </td> 
   <td colname="col2"> OS=Win98 </td> 
   <td colname="col3"> Win98 </td> 
   <td colname="col4"> <p>%1% = Win </p> <p> %2% = 98 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Mozilla/([0-9]).([0-9]) </td> 
   <td colname="col2"> Mozilla/3.0 </td> 
   <td colname="col3"> Mozilla/3.03 </td> 
   <td colname="col4"> <p>%1% = 3 </p> <p> %2% = 0 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Lesson([A-Z]) </td> 
   <td colname="col2"> Lección a </td> 
   <td colname="col3"> No hay coincidencia porque la letra a minúscula no está en el rango de mayúsculas de A a Z </td> 
   <td colname="col4"> </td> 
  </tr> 
 </tbody> 
</table>

