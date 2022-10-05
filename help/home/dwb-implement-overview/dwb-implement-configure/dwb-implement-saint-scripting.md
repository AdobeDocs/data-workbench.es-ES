---
description: En esta sección se explica el script Saint Scrubber.
title: Secuencia de comandos para la barra de desplazamiento SAINT
uuid: 2e5aa6f2-dadb-48a6-8443-69396530587c
exl-id: 5f6d92b1-baaa-4d67-a1c2-ce7d51affb17
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '613'
ht-degree: 1%

---

# Secuencia de comandos para la barra de desplazamiento SAINT{#scripting-for-the-saint-scrubber}

{{eol}}

En esta sección se explica el script Saint Scrubber.

## Descripción general de la clasificación de SAINT {#section-b840a99f10684bb4b58e844a515d0d79}

La clasificación también la conoce el SAINT de acrónimos para la Herramienta de nombres e importación de atributos de SiteCatalyst.

Cuando &quot;clasificamos&quot; una variable de SiteCatalyst, se establece una relación entre una variable y los metadatos relacionados con esa variable. Las clasificaciones se usan con mayor frecuencia en el área Campañas , por lo que utilizaré esto como una forma de explicarlas. La mayoría de los clientes envían tráfico de campaña a su sitio mediante un código de seguimiento. Este código de seguimiento es un identificador que puede representar una palabra clave específica comprada en Google, como &quot;goog123&quot;. Este identificador se pasa a la variable s.campaign para que pueda ver qué eventos de éxito del sitio se producen después de que los visitantes accedan al sitio desde ese código de campaña.

Pero, ¿qué sucede si, en lugar de ver Campañas solo por el código de seguimiento, desea ver los resultados de la campaña por Motor de búsqueda, Palabra clave o Canal de campaña? ¿Tiene que crear una nueva variable de conversión para el motor de búsqueda, otra para la palabra clave y otra para el canal de campaña? Si es así, ¡utilizaría muchas de sus cincuenta variables solo en Campañas! Afortunadamente, puede usar las clasificaciones para facilitar su vida. Dado que cada código de seguimiento puede tener un motor de búsqueda, una palabra clave o un canal de campaña, simplemente puede crear tres clasificaciones de la variable Campañas para representarlas. Básicamente, le está diciendo a SiteCatalyst que existe una relación directa entre la variable Campañas y estos otros tres valores de &quot;metadatos&quot;. Al hacerlo, el SiteCatalyst le permitirá cortar y fragmentar los eventos de éxito del sitio por las cuatro variables sin necesidad de etiquetado adicional.

## Secuencia de comandos de depurador de SAINT en DWB {#section-a42bb9236d7d49bfabdc48d39ece3c3b}

Esta secuencia de comandos se utiliza cuando se introducen datos de clasificación de SAINT en DWB. La secuencia de comandos *SaintScrubber.dat* normalmente se coloca debajo de la variable *\Scripts\Repositorio* en la FSU.

El propósito principal de esta secuencia de comandos es eliminar el encabezado de la `<discoiqbr>` Archivos de clasificación del SAINT. Además, cuenta el número si la columna mencionada en la línea del encabezado de la columna y comprueba todas las filas de datos. Si hay filas con un número menor o mayor de columnas, quitará estas filas del archivo.

La variable *SaintScrubber.dat* llama internamente al *script saint_eliminador.pl. A continuación se muestran los detalles de este archivo de secuencia de comandos:

Ruta: *E:\Scripts\Scripository\Library\Perl*

Argumentos de secuencia de comandos:

1. Carpeta de entrada (obligatoria): source_directory
1. Carpeta de salida (obligatorio) : destination_directory
1. Delimitador (obligatorio) : delimiter
1. Rechazar carpeta (opcional) (el parámetro puede dejarse en blanco o omitirse en la línea de comandos)
1. Carpeta de registro (opcional) (el parámetro se puede dejar en blanco o omitir en la línea de comandos)

Pasos realizados en la secuencia de comandos Perl:

1. Reemplace las fuentes de formularios de escape, las líneas nuevas, los retornos de carro y las pestañas con espacios.
1. Elimine los bytes dobles que se interpretan como un carácter de control en la BMP UTF-8 (Plano Multilingüe Básico) excepto para:

   * 9 ficha horizontal
   * Fuente de 10 líneas
   * 12 fuente de formulario
   * 13 retorno de carro
   * Utilice la palabra clave de barra vertical como delimitador para | p. ej.: barra vertical delimitadora
   * Eliminar otros caracteres problemáticos
   * Después de la anulación anterior, suelte cualquier línea con un número de columnas distinto de la primera línea de datos (no en blanco ni comentario)
   * Compatibilidad con archivos de rechazo opcionales para mantener líneas rechazadas en lugar de simplemente omitirlas
   * Admite la carpeta de entrada recursiva; generar carpetas de salida de la misma estructura
   * Mover los archivos de entrada procesados a subcarpetas procesadas para que el script no repita el esfuerzo cuando se ejecute de nuevo en la misma carpeta de entrada existente
   * Reconocer la fecha en los nombres de archivo del área de trabajo; ordene el procesamiento primero por fecha y después por alfa, independientemente del nombre de la carpeta. Esto garantizará que la secuencia sea correcta independientemente del tipo de archivo de área de trabajo (ecom, non-ecom) o ID de grupo de informes (si está procesando varios grupos de informes en un único conjunto de datos de Insight).
   * Asistencia de alertas de correo electrónico `<discoiqbr>`
