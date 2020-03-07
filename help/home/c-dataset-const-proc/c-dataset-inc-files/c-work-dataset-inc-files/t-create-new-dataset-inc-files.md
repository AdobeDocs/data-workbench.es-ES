---
description: Pasos para crear un nuevo archivo de inclusión de conjuntos de datos.
solution: Analytics
title: Creación de nuevos archivos de inclusión de conjunto de datos
topic: Data workbench
uuid: 707bdd84-b12b-4226-b6aa-43c9fc7ec9fe
translation-type: tm+mt
source-git-commit: 27600561841db3705f4eee6ff0aeb8890444bbc9

---


# Creación de nuevos archivos de inclusión de conjunto de datos{#creating-new-dataset-include-files}

Pasos para crear un nuevo archivo de inclusión de conjuntos de datos.

Debe crear un nuevo archivo de inclusión de conjuntos de datos para realizar cualquiera de las siguientes tareas de configuración de conjuntos de datos:

* Especificación de nuevos campos de datos que se pasarán del procesamiento de registros a la transformación.
* Definición de transformaciones que realizan cualquiera de las siguientes acciones:

   * Actualice los campos de registro existentes.
   * Produzca nuevos campos que se pasarán del procesamiento del registro a la transformación o que se utilizarán para definir dimensiones extendidas.

      Para obtener información sobre los tipos de transformación disponibles, consulte Transformaciones [de datos](../../../../home/c-dataset-const-proc/c-data-trans/c-abt-transf.md).

      >[!NOTE]
      >
      >Si está definiendo transformaciones en un nuevo archivo de inclusión de conjuntos de datos, asegúrese de tener en cuenta el orden de las entradas y salidas. Para obtener información sobre el orden de las transformaciones, consulte [Convenciones para la construcción de transformaciones](../../../../home/c-dataset-const-proc/c-data-trans/c-con-transf.md#concept-01998eebb7e347c58255fb442f2613b6).

* Creación de dimensiones extendidas. Para obtener información sobre los tipos de dimensión disponibles, consulte Dimensiones [extendidas](../../../../home/c-dataset-const-proc/c-ex-dim/c-abt-ex-dim.md).

1. Mientras trabaja en su perfil de conjunto de datos, abra el archivo [!DNL Profile Manager] y haga clic en **[!UICONTROL Dataset]** para ver los archivos de inclusión del conjunto de datos existente.

   * Para ver los [!DNL Log Processing Dataset Include] archivos, haga clic en **[!UICONTROL Log Processing]**.

   * Para ver los [!DNL Transformation Dataset Include] archivos, haga clic en **[!UICONTROL Transformation]**.

1. Cree archivos nuevos [!DNL Log Processing] o [!DNL Transformation Dataset Include] realizando uno de los siguientes pasos:

   * En la [!DNL User] columna del directorio Procesamiento de registros, haga clic en **[!UICONTROL Create]** > **[!UICONTROL New Log Processing]**. En el directorio aparece un archivo denominado [!DNL New Log Processing.cfg] .

   * En la [!DNL User] columna del directorio Transformación, haga clic en **[!UICONTROL Create]** > **[!UICONTROL New Transformation]**. En el directorio aparece un archivo denominado [!DNL New Transformation.cfg] .

1. Para cambiar el nombre del nuevo archivo, haga clic con el botón secundario en su marca de verificación en la columna y escriba el nuevo nombre en el parámetro File. [!DNL User]

   ![Información sobre los pasos](assets/vis_ProfileManager_RenameFile.png)

1. Haga clic con el botón secundario en la marca de verificación del archivo cuyo nombre ha cambiado y haga clic en **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**. Aparece la ventana de configuración.
1. Edite los parámetros en el archivo de configuración según corresponda. Consulte Conjunto de datos de procesamiento [de registros Incluir archivos](../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-log-proc-dataset-inc-files/c-log-proc-dataset-inc-files.md#concept-999475a22519432e98844622ca95b6ab) o Conjunto de datos de [transformación Incluir archivos](../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-trans-dataset-inc-files.md#concept-c64aa78ed9ce40b8a0f4932c82ff5ace) para obtener descripciones de los parámetros disponibles.
1. Para guardar los cambios, haga clic con el botón derecho del ratón **[!UICONTROL (modified)]** en la parte superior de la ventana y haga clic en **[!UICONTROL Save]**.
1. Para que los cambios realizados localmente surtan efecto, en la columna [!DNL Profile Manager], haga clic con el botón secundario en la marca de verificación del archivo en la [!DNL User] columna y, a continuación, haga clic en **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]**>*, donde nombre de perfil es el nombre del perfil del conjunto de datos o el perfil heredado al que pertenece el archivo de inclusión del conjunto de datos. El reprocesamiento o retransformación de los datos comienza después de la sincronización del perfil del conjunto de datos.

   >[!NOTE]
   >
   >No guarde el archivo de configuración modificado en ninguno de los perfiles internos proporcionados por Adobe, ya que los cambios se sobrescriben al instalar actualizaciones en estos perfiles.

Para editar un archivo de inclusión de conjuntos de datos que haya creado, consulte [Edición de archivos](../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-work-dataset-inc-files/t-edit-ex-dataset-inc-files.md#task-456c04e38ebc425fb35677a6bb6aa077)de inclusión de conjuntos de datos existentes.
