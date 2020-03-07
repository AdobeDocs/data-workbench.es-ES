---
description: Pasos para editar los archivos de inclusión de conjuntos de datos existentes.
solution: Analytics
title: Edición de archivos de inclusión de conjuntos de datos existentes
topic: Data workbench
uuid: fcce2e46-b4a8-4c53-83bb-32ab410eb89e
translation-type: tm+mt
source-git-commit: 27600561841db3705f4eee6ff0aeb8890444bbc9

---


# Edición de archivos de inclusión de conjuntos de datos existentes{#editing-existing-dataset-include-files}

Pasos para editar los archivos de inclusión de conjuntos de datos existentes.

Se abre un archivo de inclusión de conjunto de datos existente mediante el uso del [!DNL Profile Manager] en el área de trabajo de datos.

Para obtener información sobre cómo abrir y trabajar con el [!DNL Profile Manager], consulte la Guía del usuario *del área de trabajo de datos*.

1. Mientras trabaja en el perfil del conjunto de datos, abra el [!DNL Profile Manager] y haga clic en **[!UICONTROL Dataset]** para mostrar el contenido del directorio.

   * Para abrir un [!DNL Log Processing Dataset Include] archivo, haga clic en **[!UICONTROL Log Processing]** para mostrar el contenido del directorio.

   * Para abrir un [!DNL Transformation Dataset Include] archivo, haga clic en **[!UICONTROL Transformation]** para mostrar el contenido del directorio.

1. Haga clic con el botón secundario en la marca de verificación situada junto al archivo de inclusión de conjuntos de datos que desee y haga clic en **[!UICONTROL Make Local]**. En la [!DNL User] columna aparece una marca de verificación para este archivo.
1. Haga clic con el botón secundario en la marca de verificación recién creada y haga clic en **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**. Aparece la ventana de configuración.

   También puede abrir un archivo de inclusión de conjuntos de datos desde un [!DNL Transformation Dependency Maps]. Para obtener más información [!DNL Transformation Dependency Maps], consulte [Reprocesamiento y retransformación](../../../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md).

1. Edite los parámetros en el archivo de configuración según corresponda. Consulte Conjunto de datos de procesamiento [de registros Incluir archivos](../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-log-proc-dataset-inc-files/c-log-proc-dataset-inc-files.md#concept-999475a22519432e98844622ca95b6ab) o Conjunto de datos de [transformación Incluir archivos](../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-trans-dataset-inc-files.md#concept-c64aa78ed9ce40b8a0f4932c82ff5ace) para obtener descripciones de los parámetros.

   Al editar un archivo de inclusión de datos dentro de una ventana del área de trabajo de datos, puede utilizar teclas de método abreviado para las funciones de edición básicas, como cortar (Ctrl+x), copiar (Ctrl+c), pegar (Ctrl+v), deshacer (Ctrl+z), rehacer (Ctrl+Mayús+z), seleccionar la sección (hacer clic+arrastrar) y seleccionar todo (Ctrl+a). Además, puede utilizar los métodos abreviados para copiar y pegar texto de un archivo de configuración ( [!DNL .cfg]) a otro.

1. Para guardar los cambios, haga clic con el botón derecho del ratón **[!UICONTROL (modified)]** en la parte superior de la ventana y haga clic en **[!UICONTROL Save]**.
1. Para que los cambios realizados localmente surtan efecto, en la columna [!DNL Profile Manager], haga clic con el botón secundario en la marca de verificación del archivo en la [!DNL User] columna y, a continuación, haga clic en **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]**>*, donde nombre de perfil es el nombre del perfil del conjunto de datos o el perfil heredado al que pertenece el archivo de inclusión del conjunto de datos. El reprocesamiento o retransformación de los datos comienza después de la sincronización del perfil del conjunto de datos.

   >[!NOTE]
   >
   >No guarde el archivo de configuración modificado en ninguno de los perfiles internos proporcionados por Adobe, ya que los cambios se sobrescriben al instalar actualizaciones en estos perfiles.

