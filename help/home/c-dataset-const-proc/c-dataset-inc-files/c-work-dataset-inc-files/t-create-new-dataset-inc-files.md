---
description: Pasos para crear un nuevo archivo de inclusión de conjunto de datos.
title: Creación de nuevos archivos de inclusión de conjunto de datos
uuid: 707bdd84-b12b-4226-b6aa-43c9fc7ec9fe
exl-id: 8a7b343d-b695-41aa-b465-8c5cd68d6ef7
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '393'
ht-degree: 3%

---

# Creación de nuevos archivos de inclusión de conjunto de datos{#creating-new-dataset-include-files}

{{eol}}

Pasos para crear un nuevo archivo de inclusión de conjunto de datos.

Debe crear un nuevo archivo de inclusión de conjunto de datos para realizar cualquiera de las siguientes tareas de configuración de conjunto de datos:

* Especificación de nuevos campos de datos que se pasarán del procesamiento de registros a la transformación.
* Definición de transformaciones que realizan cualquiera de las siguientes acciones:

   * Actualice los campos de registro existentes.
   * Produzca nuevos campos que se pasarán del procesamiento de registros a la transformación o que se utilicen para definir dimensiones extendidas.

      Para obtener información sobre los tipos de transformación disponibles, consulte [Transformaciones de datos](../../../../home/c-dataset-const-proc/c-data-trans/c-abt-transf.md).

      >[!NOTE]
      >
      >Si está definiendo transformaciones en un nuevo archivo de inclusión de conjunto de datos, asegúrese de tener en cuenta el orden de las entradas y salidas. Para obtener información sobre la ordenación de transformaciones, consulte [Convenciones para crear transformaciones](../../../../home/c-dataset-const-proc/c-data-trans/c-con-transf.md#concept-01998eebb7e347c58255fb442f2613b6).

* Creación de dimensiones extendidas. Para obtener información sobre los tipos de dimensiones disponibles, consulte [Dimension extendidos](../../../../home/c-dataset-const-proc/c-ex-dim/c-abt-ex-dim.md).

1. Mientras trabaja en el perfil del conjunto de datos, abra el [!DNL Profile Manager] y haga clic en **[!UICONTROL Dataset]** para ver los archivos de inclusión del conjunto de datos existente.

   * Para ver el [!DNL Log Processing Dataset Include] archivos, haga clic en **[!UICONTROL Log Processing]**.

   * Para ver el [!DNL Transformation Dataset Include] archivos, haga clic en **[!UICONTROL Transformation]**.

1. Cree una nueva [!DNL Log Processing] o [!DNL Transformation Dataset Include] realizando uno de los siguientes pasos:

   * En el [!DNL User] para el directorio Procesamiento de registros, haga clic en **[!UICONTROL Create]** > **[!UICONTROL New Log Processing]**. Un archivo llamado [!DNL New Log Processing.cfg] aparece en el directorio .

   * En el [!DNL User] para el directorio Transformation , haga clic en **[!UICONTROL Create]** > **[!UICONTROL New Transformation]**. Un archivo llamado [!DNL New Transformation.cfg] aparece en el directorio .

1. Para cambiar el nombre del nuevo archivo, haga clic con el botón derecho en su marca de verificación en la [!DNL User] y escriba el nuevo nombre en el parámetro File .

   ![Información sobre los pasos](assets/vis_ProfileManager_RenameFile.png)

1. Haga clic con el botón derecho en la marca de verificación del archivo cuyo nombre ha cambiado y haga clic en **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**. Aparecerá la ventana de configuración.
1. Edite los parámetros en el archivo de configuración según corresponda. Consulte [Archivos de inclusión de conjunto de datos de procesamiento de registros](../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-log-proc-dataset-inc-files/c-log-proc-dataset-inc-files.md#concept-999475a22519432e98844622ca95b6ab) o [Archivos de inclusión de conjunto de datos de transformación](../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-trans-dataset-inc-files.md#concept-c64aa78ed9ce40b8a0f4932c82ff5ace) para obtener descripciones de los parámetros disponibles.
1. Para guardar los cambios, haga clic con el botón derecho **[!UICONTROL (modified)]** en la parte superior de la ventana y haga clic en **[!UICONTROL Save]**.
1. Para que los cambios realizados localmente tengan efecto, en la variable [!DNL Profile Manager], haga clic con el botón derecho en la marca de verificación del archivo en la variable [!DNL User] y, a continuación, haga clic en **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]**>*, donde nombre de perfil es el nombre del perfil del conjunto de datos o el perfil heredado al que pertenece el archivo de inclusión del conjunto de datos. El reprocesamiento o retransformación de los datos comienza después de la sincronización del perfil del conjunto de datos.

   >[!NOTE]
   >
   >No guarde el archivo de configuración modificado en ninguno de los perfiles internos proporcionados por Adobe, ya que los cambios se sobrescriben al instalar actualizaciones en estos perfiles.

Para editar un archivo de inclusión de conjunto de datos que haya creado, consulte [Edición de archivos de inclusión de conjuntos de datos existentes](../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-work-dataset-inc-files/t-edit-ex-dataset-inc-files.md#task-456c04e38ebc425fb35677a6bb6aa077).
