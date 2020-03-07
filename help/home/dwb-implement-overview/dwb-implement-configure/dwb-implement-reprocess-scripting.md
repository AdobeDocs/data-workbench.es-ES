---
description: Esta sección es una guía rápida que le proporciona los pasos mínimos requeridos para configurar y programar scripts para volver a procesar semanalmente los archivos de registro. Se puede utilizar como guía de referencia para configurar o modificar los perfiles.
title: Secuencia de comandos para reprocesamiento semanal
uuid: d3cd163d-6129-4883-ac7c-b2f75b5eb247
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Secuencia de comandos para reprocesamiento semanal{#scripting-to-weekly-reprocess}

Esta sección es una guía rápida que le proporciona los pasos mínimos requeridos para configurar y programar scripts para volver a procesar semanalmente los archivos de registro. Se puede utilizar como guía de referencia para configurar o modificar los perfiles.

## ¿Qué es el reprocesamiento? {#section-7e335aacc199488592e78a835e2649fe}

Cargar los datos en DWB en función de los cambios en las fuentes de datos, las fuentes de datos sin conexión o el período de tiempo. La secuencia de comandos reprocesará el parámetro de fecha de inicio en el archivo *Log Processing.cfg* .

## Requisitos previos {#section-804acce5df4942469c9313535627038a}

ID del grupo de informes, número de datos del mes que deben estar disponibles en DWB. La carpeta Perl64 debe estar disponible en su C:\ drive.

## Volver a procesar registros {#section-565d3e1f0df14127a97d9beecd14f02f}

Proporcione los detalles anteriores (requisitos previos) en el script de comando de Windows *Reprocess.bat* , disponible en la carpeta *\scripts\Log Processing* del servidor FSU principal.

Esta secuencia de comandos llamará internamente a dos secuencias de comandos específicas del cliente: Uno para volver a procesar los datos y otro para la alerta de correo electrónico. Estas dos secuencias de comandos también están disponibles en la carpeta *\scripts\Log Processing* .

La secuencia de comandos cambiará los parámetros de reprocesamiento en el archivo *Log Processing.cfg* .

## Ventana móvil para registros {#section-ed5f44d890b34523ab33da7aa0ae3990}

Proporcione detalles (requisitos previos) en el comando windows script *logprocessingdate.bat* disponible en la carpeta *\scripts\Scripository* del servidor FSU de creación. Esta secuencia de comandos llamará internamente a dos secuencias de comandos específicas del cliente: Uno para configurar la fecha de inicio de los registros y otro para las alertas de correo electrónico. Estas dos secuencias de comandos también están disponibles en* \scripts\Scripository*

Proporcione la ID del grupo de informes y el número de meses en el archivo * logprocessingdate.bat*.

La secuencia de comandos cambiará el parámetro de fecha de inicio en *Log Processing.cfg*.

>[!NOTE]
>
>Si la carpeta *Scripository* no está disponible, siga el proceso que se muestra a continuación para copiar la carpeta *Scripository* y realizar cambios en los archivos anteriores utilizando los detalles específicos del cliente. Y proporcione su dirección de correo electrónico para obtener una alerta en caso de error.

## Programación de secuencias de comandos {#section-063cf0c755dc47d28d60947d8d43d0e9}

Siga estos pasos para programar las secuencias de comandos en el programador de tareas de Windows.

1. Programe la secuencia de comandos en el programador de tareas de Windows.

   * Abrir programador de tareas: Haga clic con el botón secundario en la biblioteca **del programador de** tareas y haga clic en **Crear tarea**.

   * En la ficha **General** , proporcione un nombre de tarea y seleccione **Opciones**.

   * En la ficha **Desencadenadores** , haga clic en **Nuevo** y se abrirá una nueva ventana.

   * En la ficha **Acciones** , haga clic en **Nuevo** y se abrirá una nueva ventana. A continuación, proporcione los detalles de la secuencia de comandos y otras opciones. (Iniciar en tendrá una ruta donde se coloca la secuencia de comandos).

1. Validación: Haga clic con el botón derecho y ejecute el trabajo y compruebe los cambios en el archivo *Log processing.cfg* . Se enviará un correo electrónico a la ID de correo electrónico proporcionada en la secuencia de comandos.

