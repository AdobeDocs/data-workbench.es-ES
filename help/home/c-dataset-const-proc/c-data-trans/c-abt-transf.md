---
description: Las transformaciones permiten extraer información disponible en los archivos de datos y manipularla en un formulario más útil.
title: Acerca de las transformaciones
uuid: 9366f607-741d-4512-9e1b-4165f4291246
exl-id: 9bd533ef-a87e-400a-9bb0-5af1851cca0a
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '307'
ht-degree: 1%

---

# Acerca de las transformaciones{#about-transformations}

Las transformaciones permiten extraer información disponible en los archivos de datos y manipularla en un formulario más útil.

Las transformaciones funcionan en las entradas de registro (puede considerar las entradas de registro como filas de datos) en sus fuentes de registro. Para cada fila de datos, la transformación toma el valor del campo de entrada especificado, realiza un conjunto de pasos de procesamiento y registra el resultado en el campo de salida especificado. Puede definir transformaciones que se ejecutarán durante la fase de procesamiento de registros o de transformación del proceso de construcción del conjunto de datos:

* **Durante el procesamiento del registro:** las transformaciones ejecutadas durante la fase de procesamiento del registro de la construcción del conjunto de datos se aplican a cada registro de datos de evento (entrada de registro) para actualizar los campos de registro existentes o producir nuevos campos. Los resultados de las transformaciones se utilizan junto con las condiciones de entrada de registro para evaluar qué entradas de registro se filtran fuera del conjunto de datos durante el procesamiento del registro.
* **Durante la transformación:** las transformaciones ejecutadas durante la fase de transformación de la construcción del conjunto de datos funcionan en los campos de datos pasados desde el procesamiento de registros para crear dimensiones ampliadas que puede utilizar en sus análisis. Consulte [Dimension extendidos](../../../home/c-dataset-const-proc/c-ex-dim/c-abt-ex-dim.md).

>[!NOTE]
>
>La entrada de datos para la transformación a partir del procesamiento del registro se ordena por tiempo y se agrupa por el ID de seguimiento en los datos de origen. Varias transformaciones requieren que los datos estén en este formulario y funcionen solo cuando se definen en durante la transformación.

Los cambios en las transformaciones deben realizarse con cuidado. Las transformaciones no afectan a qué entradas de registro fluyen en el proceso de construcción del conjunto de datos, pero sí afectan a los resultados presentados. Esto permite realizar cambios en lo que se analiza sin cambiar los datos en los que se basa el análisis. Sin embargo, los cambios en las transformaciones pueden alterar fundamentalmente los valores producidos en los análisis.
