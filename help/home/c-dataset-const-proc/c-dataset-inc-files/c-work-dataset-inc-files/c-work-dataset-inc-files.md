---
description: Los archivos de inclusión de conjunto de datos proporcionan una manera flexible de configurar el conjunto de datos.
title: Uso de archivos de inclusión de conjunto de datos
uuid: 258226c4-22e5-4d9d-9044-8312709e0460
exl-id: 94044c85-030c-4912-9546-d4a34b4115e0
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '238'
ht-degree: 4%

---

# Uso de archivos de inclusión de conjunto de datos{#working-with-dataset-include-files}

Los archivos de inclusión de conjunto de datos proporcionan una manera flexible de configurar el conjunto de datos.

Dentro de cada archivo, puede definir tantos campos, transformaciones o dimensiones como desee y puede organizar los archivos de inclusión en función del perfil heredado al que pertenezcan. Al configurar el conjunto de datos, tiene la opción de editar los archivos de inclusión del conjunto de datos proporcionados con los perfiles internos para la aplicación de Adobe o de crear nuevos archivos de inclusión de conjuntos de datos para cualquier perfil heredado que cree.

Al editar los parámetros de un archivo de inclusión de conjunto de datos para un perfil interno y guardar el archivo actualizado en el perfil del conjunto de datos o un perfil heredado que haya creado, se anula la configuración original del archivo. Adobe recomienda editar un archivo de inclusión de conjunto de datos para un perfil interno siempre que necesite realizar cambios menores en el contenido del conjunto de datos, como cambiar un parámetro Condition o la configuración predeterminada de un parámetro. Consulte [Edición de archivos de inclusión de conjuntos de datos existentes](../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-work-dataset-inc-files/t-edit-ex-dataset-inc-files.md#task-456c04e38ebc425fb35677a6bb6aa077). Sin embargo, cuando desea especificar un nuevo campo para pasar del procesamiento de registros a la transformación, actualizar o crear nuevos campos mediante transformaciones, o definir dimensiones ampliadas, es mejor crear un nuevo archivo de inclusión de conjunto de datos. Consulte [Creación de nuevos archivos de inclusión de conjunto de datos](../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-work-dataset-inc-files/t-create-new-dataset-inc-files.md#task-b29f30605c374a6ca747ac843337b06e). Puede editar el archivo que cree cada vez que desee o como desee.
