---
description: Puede utilizar el parámetro Oculto o el parámetro Mostrar para ocultar las dimensiones extendidas de modo que no se muestren en el menú de dimensiones del área de trabajo de datos.
solution: Analytics
title: Ocultar dimensiones extendidas
topic: Data workbench
uuid: c32f47ad-0246-4611-b54c-0c9f0eb396bd
translation-type: tm+mt
source-git-commit: 27600561841db3705f4eee6ff0aeb8890444bbc9

---


# Ocultar dimensiones extendidas{#hiding-extended-dimensions}

Puede utilizar el parámetro Oculto o el parámetro Mostrar para ocultar las dimensiones extendidas de modo que no se muestren en el menú de dimensiones del área de trabajo de datos.

Cuando se introduce la configuración adecuada para cualquiera de los parámetros, el nombre de la dimensión no aparece en el menú del área de trabajo de datos, pero aún está en el perfil y disponible para su uso. Cualquier usuario del área de trabajo de datos puede mostrar temporalmente las dimensiones ocultas estableciendo el parámetro Mostrar todo en el [!DNL Insight.cfg] archivo en true.

Para obtener más información sobre el parámetro Mostrar todo, consulte el apéndice sobre los parámetros de configuración del área de trabajo de datos en la Guía *del usuario del área de trabajo de* datos.

Las siguientes secciones describen cómo utilizar los parámetros Oculto y Mostrar para ocultar las dimensiones extendidas.

* [Ocultar dimensiones extendidas con el parámetro oculto](../../../../home/c-dataset-const-proc/c-dataset-config-tools/c-hide-dataset-comp/c-hide-ex-dim.md#section-7167a6f6241a4bc78f2f322e048d65cf)
* [Ocultar dimensiones extendidas con el parámetro Mostrar](../../../../home/c-dataset-const-proc/c-dataset-config-tools/c-hide-dataset-comp/c-hide-ex-dim.md#section-4dceb1079c7f40d2bffc686d1f73f8ad)

## Ocultar dimensiones extendidas con el parámetro oculto {#section-7167a6f6241a4bc78f2f322e048d65cf}

El parámetro Oculto es un parámetro opcional que se puede utilizar al definir dimensiones extendidas en [!DNL Transformation Dataset Configuration] archivos.

1. Abra [!DNL Transformation Dataset Configuration] los archivos en los que se define la dimensión ampliada que desea ocultar. Consulte [Edición de conjuntos de datos existentes Incluir archivos](../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-work-dataset-inc-files/t-edit-ex-dataset-inc-files.md#task-456c04e38ebc425fb35677a6bb6aa077).

1. Busque el parámetro Oculto para la dimensión deseada en la ventana de configuración y escriba *true*.
1. Guarde el archivo localmente y, a continuación, guárdelo en el perfil adecuado del servidor. Consulte [Edición de conjuntos de datos existentes Incluir archivos](../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-work-dataset-inc-files/t-edit-ex-dataset-inc-files.md#task-456c04e38ebc425fb35677a6bb6aa077).

El conjunto de datos se retransforma, tras lo cual la dimensión ampliada no aparece en el menú de dimensiones del área de trabajo de datos. Para obtener más información sobre el parámetro Oculto, consulte Dimensiones [extendidas](../../../../home/c-dataset-const-proc/c-ex-dim/c-abt-ex-dim.md).

Si cambia la configuración del parámetro Oculto, debe volver a transformar el conjunto de datos para que el cambio surta efecto.

## Ocultar dimensiones extendidas con el parámetro Mostrar {#section-4dceb1079c7f40d2bffc686d1f73f8ad}

El parámetro Show no es uno de los parámetros disponibles para definir dimensiones extendidas en [!DNL Transformation Dataset Configuration] archivos. En su lugar, el parámetro se define en los [!DNL .dim] archivos para cualquier dimensión derivada que se cree. Por lo tanto, para utilizar el parámetro Mostrar para ocultar una dimensión extendida, primero debe crear una dimensión derivada basada en la dimensión extendida, tal como se describe en el siguiente procedimiento:

1. Utilice un editor de texto como Bloc de notas para crear un archivo vacío llamado &lt;nombre *de* dimensión>.dim El nombre del archivo debe coincidir con el nombre de la dimensión que desea ocultar. Por ejemplo, para ocultar la dimensión Página siguiente, debe crear un [!DNL Next Page.dim] archivo.

1. Agregue el siguiente texto al archivo:

   * entity = ref: wdata/model/dim/Parent/+name
   * show = bool: false

1. Guarde el archivo en el directorio Dimensiones del perfil. Si lo desea, puede guardar el archivo en un subdirectorio.

Cuando se utiliza el parámetro Mostrar para ocultar una dimensión extendida, no es necesario retransformar el conjunto de datos para que el cambio surta efecto. Puede elegir ocultar o mostrar la dimensión en la versión local del perfil (es decir, puede guardar el [!DNL .dim] archivo en la carpeta Usuario) o puede guardar el [!DNL .dim] archivo en el servidor para que lo utilicen otros usuarios del perfil.

También puede utilizar el parámetro Mostrar para ocultar métricas y filtros. Para obtener más información, consulte el capítulo Configuración de interfaz y características de análisis en la Guía *del usuario de Área de trabajo de* datos.
