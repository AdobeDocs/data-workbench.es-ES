---
title: Página de prueba oculta
description: Esta página está oculta para la búsqueda y para la TDC
hide: true
hidefromtoc: true
badgePremium: label="Premium" type="Positive" url="https://www.premium-product.com" tooltip="Download Premium"
badgeExam: label="Exam ADO-E903" type="neutral"
source-git-commit: c92c1e5688ca867caf1f3d4a6a3e44dafb5b3734
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# Página de prueba oculta

## Distintivos

Un distintivo es una etiqueta de color que se utiliza como indicador de contenido. Por ejemplo, puede agregar un distintivo para marcar un artículo como _Beta_ o una sección como _Premium_. Puede cambiar el color de un distintivo y asociar una dirección URL y la información del objeto.

[!BADGE Ejemplo de distintivo]

Existen dos tipos de distintivos, cada uno con una sintaxis diferente:

* **Metadatos** - Muestra el distintivo cerca de la parte superior de una página
* **En línea** - Muestra el distintivo donde se encuentra la sintaxis

### Distintivos de metadatos

Al agregar sintaxis de distintivo en los metadatos, se coloca un distintivo encima del título de la página (H1) en el artículo.

Puede asignar nombres a los distintivos, por ejemplo, mediante _badge1_ o _badge2_. O bien, puede ser más creativo (siempre que el nombre comience por _distintivo_).

Ejemplos de metadatos:

```
badgePremium: label="Premium" type="Positive" url="https://www.premium-product.com" tooltip="Download Premium"
badgeExam: label="Exam ADO-E903" type="neutral"
```

* **badgePremium:** En este ejemplo se muestra un distintivo Premium con una dirección URL y una información del objeto.

* **badgeExam:** En este ejemplo se muestra una insignia oscura con un número de ID de examen.

#### Distintivos en línea

Especifique la información del distintivo en su propia línea o en un encabezado, tabla u otro elemento de página.

Esta es la sintaxis de un distintivo en línea con una etiqueta beta, color azul, URL e información del objeto:

`[!BADGE Beta]{type=Informative url="https://www.example.com" tooltip="Go to example.com"}`

### Colores de distintivo disponibles

Los distintivos utilizan colores definidos en Espectro de Adobe:

| Tipo | Distintivo |
|---|---|
| Informativo (predeterminado) | [!BADGE Beta]{type=Informative url="https://www.example.com"} |
| Positiva | [!BADGE Nueva función]{type=Positive url="https://www.example.com" tooltip="Vaya a example.com"} |
| Negativa | [!BADGE Suspendido]{type=negative tooltip="Esta función ya ha finalizado su vida útil"} |
| Neutra | [!BADGE Quizás]{type=Neutral tooltip="Un jinete se cayó del caballo..."} |
| Precaución | [!BADGE Atención]{type=Caution tooltip="Estado amarillo"} |

Ejemplos de sintaxis

```
|Type|Badge|
|---|---|
|Informative (default)|[!BADGE Beta]{type=Informative url="https://www.example.com"}|
|Positive|[!BADGE New Feature]{type=Positive url="https://www.example.com" tooltip="Go to example.com"}|
|Negative|[!BADGE Discontinued]{type=negative tooltip="This feature is now end of life"}|
|Neutral|[!BADGE Maybe]{type=Neutral tooltip="A rider fell off the horse..."}|
|Caution|[!BADGE Attention]{type=Caution tooltip="Yellow status"}|
```

### Requisitos para distintivos

