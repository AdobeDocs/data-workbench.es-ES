---
description: Los archivos de inclusión de datos proporcionan una manera flexible de configurar el conjunto de datos.
solution: Analytics
title: Uso de archivos de inclusión de conjunto de datos
topic: Data workbench
uuid: 258226c4-22e5-4d9d-9044-8312709e0460
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Uso de archivos de inclusión de conjunto de datos{#working-with-dataset-include-files}

Los archivos de inclusión de datos proporcionan una manera flexible de configurar el conjunto de datos.

Dentro de cada archivo, puede definir tantos campos, transformaciones o dimensiones como desee y puede organizar los archivos de inclusión en función del perfil heredado al que pertenecen. Al configurar el conjunto de datos, tiene la opción de editar los archivos de inclusión de conjuntos de datos que se proporcionan con los perfiles internos de la aplicación de Adobe o crear nuevos archivos de inclusión de conjuntos de datos para cualquier perfil heredado que cree.

Al editar los parámetros de un archivo de inclusión de conjuntos de datos para un perfil interno y guardar el archivo actualizado en el perfil del conjunto de datos o en un perfil heredado que se cree, se anula la configuración original del archivo. Adobe recomienda editar un archivo de inclusión de conjuntos de datos para un perfil interno siempre que necesite realizar cambios menores en el contenido del conjunto de datos, como cambiar un parámetro Condition o la configuración predeterminada de un parámetro. Consulte [Edición de conjuntos de datos existentes Incluir archivos](../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-work-dataset-inc-files/t-edit-ex-dataset-inc-files.md#task-456c04e38ebc425fb35677a6bb6aa077). Sin embargo, si desea especificar un nuevo campo para pasar del procesamiento de registros a la transformación, actualizar o crear nuevos campos mediante transformaciones o definir dimensiones ampliadas, es mejor crear un nuevo archivo de inclusión de conjuntos de datos. Consulte [Creación de nuevos conjuntos de datos para incluir archivos](../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-work-dataset-inc-files/t-create-new-dataset-inc-files.md#task-b29f30605c374a6ca747ac843337b06e). Puede editar el archivo que cree cada vez que desee o como desee.
