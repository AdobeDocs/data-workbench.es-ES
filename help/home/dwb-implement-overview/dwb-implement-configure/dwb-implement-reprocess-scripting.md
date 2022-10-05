---
description: Esta sección es una guía rápida que le proporciona los pasos mínimos necesarios para configurar y programar scripts para que reprocesen semanalmente sus archivos de registro. Se puede utilizar como guía de referencia para configurar o modificar los perfiles.
title: Secuencia de comandos para reprocesamiento semanal
uuid: d3cd163d-6129-4883-ac7c-b2f75b5eb247
exl-id: f1b6f12e-629e-47c7-aa15-41f76d1c3192
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '434'
ht-degree: 2%

---

# Secuencia de comandos para reprocesamiento semanal{#scripting-to-weekly-reprocess}

{{eol}}

Esta sección es una guía rápida que le proporciona los pasos mínimos necesarios para configurar y programar scripts para que reprocesen semanalmente sus archivos de registro. Se puede utilizar como guía de referencia para configurar o modificar los perfiles.

## ¿Qué es el reprocesamiento? {#section-7e335aacc199488592e78a835e2649fe}

Cargar los datos a DWB según los cambios en las fuentes de datos, las fuentes de datos sin conexión o el período de tiempo. La secuencia de comandos reprocesará el parámetro de fecha de inicio en *Log Processing.cfg* archivo.

## Requisitos previos {#section-804acce5df4942469c9313535627038a}

ID del grupo de informes, los datos del número de meses deben estar disponibles en el DWB. La carpeta Perl64 debe estar disponible en su C:\ drive.

## Volver a procesar registros {#section-565d3e1f0df14127a97d9beecd14f02f}

Proporcionar los detalles anteriores (requisitos previos) en el script de comandos de windows *Reprocesar.bat* disponible en la carpeta *\scripts\Procesamiento de registros* en el servidor FSU principal.

Esta secuencia de comandos llama internamente a dos secuencias de comandos específicas del cliente: Uno para volver a procesar los datos y otro para las alertas de correo electrónico. Estas dos secuencias de comandos también están disponibles en la sección *\scripts\Procesamiento de registros* carpeta.

La secuencia de comandos cambiará los parámetros de reprocesamiento en la variable *Log Processing.cfg* archivo.

## Ventana móvil para registros {#section-ed5f44d890b34523ab33da7aa0ae3990}

Proporcionar detalles (requisitos previos) en el script de comandos de windows *logprocessingdate.bat* disponible en la carpeta *\scripts\Script* en el servidor de FSU de creación. Esta secuencia de comandos llama internamente a dos secuencias de comandos específicas del cliente: Una para configurar la fecha de inicio de los registros y otra para las alertas de correo electrónico. Estas dos secuencias de comandos también están disponibles en* \scripts\Scripts*

Proporcione el ID del grupo de informes y el número de meses en el archivo logprocessingdate.bat*.

La secuencia de comandos cambiará el parámetro de fecha de inicio en *Log Processing.cfg*.

>[!NOTE]
>
>Si la variable *Anuncio* no está disponible, siga el proceso que se muestra a continuación para copiar la *Anuncio* y realice cambios en los archivos anteriores utilizando detalles específicos del cliente. Y proporcione su dirección de correo electrónico para obtener una alerta en caso de error.

## Programación de scripts {#section-063cf0c755dc47d28d60947d8d43d0e9}

Siga estos pasos para programar las secuencias de comandos en el programador de tareas de Windows.

1. Programe la secuencia de comandos en el programador de tareas de Windows.

   * Abra Programador de tareas: Haga clic con el botón derecho en la variable **Biblioteca del Programador de tareas** y haga clic en **Crear tarea**.

   * En el **General** ficha proporcionar un nombre de tarea y seleccionar **Opciones**.

   * En el **Déclencheur** , haga clic en **Nuevo** y se abrirá una nueva ventana.

   * En el **Acciones** , haga clic en **Nuevo** y se abrirá una nueva ventana. A continuación, proporcione los detalles de la secuencia de comandos y otras opciones. (Iniciar en tendrá una ruta donde se coloca el script).

1. Validación: Haga clic con el botón derecho del ratón y ejecute el trabajo y compruebe los cambios en la *Log processing.cfg* archivo. Se enviará un correo electrónico al ID de correo electrónico proporcionado en la secuencia de comandos.
