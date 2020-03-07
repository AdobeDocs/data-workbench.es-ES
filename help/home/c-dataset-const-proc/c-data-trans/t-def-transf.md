---
description: Puede definir las transformaciones de datos que se aplicarán durante la fase de procesamiento de registros o de transformación de la construcción de conjuntos de datos.
solution: Analytics
title: Definición de una transformación
topic: Data workbench
uuid: 69dd667b-e465-4c1a-a20e-4384e8988cd0
translation-type: tm+mt
source-git-commit: 27600561841db3705f4eee6ff0aeb8890444bbc9

---


# Definición de una transformación{#defining-a-transformation}

Puede definir las transformaciones de datos que se aplicarán durante la fase de procesamiento de registros o de transformación de la construcción de conjuntos de datos.

>[!NOTE]
>
>Adobe recomienda definir transformaciones en [!DNL Log Processing] o en [!DNL Transformation Dataset Include] archivos en lugar de en [!DNL Log Processing.cfg] o [!DNL Transformation.cfg].

Las siguientes transformaciones solo funcionan cuando se definen en el [!DNL Transformation.cfg] archivo o en un [!DNL Transformation Dataset Include] archivo:

* [](../../../home/c-dataset-const-proc/c-data-trans/c-transf-types/c-uri-transf/c-appenduri.md#concept-a0df05dd958645bf8219fc7b0b675ee4)AppendURII
* [CrossRows](../../../home/c-dataset-const-proc/c-data-trans/c-transf-types/c-standard-transf/c-crossrows.md#concept-fcace08804f54db397ed631cc13ff4f2)
* [LookupRows](../../../home/c-dataset-const-proc/c-data-trans/c-transf-types/c-standard-transf/c-lookuprows.md#concept-4bd9a1f13ee243e592a6a0008053134f)
* [Orígenes de datos ODBC](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-odbc-data-sources.md#concept-5f2cf635081d44beab826ef5ec8cf4e3)
* [Sesionize](../../../home/c-dataset-const-proc/c-data-trans/c-transf-types/c-standard-transf/c-sessionize.md#concept-b1af95c8cba34b248f86de883d914bc0)

**Definición de una transformación**

1. Utilice el [!DNL Profile Manager] para abrir el archivo de configuración del conjunto de datos en el que desea definir la transformación.

   * (Recomendado) Para abrir un archivo de inclusión de conjuntos de datos, consulte [Conjunto de datos Incluir archivos](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-abt-dataset-inc-files.md).
   * Para abrir el [!DNL Log Processing.cfg] archivo, consulte [Edición del archivo](../../../home/c-dataset-const-proc/c-log-proc-config-file/t-edit-log-proc-config-file.md#task-6a2fa1b735cb4eefad730f0a3a7858e5)de configuración de procesamiento de registros.

   * Para abrir el [!DNL Transformation.cfg] archivo, consulte [Edición del archivo](../../../home/c-dataset-const-proc/c-trans-config-file/t-edit-trans-config-file.md#task-cfef4142c1bf4437a669d1fdc75cabbc)de configuración de transformación.

1. Haga clic con el botón secundario **[!UICONTROL Transformations]** y, a continuación, haga clic en **[!UICONTROL Add new]** > *&lt;**[!UICONTROL Transformation type]**>*.
1. Introduzca la información adecuada para la transformación. Para obtener descripciones de los tipos de transformación e información sobre sus parámetros, consulte las secciones siguientes:

   * [Transformaciones estándar](../../../home/c-dataset-const-proc/c-data-trans/c-transf-types/c-standard-transf/c-standard-transf.md#concept-25f4bdbf8fe74c4aaeb2fcd226243886)
   * [Transformaciones de URI](../../../home/c-dataset-const-proc/c-data-trans/c-transf-types/c-uri-transf/c-uri-transf.md#concept-2dfa0ffcd83d4fb69c1f42ad50dea125)
   * [Integración de datos de búsqueda](../../../home/c-dataset-const-proc/c-data-trans/c-int-lookup-data/c-int-lookup-data.md#concept-08ff70769a464f50ab14299a344f05c7)

1. Una vez definidas las transformaciones en el archivo de configuración, guarde el archivo localmente y guárdelo en el perfil del conjunto de datos en el servidor del área de trabajo de datos.

       Sugerencias para definir y editar transformaciones:
   
   * Al editar la configuración de una transformación dentro de una ventana del área de trabajo de datos, puede utilizar teclas de método abreviado para las funciones de edición básicas, como cortar (Ctrl+x), copiar (Ctrl+c), pegar (Ctrl+v), deshacer (Ctrl+z), rehacer (Ctrl+Mayús+z), seleccionar la sección (hacer clic+arrastrar) y seleccionar todo (Ctrl+a). Además, puede utilizar los métodos abreviados para copiar y pegar texto o definiciones de transformación completas de un archivo de configuración ( [!DNL .cfg]) a otro.
   * Para cualquier transformación que defina, puede agregar una o más líneas de comentarios al parámetro Comments para describir más la transformación o agregar notas sobre su uso. Para agregar un comentario mediante el área de trabajo de datos, haga clic con el botón secundario en la etiqueta y, a continuación, haga clic en **[!UICONTROL Comments]** > **[!UICONTROL Add new]** **[!UICONTROL Comment Line]**.

   * Puede abrir la configuración de cualquier transformación desde un [!DNL Transformation Dependency Map]. Después de abrir la configuración, puede editarla y guardar los cambios. Para obtener más información [!DNL Transformation Dependency Maps], consulte Herramientas [de configuración](../../../home/c-dataset-const-proc/c-dataset-config-tools/c-dataset-config-tools.md#concept-6e058b7691834cf79dcfd1573f78d4f5)de conjuntos de datos.

   * Una salida de cadena vacía de una transformación puede sobrescribir una cadena que no esté vacía en el campo de salida.