* Solo se permiten dos distintivos en los metadatos. Esta regla es configurable, por lo que debe hacernos saber si necesita una excepción.
* Solo se requiere la etiqueta del distintivo. La variable `type`, `url`y `tooltip` Los parámetros son opcionales. La variable `type` determina el color. La variable `url` permite a los usuarios hacer clic en el distintivo para abrir un artículo o una página. La variable `tooltip` muestra el texto de información sobre herramientas al pasar el ratón.
* Adición de un distintivo al `TOC.md` muestra el distintivo en cada artículo de la guía. Si especifica una dirección URL para que el distintivo vaya a un artículo, asegúrese de utilizar un vínculo raíz (por ejemplo, `/help/guide/article.md`) no es un vínculo relativo (por ejemplo, `article.md`) para tener en cuenta los artículos de diferentes carpetas.
* Adición de un distintivo a `metadata-new.md` muestra el distintivo en cada artículo de una cesión temporal.
* Para los distintivos de metadatos, asegúrese de que todos los valores estén entre comillas. Para distintivos en línea, asegúrese de que `url` y `tooltip` están entre comillas.
* Los valores válidos de tipo incluyen *Informativo* (predeterminado, azul), *Positivo* (verde), *Negativo* (rojo), *Neutro* (gris oscuro) y *Precaución* (amarillo).
* Las etiquetas de distintivo están localizadas.
* Si se especifican varios distintivos de metadatos, los distintivos se muestran en orden alfabético en función del nombre del distintivo, como `badge1:` o `badgeWeb`.
* Si desea que la dirección URL se abra en una pestaña nueva, utilice esta sintaxis:

   ```
   [!BADGE Open in new tab]{type=Negative url="https://www.adobe.com newtab=true" tooltip="Open adobe.com in new tab"}
   ```

   Procesado:

   [!BADGE Abrir en una pestaña nueva]{type=Negative url="https://www.adobe.com newtab=true" tooltip="Abra adobe.com en la nueva pestaña"}

## Resaltado del texto

El equipo de Workfront ha solicitado poder utilizar el resaltado amarillo para indicar la vista previa de las próximas funciones. Así es como funciona.

Ejemplo 1:

```
This entire paragraph should NOT be highlighted. <span class="preview"> This word is **bold** inside a highlighted sentence.</span> And this is just the last sentence.
```

Procesado:

Todo este párrafo NO debe destacarse. <span class="preview"> Esta palabra es **bold** dentro de una frase resaltada.</span> Y esta es sólo la última frase.

Ejemplo 2:

```
Highlighting should start after this paragraph.

<div class="preview">

**This is a test**

>[!TIP]
>
>Drink 6 cups of water a day.

Last highlighted paragraph

<\div>

Not highlighted
```

Procesado: El resaltado debe comenzar después de este párrafo.

<div class="preview">

**Esta es una prueba**

>[!TIP]
>
>Beba 6 tazas de agua al día.

Último párrafo resaltado

&lt;\div>

No resaltado

Como regla general, utilice `<span class="preview">` para resaltar un párrafo o texto dentro de un párrafo, y utilice `<div class="preview">` para varios párrafos y componentes.

## Resaltado de sintaxis para bloques de código

El Experience League admite el resaltado de sintaxis para bloques de código. Asegúrese de especificar un idioma como `java` después del conjunto inicial de comillas invertidas para asegurarse de que la sintaxis está resaltada correctamente. Para obtener una lista de idiomas válidos, consulte [https://prismjs.com](https://prismjs.com/#supported-languages). Si faltan idiomas, registre un ticket de jira.

### Numeración de líneas en bloques de código

Agregar `{line-numbers="true"}` después del idioma para habilitar la numeración de líneas.

Ejemplo con números de línea (&grave;&grave;&grave;&grave;`html {line-numbers="true"}`):

```html {line-numbers="true"}
<!DOCTYPE html>
<html>
<body>

<h1>My First Heading</h1>
<p>My first paragraph.</p>

</body>
</html>
```

**Iniciar numeración en la línea _**

Agregar `start-number="n"` después de la sintaxis del número de línea para iniciar la numeración en un número distinto de 1.

Ejemplo con la nueva línea de inicio (&grave;&grave;&amp;grave);`html {line-numbers="true" start-line="7"}`):

```html {line-numbers="true" start-line="7"}
<!DOCTYPE html>
<html>
<body>

<h1>My First Heading</h1>
<p>My first paragraph.</p>
<p>My second paragraph.</p>

</body>
</html>
```

### Resaltado de líneas en bloques de código

Agregar `highlight="n"` después de la sintaxis del número de línea para resaltar filas dentro de un bloque de código. Especificación `11-13, 16` resaltará las líneas 11 a 13 y 16.

Ejemplo con resaltado de línea (&grave;&grave;&grave;&grave;`html {line-numbers="true" start-line="7" highlight="11-13, 16"}`):

```html {line-numbers="true" start-line="7" highlight="11-13, 16"}
<!DOCTYPE html>
<html>
<body>

<h1>My First Heading</h1>
<p>My first paragraph.</p>
<p>My second paragraph.</p>

</body>
</html>
```
