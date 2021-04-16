---
description: Pasos para definir dimensiones extendidas.
title: Definición de dimensiones extendidas
uuid: 25946998-54ca-4595-a2f9-9c593917643a
exl-id: e1664548-e2b4-47bb-8bec-155c16873e08
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '191'
ht-degree: 9%

---

# Definición de dimensiones extendidas{#defining-extended-dimensions}

Pasos para definir dimensiones extendidas.

1. Mientras trabaja en el perfil del conjunto de datos, abra [!DNL Profile Manager] y haga clic en **[!UICONTROL Dataset]** para mostrar su contenido.
1. Abra el archivo [!DNL Transformation.cfg] o el archivo [!DNL Transformation Dataset Include] en el que desea definir la dimensión ampliada.

   * (Recomendado) Para abrir un archivo de inclusión de conjunto de datos, consulte [Archivos de inclusión de conjunto de datos](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-abt-dataset-inc-files.md).

      >[!NOTE]
      >
      >Adobe recomienda definir dimensiones extendidas en uno o varios archivos [!DNL Transformation Dataset Include] nuevos. Para obtener más información, consulte [Creación de nuevos archivos de inclusión de conjunto de datos](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-work-dataset-inc-files/t-create-new-dataset-inc-files.md#task-b29f30605c374a6ca747ac843337b06e).

   * Para abrir el archivo [!DNL Transformation.cfg], consulte [Edición del archivo de configuración de transformación](../../../home/c-dataset-const-proc/c-trans-config-file/t-edit-trans-config-file.md#task-cfef4142c1bf4437a669d1fdc75cabbc).

1. Haga clic con el botón derecho en **[!UICONTROL Transformations]** y haga clic en **[!UICONTROL Add new]** > *&lt;**[!UICONTROL Extended dimension type]**>*.
1. Introduzca la información adecuada para su dimensión extendida. Para obtener descripciones de los tipos de transformación e información sobre sus parámetros, consulte las secciones siguientes:

   * [Dimensiones contables](../../../home/c-dataset-const-proc/c-ex-dim/c-types-ex-dim/c-count-dim.md#concept-f28b633419494e7bbc510012dbfcc6f8)
   * [Dimensiones simples](../../../home/c-dataset-const-proc/c-ex-dim/c-types-ex-dim/c-simple-dim.md#concept-c1d804dac4094489afe61560d2908181)
   * [Dimensión “varios a varios”](../../../home/c-dataset-const-proc/c-ex-dim/c-types-ex-dim/c-many-dim.md#concept-5ed3cca8b2194d4f96134f6238040998)
   * [Dimensiones numéricas](../../../home/c-dataset-const-proc/c-ex-dim/c-types-ex-dim/c-num-dim.md#concept-8513b9afaff447c8b334410b565b91ed)
   * [Dimensiones denormales](../../../home/c-dataset-const-proc/c-ex-dim/c-types-ex-dim/c-denormal-dim.md#concept-54a2600b8ee748b7acff405daccf3489)
   * [Dimensiones temporales](../../../home/c-dataset-const-proc/c-ex-dim/c-types-ex-dim/c-time-dim.md#concept-1e4eeb8d33964bb2a8d5768d6439df67)

      Para cualquier dimensión ampliada que defina, puede agregar una o más líneas de comentario al parámetro Comentarios para describir aún más la dimensión o agregar notas sobre su uso. Para agregar un comentario, haga clic con el botón derecho en la etiqueta **[!UICONTROL Comments]** y haga clic en **[!UICONTROL Add new]** > **[!UICONTROL Comment Line]**.

1. Una vez definidas las dimensiones ampliadas en el archivo de configuración, guarde el archivo localmente y guárdelo en el perfil del conjunto de datos en el servidor de Data Workbench.
