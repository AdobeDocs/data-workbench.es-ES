---
description: Puede utilizar el parámetro Oculto o el parámetro Mostrar para ocultar las dimensiones extendidas de modo que no se muestren en el menú Dimensión de Data Workbench.
title: Ocultar dimensiones extendidas
uuid: c32f47ad-0246-4611-b54c-0c9f0eb396bd
exl-id: 5baccf39-6f3b-40a1-b1c0-a8e5d6a61211
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '535'
ht-degree: 1%

---

# Ocultar dimensiones extendidas{#hiding-extended-dimensions}

Puede utilizar el parámetro Oculto o el parámetro Mostrar para ocultar las dimensiones extendidas de modo que no se muestren en el menú Dimensión de Data Workbench.

Cuando se introduce la configuración adecuada para cualquiera de los parámetros, el nombre de la dimensión no aparece en el menú de Data Workbench, pero sigue en el perfil y está disponible para su uso. Cualquier usuario de Data Workbench puede mostrar temporalmente las dimensiones ocultas estableciendo el parámetro Mostrar todo en el archivo [!DNL Insight.cfg] en true.

Para obtener más información sobre el parámetro Mostrar todo , consulte el apéndice sobre los parámetros de configuración de Data Workbench en la *Guía del usuario de Data Workbench*.

En las secciones siguientes se describe cómo utilizar los parámetros Oculto y Mostrar para ocultar dimensiones extendidas.

* [Ocultar Dimension extendidos mediante el parámetro oculto](../../../../home/c-dataset-const-proc/c-dataset-config-tools/c-hide-dataset-comp/c-hide-ex-dim.md#section-7167a6f6241a4bc78f2f322e048d65cf)
* [Ocultar Dimension extendidos mediante el parámetro Mostrar](../../../../home/c-dataset-const-proc/c-dataset-config-tools/c-hide-dataset-comp/c-hide-ex-dim.md#section-4dceb1079c7f40d2bffc686d1f73f8ad)

## Ocultar Dimension extendidos usando el parámetro oculto {#section-7167a6f6241a4bc78f2f322e048d65cf}

El parámetro Oculto es un parámetro opcional que se puede utilizar al definir dimensiones extendidas en archivos [!DNL Transformation Dataset Configuration].

1. Abra archivos [!DNL Transformation Dataset Configuration] en los que se defina la dimensión ampliada que desea ocultar. Consulte [Edición de archivos de inclusión de conjuntos de datos existentes](../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-work-dataset-inc-files/t-edit-ex-dataset-inc-files.md#task-456c04e38ebc425fb35677a6bb6aa077).

1. Busque el parámetro Hidden para la dimensión deseada en la ventana de configuración y escriba *true*.
1. Guarde el archivo localmente y, a continuación, guárdelo en el perfil correspondiente del servidor. Consulte [Edición de archivos de inclusión de conjuntos de datos existentes](../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-work-dataset-inc-files/t-edit-ex-dataset-inc-files.md#task-456c04e38ebc425fb35677a6bb6aa077).

El conjunto de datos se retransforma, tras lo cual la dimensión ampliada no aparece en el menú de dimensión de Data Workbench. Para obtener más información sobre el parámetro Oculto, consulte [Dimension extendidos](../../../../home/c-dataset-const-proc/c-ex-dim/c-abt-ex-dim.md).

Si cambia la configuración del parámetro Oculto , debe volver a transformar el conjunto de datos para que el cambio surta efecto.

## Ocultar Dimension extendidos usando el parámetro Mostrar {#section-4dceb1079c7f40d2bffc686d1f73f8ad}

El parámetro Mostrar no es uno de los parámetros disponibles para definir dimensiones extendidas en archivos [!DNL Transformation Dataset Configuration]. En su lugar, el parámetro se define en los archivos [!DNL .dim] para cualquier dimensión derivada que cree. Por lo tanto, para utilizar el parámetro Show para ocultar una dimensión extendida, primero debe crear una dimensión derivada basada en la dimensión extendida como se describe en el siguiente procedimiento:

1. Utilice un editor de texto como el Bloc de notas para crear un archivo vacío llamado &lt;*dimension name*>.dim El nombre del archivo debe coincidir con el nombre de la dimensión que desea ocultar. Por ejemplo, para ocultar la dimensión Página siguiente, debe crear un archivo [!DNL Next Page.dim].

1. Agregue el siguiente texto al archivo:

   * entity = ref: wdata/model/dim/Parent/+name
   * show = bool: false

1. Guarde el archivo en el directorio de Dimension del perfil. Si lo desea, puede guardar el archivo en un subdirectorio.

Cuando se utiliza el parámetro Show para ocultar una dimensión extendida, no es necesario retransformar el conjunto de datos para que el cambio tenga efecto. Puede elegir ocultar o mostrar la dimensión en su versión local del perfil (es decir, puede guardar el archivo [!DNL .dim] en la carpeta Usuario) o guardar el archivo [!DNL .dim] en el servidor para que lo utilicen otros usuarios del perfil.

También puede utilizar el parámetro Mostrar para ocultar métricas y filtros. Para obtener más información, consulte el capítulo Configuración de interfaz y características de análisis en la *Guía del usuario de Data Workbench*.
