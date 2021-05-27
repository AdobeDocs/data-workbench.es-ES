---
description: Puede definir las transformaciones de datos que se aplicarán durante la fase de procesamiento de registros o de transformación de la construcción del conjunto de datos.
title: Definición de una transformación
uuid: 69dd667b-e465-4c1a-a20e-4384e8988cd0
exl-id: 61ce8093-9e64-419a-bddc-dc2225c0eaab
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '351'
ht-degree: 5%

---

# Definición de una transformación{#defining-a-transformation}

Puede definir las transformaciones de datos que se aplicarán durante la fase de procesamiento de registros o de transformación de la construcción del conjunto de datos.

>[!NOTE]
>
>Adobe recomienda definir transformaciones en archivos [!DNL Log Processing] o [!DNL Transformation Dataset Include] en lugar de en [!DNL Log Processing.cfg] o [!DNL Transformation.cfg].

Las siguientes transformaciones solo funcionan cuando se definen en el archivo [!DNL Transformation.cfg] o en un archivo [!DNL Transformation Dataset Include]:

* [](../../../home/c-dataset-const-proc/c-data-trans/c-transf-types/c-uri-transf/c-appenduri.md#concept-a0df05dd958645bf8219fc7b0b675ee4)AppendURII
* [CrossRows](../../../home/c-dataset-const-proc/c-data-trans/c-transf-types/c-standard-transf/c-crossrows.md#concept-fcace08804f54db397ed631cc13ff4f2)
* [LookupRows](../../../home/c-dataset-const-proc/c-data-trans/c-transf-types/c-standard-transf/c-lookuprows.md#concept-4bd9a1f13ee243e592a6a0008053134f)
* [Fuentes de datos ODBC](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-odbc-data-sources.md#concept-5f2cf635081d44beab826ef5ec8cf4e3)
* [Sessionize](../../../home/c-dataset-const-proc/c-data-trans/c-transf-types/c-standard-transf/c-sessionize.md#concept-b1af95c8cba34b248f86de883d914bc0)

**Definición de una transformación**

1. Utilice [!DNL Profile Manager] para abrir el archivo de configuración del conjunto de datos en el que desea definir la transformación.

   * (Recomendado) Para abrir un archivo de inclusión de conjunto de datos, consulte [Archivos de inclusión de conjunto de datos](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-abt-dataset-inc-files.md).
   * Para abrir el archivo [!DNL Log Processing.cfg], consulte [Edición del archivo de configuración de procesamiento de registros](../../../home/c-dataset-const-proc/c-log-proc-config-file/t-edit-log-proc-config-file.md#task-6a2fa1b735cb4eefad730f0a3a7858e5).

   * Para abrir el archivo [!DNL Transformation.cfg], consulte [Edición del archivo de configuración de transformación](../../../home/c-dataset-const-proc/c-trans-config-file/t-edit-trans-config-file.md#task-cfef4142c1bf4437a669d1fdc75cabbc).

1. Haga clic con el botón derecho en **[!UICONTROL Transformations]** y, a continuación, haga clic en **[!UICONTROL Add new]** > *&lt;**[!UICONTROL Transformation type]**>*.
1. Introduzca la información adecuada para la transformación. Para obtener descripciones de los tipos de transformación e información sobre sus parámetros, consulte las secciones siguientes:

   * [Transformaciones estándar](../../../home/c-dataset-const-proc/c-data-trans/c-transf-types/c-standard-transf/c-standard-transf.md#concept-25f4bdbf8fe74c4aaeb2fcd226243886)
   * [Transformaciones de URI](../../../home/c-dataset-const-proc/c-data-trans/c-transf-types/c-uri-transf/c-uri-transf.md#concept-2dfa0ffcd83d4fb69c1f42ad50dea125)
   * [Integración de datos de búsqueda](../../../home/c-dataset-const-proc/c-data-trans/c-int-lookup-data/c-int-lookup-data.md#concept-08ff70769a464f50ab14299a344f05c7)

1. Una vez definidas las transformaciones en el archivo de configuración, guarde el archivo localmente y guárdelo en el perfil del conjunto de datos en el servidor de Data Workbench.

       Sugerencias para definir y editar transformaciones:
   
   * Al editar la configuración de una transformación dentro de una ventana de Data Workbench, puede utilizar teclas de método abreviado para las funciones de edición básicas, como cortar (Ctrl+x ), copiar (Ctrl+c), pegar (Ctrl+v ), deshacer (Ctrl+z ), rehacer (Ctrl+Mayús+z ), seleccionar la sección (clic+arrastrar) y seleccionar todo (Ctrl+a ). Además, puede utilizar los accesos directos para copiar y pegar el texto o las definiciones de transformación completas de un archivo de configuración ( [!DNL .cfg]) a otro.
   * Para cualquier transformación que defina, puede agregar una o más líneas de comentarios al parámetro Comentarios para describir más la transformación o agregar notas sobre su uso. Para agregar un comentario utilizando Data Workbench, haga clic con el botón derecho en la etiqueta **[!UICONTROL Comments]** y, a continuación, haga clic en **[!UICONTROL Add new]** > **[!UICONTROL Comment Line]**.

   * Puede abrir la configuración de cualquier transformación desde [!DNL Transformation Dependency Map]. Después de abrir la configuración, puede editarla y guardar los cambios. Para obtener más información sobre [!DNL Transformation Dependency Maps], consulte [Herramientas de configuración de conjuntos de datos](../../../home/c-dataset-const-proc/c-dataset-config-tools/c-dataset-config-tools.md#concept-6e058b7691834cf79dcfd1573f78d4f5).

   * Un resultado de cadena vacío de una transformación puede sobrescribir una cadena que no esté vacía en el campo de salida.
