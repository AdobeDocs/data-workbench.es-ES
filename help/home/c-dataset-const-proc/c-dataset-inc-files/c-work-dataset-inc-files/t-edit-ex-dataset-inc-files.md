---
description: Pasos para editar archivos de inclusión de conjuntos de datos existentes.
title: Edición de archivos de inclusión de conjuntos de datos existentes
uuid: fcce2e46-b4a8-4c53-83bb-32ab410eb89e
exl-id: f4095871-d004-4e10-af18-bf6c1e47493d
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '329'
ht-degree: 3%

---

# Edición de archivos de inclusión de conjuntos de datos existentes{#editing-existing-dataset-include-files}

{{eol}}

Pasos para editar archivos de inclusión de conjuntos de datos existentes.

Abra un archivo de inclusión de conjunto de datos existente usando la variable [!DNL Profile Manager] en data workbench.

Para obtener información sobre cómo abrir y trabajar con la variable [!DNL Profile Manager], consulte la *Guía del usuario de Data Workbench*.

1. Mientras trabaja en el perfil del conjunto de datos, abra el [!DNL Profile Manager] y haga clic en **[!UICONTROL Dataset]** para mostrar el contenido del directorio.

   * Para abrir un [!DNL Log Processing Dataset Include] archivo, haga clic en **[!UICONTROL Log Processing]** para mostrar el contenido del directorio.

   * Para abrir un [!DNL Transformation Dataset Include] archivo, haga clic en **[!UICONTROL Transformation]** para mostrar el contenido del directorio.

1. Haga clic con el botón derecho en la marca de verificación situada junto al archivo de inclusión de conjunto de datos deseado y haga clic en **[!UICONTROL Make Local]**. Aparece una marca de verificación para este archivo en la variable [!DNL User] para abrir el Navegador.
1. Haga clic con el botón derecho en la marca de verificación recién creada y haga clic en **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**. Aparecerá la ventana de configuración.

   También puede abrir un archivo de inclusión de conjunto de datos desde un [!DNL Transformation Dependency Maps]. Para obtener información sobre [!DNL Transformation Dependency Maps], consulte [Reprocesamiento y retransformación](../../../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md).

1. Edite los parámetros en el archivo de configuración según corresponda. Consulte [Archivos de inclusión de conjunto de datos de procesamiento de registros](../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-log-proc-dataset-inc-files/c-log-proc-dataset-inc-files.md#concept-999475a22519432e98844622ca95b6ab) o [Archivos de inclusión de conjunto de datos de transformación](../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-trans-dataset-inc-files.md#concept-c64aa78ed9ce40b8a0f4932c82ff5ace) para obtener descripciones de los parámetros.

   Al editar un archivo de inclusión de conjunto de datos dentro de una ventana de Data Workbench, puede utilizar teclas de método abreviado para funciones de edición básicas, como cortar (Ctrl+x ), copiar (Ctrl+c), pegar (Ctrl+v ), deshacer (Ctrl+z ), rehacer (Ctrl+Mayús+z ), seleccionar sección (clic+arrastrar) y seleccionar todo (Ctrl+a ). Además, puede utilizar los accesos directos para copiar y pegar texto de un archivo de configuración ( [!DNL .cfg]) a otro.

1. Para guardar los cambios, haga clic con el botón derecho **[!UICONTROL (modified)]** en la parte superior de la ventana y haga clic en **[!UICONTROL Save]**.
1. Para que los cambios realizados localmente tengan efecto, en la variable [!DNL Profile Manager], haga clic con el botón derecho en la marca de verificación del archivo en la variable [!DNL User] y, a continuación, haga clic en **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]**>*, donde nombre de perfil es el nombre del perfil del conjunto de datos o el perfil heredado al que pertenece el archivo de inclusión del conjunto de datos. El reprocesamiento o retransformación de los datos comienza después de la sincronización del perfil del conjunto de datos.

   >[!NOTE]
   >
   >No guarde el archivo de configuración modificado en ninguno de los perfiles internos proporcionados por Adobe, ya que los cambios se sobrescriben al instalar actualizaciones en estos perfiles.
