---
description: Pasos para definir dimensiones extendidas.
solution: Analytics
title: Definición de dimensiones extendidas
topic: Data workbench
uuid: 25946998-54ca-4595-a2f9-9c593917643a
translation-type: tm+mt
source-git-commit: 27600561841db3705f4eee6ff0aeb8890444bbc9

---


# Definición de dimensiones extendidas{#defining-extended-dimensions}

Pasos para definir dimensiones extendidas.

1. Mientras trabaja en el perfil del conjunto de datos, abra el [!DNL Profile Manager] y haga clic en **[!UICONTROL Dataset]** para mostrar su contenido.
1. Abra el [!DNL Transformation.cfg] archivo o el [!DNL Transformation Dataset Include] archivo en el que desea definir la dimensión extendida.

   * (Recomendado) Para abrir un archivo de inclusión de conjuntos de datos, consulte [Conjunto de datos Incluir archivos](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-abt-dataset-inc-files.md).

      >[!NOTE]
      >
      >Adobe recomienda definir dimensiones extendidas en uno o varios [!DNL Transformation Dataset Include] archivos nuevos. Para obtener más información, consulte [Creación de nuevos conjuntos de datos para incluir archivos](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-work-dataset-inc-files/t-create-new-dataset-inc-files.md#task-b29f30605c374a6ca747ac843337b06e).

   * Para abrir el [!DNL Transformation.cfg] archivo, consulte [Edición del archivo](../../../home/c-dataset-const-proc/c-trans-config-file/t-edit-trans-config-file.md#task-cfef4142c1bf4437a669d1fdc75cabbc)de configuración de transformación.

1. Haga clic con el botón derecho **[!UICONTROL Transformations]** y haga clic en **[!UICONTROL Add new]** > *&lt;**[!UICONTROL Extended dimension type]**>*.
1. Introduzca la información adecuada para la dimensión extendida. Para obtener descripciones de los tipos de transformación e información sobre sus parámetros, consulte las secciones siguientes:

   * [Dimensiones contables](../../../home/c-dataset-const-proc/c-ex-dim/c-types-ex-dim/c-count-dim.md#concept-f28b633419494e7bbc510012dbfcc6f8)
   * [Dimensiones simples](../../../home/c-dataset-const-proc/c-ex-dim/c-types-ex-dim/c-simple-dim.md#concept-c1d804dac4094489afe61560d2908181)
   * [Varias dimensiones a muchas](../../../home/c-dataset-const-proc/c-ex-dim/c-types-ex-dim/c-many-dim.md#concept-5ed3cca8b2194d4f96134f6238040998)
   * [Dimensiones numéricas](../../../home/c-dataset-const-proc/c-ex-dim/c-types-ex-dim/c-num-dim.md#concept-8513b9afaff447c8b334410b565b91ed)
   * [Dimensiones denormales](../../../home/c-dataset-const-proc/c-ex-dim/c-types-ex-dim/c-denormal-dim.md#concept-54a2600b8ee748b7acff405daccf3489)
   * [Dimensiones temporales](../../../home/c-dataset-const-proc/c-ex-dim/c-types-ex-dim/c-time-dim.md#concept-1e4eeb8d33964bb2a8d5768d6439df67)

      Para cualquier dimensión ampliada que defina, puede agregar una o más líneas de comentario al parámetro Comments para describir más la dimensión o agregar notas sobre su uso. Para agregar un comentario, haga clic con el botón secundario en la **[!UICONTROL Comments]** etiqueta y haga clic en **[!UICONTROL Add new]** > **[!UICONTROL Comment Line]**.

1. Una vez definidas las dimensiones extendidas en el archivo de configuración, guarde el archivo localmente y guárdelo en el perfil del conjunto de datos en el servidor del área de trabajo de datos.
