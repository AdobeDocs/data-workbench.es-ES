---
title: Página de prueba oculta
description: Esta página no se puede buscar ni consultar en la tabla de contenido
hide: true
hidefromtoc: true
badgePremium: label="Premium" type="Positive" url="https://www.premium-product.com" tooltip="Descargar Premium"
badgeExam: label="Examen ADO-E903" type="neutral"
exl-id: 02245655-511e-4e89-8846-dac85681ea91
source-git-commit: 6a10bc9a2ed41223070f3eba94b8ea7b4b1b77ab
workflow-type: tm+mt
source-wordcount: '806'
ht-degree: 4%

---

# Página de prueba oculta

Activar? Vuelva a comprobar el envío alrededor de las 3:10 PM. ¿Saldrá en vivo a las 3:30 PM?

## Previsualizar problema

El siguiente párrafo no se representa correctamente en la vista previa de VSC. No estoy seguro de por qué.

Si administra la contraseña [!DNL Adobe], puede [cambiar la contraseña en su cuenta de Adobe](https://helpx.adobe.com/manage-account/using/change-or-reset-password.html){target="_blank"}.

## Tipos de notas

Todos los tipos de notas admitidos.

>[!NOTE]
>
>This is a standard NOTE block.

>[!TIP]
>
>This is a standard tip.

>[!IMPORTANT]
>
>Esta es una nota importante.

>[!WARNING]
>
>Esta es una advertencia.

>[!CAUTION]
>
>Esto es una advertencia.

>[!ADMIN]
>
>Esta es una nota de administrador que se representa como ADMINISTRACIÓN. Solo EXL.

>[!AVAILABILITY]
>
>Esta es una nota de disponibilidad. Solo EXL.

>[!PREREQUISITES]
>
>Esta es una nota de Requisitos previos. Solo EXL.

>[!INFO]
>
>Esta es una nota informativa. Solo EXL.

>[!ERROR]
>
>Esta es una nota de error. Solo EXL.

>[!SUCCESS]
>
>Esta es una nota de éxito. Solo EXL.

>[!MORELIKETHIS]
>
>* Página 1
>* Página 2

## Insignias

Un distintivo es una etiqueta de color que se utiliza como indicador de contenido. Por ejemplo, puede agregar una insignia para marcar un artículo como _Beta_ o una sección como _Premium_. Puede cambiar el color de un distintivo y asociar una dirección URL con información sobre herramientas.

[!BADGE Ejemplo de insignia]

Existen dos tipos of insignias, cada una con una sintaxis diferente:

* **Metadatos** - Muestra el distintivo cerca de la parte superior de una página
* **En línea** - Muestra el distintivo donde se encuentra la sintaxis

### Distintivos de metadatos

Si agrega sintaxis de distintivo en los metadatos, colocará un distintivo encima del título de la página (H1) en el artículo.

Puede asignar nombres a los distintivos, por ejemplo, utilizando _distintivo1_ o _distintivo2_. O puede ser más creativo (siempre y cuando el nombre comience por ) _distintivo_).

Ejemplos de metadatos:

```
badgePremium: label="Premium" type="Positive" url="https://www.premium-product.com" tooltip="Download Premium"
badgeExam: label="Exam ADO-E903" type="neutral"
```

* **badgePremium:** Este ejemplo muestra un distintivo Premium con una dirección URL y información del objeto.

* **badgeExam:** Este ejemplo muestra un distintivo oscuro con un número de ID de examen.

#### Distintivos en línea

Especifique la información del distintivo en su propia línea o en un encabezado, tabla u otro elemento de página.

Esta es la sintaxis de un distintivo en línea con una etiqueta beta, un color azul, una dirección URL y información del objeto:

`[!BADGE Beta]{type=Informative url="https://www.example.com" tooltip="Go to example.com"}`

### Colores de distintivo disponibles

Las insignias utilizan colores definidos en Espectro de Adobe:

| Tipo | Insignia |
|---|---|
| Informativo (predeterminado) | [!BADGE Beta]{type=Informative url="https://www.example.com"} |
| Positiva | [!BADGE Nueva función]{type=Positive url="https://www.example.com" tooltip="Vaya a example.com"} |
| Negativa | [!BADGE Suspendido]{type=negative tooltip="Esta función acaba ahora con su vida útil"} |
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

### Requisitos para las insignias

