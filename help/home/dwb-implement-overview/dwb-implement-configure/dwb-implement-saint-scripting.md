---
description: Esta sección explica el script de Saint Scrubber.
title: Secuencia de comandos para la barra de desplazamiento SAINT
uuid: 2e5aa6f2-dadb-48a6-8443-69396530587c
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Secuencia de comandos para la barra de desplazamiento SAINT{#scripting-for-the-saint-scrubber}

Esta sección explica el script de Saint Scrubber.

## Descripción general de la clasificación SAINT {#section-b840a99f10684bb4b58e844a515d0d79}

La clasificación también se conoce por el acrónimo SAINT para la Herramienta de nombres e importación de atributos de SiteCatalyst.

Cuando &quot;clasificamos&quot; una variable de SiteCatalyst, se establece una relación entre una variable y los metadatos relacionados con esa variable. Las clasificaciones se utilizan con mayor frecuencia en el área Campañas, por lo que las voy a utilizar para explicarlas. La mayoría de los clientes envían tráfico de campaña a su sitio mediante un código de seguimiento. Este código de seguimiento es un identificador que puede representar una palabra clave específica comprada en Google, como &quot;goog123&quot;. Este identificador se pasa a la variable s.campaign para que pueda ver qué eventos de éxito del sitio se producen después de que los visitantes ingresan al sitio desde ese código de campaña.

Pero, ¿qué sucede si, en lugar de ver Campañas sólo por el código de seguimiento, desea ver los resultados de las campañas por motor de búsqueda, palabra clave o canal de campaña? ¿Tiene que crear una nueva variable de conversión para el motor de búsqueda, otra para la palabra clave y otra para el canal de campaña? Si es así, ¡utilizaría muchas de sus cincuenta variables solo en Campañas! Afortunadamente, puede usar las clasificaciones para facilitar su vida. Dado que cada código de seguimiento puede tener un motor de búsqueda, una palabra clave o un canal de campaña, simplemente puede crear tres clasificaciones de la variable Campañas para representarlas. Básicamente, usted le dice a SiteCatalyst que existe una relación directa entre la variable Campañas y estos tres otros valores de &quot;metadatos&quot;. Al hacer esto, SiteCatalyst le permitirá fraccionar y fraccionar los eventos de éxito del sitio según las cuatro variables sin etiquetado adicional.

## Secuencia de comandos de depurador SAINT en DWB {#section-a42bb9236d7d49bfabdc48d39ece3c3b}

Esta secuencia de comandos se utiliza cuando se introducen datos de clasificación SAINT en DWB. La secuencia de comandos *SaintScrubber.dat* se coloca normalmente en la carpeta *\Scripts\Scripository* de la FSU.

El propósito principal de esta secuencia de comandos es eliminar el encabezado de los archivos de clasificación de `<discoiqbr>` SAINT. Además, cuenta el número si la columna mencionada en la línea del encabezado de columna y comprueba todas las filas de datos. Si hay filas con un número menor o mayor de columnas, se eliminan estas filas del archivo.

El archivo *SaintScrubber.dat* llama internamente al *script saint_scrubber.pl. A continuación se detallan los detalles de este archivo de secuencias de comandos:

Ruta: *E:\Scripts\Scripository\Library\Perl*

Argumentos de secuencias de comandos:

1. Carpeta de entrada (obligatoria): source_directory
1. Carpeta de salida (obligatoria): destination_directory
1. Delimitador (obligatorio): delimiter
1. Rechazar carpeta (opcional)(el parámetro se puede dejar en blanco o omitir en la línea de comandos)
1. Carpeta de registro (opcional)(el parámetro se puede dejar en blanco o omitir en la línea de comandos)

Pasos realizados en la secuencia de comandos Perl:

1. Reemplazar las fuentes de formularios escapados, las líneas nuevas, los retornos de carro y las fichas con espacios.
1. Elimine los bytes dobles que se interpretan como un carácter de control en la BMP UTF-8 (Plano multilingüe básico) excepto para:

   * 9, ficha horizontal
   * Alimentación de 10 líneas
   * 12 fuente de formulario
   * 13 devolución de carro
   * Utilice la palabra clave pipe como delimitador para| p. ej.: barra vertical delimitadora
   * Eliminar otros caracteres problemáticos
   * Después del desplazamiento anterior, coloque cualquier línea con un número de columnas distinto al de la primera línea de datos (no en blanco o comentario)
   * Admitir archivos de rechazo opcionales para mantener las líneas rechazadas en lugar de simplemente omitirlas
   * Admite la carpeta de entrada recursiva; generar carpetas de salida de la misma estructura
   * Mover los archivos de entrada procesados a subcarpetas procesadas para que la secuencia de comandos no repita el esfuerzo cuando se ejecute de nuevo en la misma carpeta de entrada existente
   * Reconocer la fecha en los nombres de archivo del área de trabajo; ordene el procesamiento primero por fecha y después por alfa, independientemente del nombre de la carpeta. Esto garantizará que la secuencia sea correcta independientemente del tipo de archivo del área de trabajo (ecom, non-ecom) o la ID del grupo de informes (si está procesando varios grupos de informes en un único conjunto de datos de Insight).
   * Alertas de correo electrónico de asistencia `<discoiqbr>`