* Solo se permiten dos insignias en los metadatos. Esta regla se puede configurar, por lo que debe saber si necesita una excepción.
* Solo se requiere la etiqueta del distintivo. El `type`, `url`, y `tooltip` Los parámetros de son opcionales. El `type` determina el color. El `url` El parámetro permite a los usuarios hacer clic en el distintivo para abrir un artículo o una página. El `tooltip` El parámetro muestra el texto de la información del objeto al pasar el ratón.
* Añadir un distintivo a la `TOC.md` Este archivo muestra el distintivo de cada artículo de la guía. Si especifica una dirección URL para que el distintivo salte a un artículo, asegúrese de utilizar un vínculo raíz (por ejemplo, `/help/guide/article.md`) no es un vínculo relativo (por ejemplo, `article.md`) para tener en cuenta los artículos de diferentes carpetas.
* Adición de un distintivo a `metadata-new.md` muestra el distintivo de cada artículo de un repositorio.
* Para los distintivos de metadatos, asegúrese de que todos los valores estén entre comillas. Para insignias en línea, asegúrese de que `url` y `tooltip` están entre comillas.
* Los valores de tipo válidos incluyen *Informativo* (predeterminado, azul), *Positivo* (verde), *Negativo* (rojo), *Neutro* (gris oscuro), y *Precaución* (amarillo).
* Las etiquetas de distintivo están localizadas.
* Si se especifican varios distintivos de metadatos, estos se muestran en orden alfabético en función del nombre del distintivo, como `badge1:` o `badgeWeb`.
* Si desea que la dirección URL se abra en una pestaña nueva, utilice esta sintaxis:

  ```
  [!BADGE Open in new tab]{type=Negative url="https://www.adobe.com newtab=true" tooltip="Open adobe.com in new tab"}
  ```

  Procesado:

  [!BADGE Abrir en ficha nueva]{type=Negative url="https://www.adobe.com newtab=true" tooltip="Abra adobe.com en una ficha nueva"}

## Resaltado de texto

El equipo de Workfront solicitó poder utilizar el resaltado amarillo para indicar la previsualización de las próximas funciones. Así es como funciona.

Ejemplo 1:

```
This entire paragraph should NOT be highlighted. <span class="preview"> This word is **bold** inside a highlighted sentence.</span> And this is just the last sentence.
```

Procesado:

NO se debe resaltar todo este párrafo. <span class="preview"> Esta palabra es **negrita** dentro de una frase resaltada.</span> Y esta es solo la última oración.

Ejemplo 2:

```
Highlighting should start after this paragraph.

<div class="preview">

Start of DIV.

This is a new paragraph, then an image

![image](/help/home/assets/analytics-icon-24.png)

Last highlighted item.

</div>

Not highlighted
```

Procesado:

El resaltado debe comenzar después de este párrafo.

<div class="preview">

Inicio de DIV.

Este es un nuevo párrafo, luego una imagen

![image](/help/home/assets/analytics-icon-24.png)

Último elemento resaltado.

</div>

No resaltado

## Resaltado de sintaxis para bloques de código

Experience League admite el resaltado de sintaxis para bloques de código. Asegúrese de especificar un idioma como `java` después del conjunto de comillas invertidas de apertura para asegurarse de que la sintaxis esté resaltada correctamente. Para ver una lista de idiomas válidos, consulte [https://prismjs.com](https://prismjs.com/#supported-languages). Si falta algún idioma, por favor registre un ticket jira.

### Numeración de líneas en bloques de código

Añadir `{line-numbers="true"}` después del idioma para habilitar la numeración de líneas.

Ejemplo con números de línea (&grave;&grave;&grave;`html {line-numbers="true"}`):

```html {line-numbers="true"}
<!DOCTYPE html>
<html>
<body>

<h1>My First Heading</h1>
<p>My first paragraph.</p>

</body>
</html>
```

**Iniciar numeración en línea _**

Añadir `start-number="n"` después de la sintaxis del número de línea para iniciar la numeración en un número distinto de 1.

Ejemplo con nueva línea de inicio (&grave;&grave;&grave;`html {line-numbers="true" start-line="7"}`):

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

Añadir `highlight="n"` después de la sintaxis del número de línea para resaltar filas dentro de un bloque de código. Especificación `11-13, 16` resaltará las líneas 11 a 13 y 16.

Ejemplo con resaltado de líneas (&grave;&grave;&grave;`html {line-numbers="true" start-line="7" highlight="11-13, 16"}`):

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
