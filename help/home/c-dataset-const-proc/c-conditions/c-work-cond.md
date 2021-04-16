---
description: Información sobre cómo agregar, quitar o copiar una condición.
title: Trabajo con condiciones
uuid: b6f52b40-26aa-429b-9ff5-3f3b9c9d57a9
exl-id: 0792b308-aa0b-4741-be0c-4f7cc28f3e09
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '350'
ht-degree: 1%

---

# Trabajo con condiciones{#working-with-conditions}

Información sobre cómo agregar, quitar o copiar una condición.

* [Agregar una condición a un archivo de configuración de conjunto de datos](../../../home/c-dataset-const-proc/c-conditions/c-work-cond.md#section-3e2a34db047b462585502f69722f6511)
* [Eliminación de una condición de un archivo de configuración de conjunto de datos](../../../home/c-dataset-const-proc/c-conditions/c-work-cond.md#section-677270f93f1648c3a268ca2aea7d4540)
* [Copiar una condición](../../../home/c-dataset-const-proc/c-conditions/c-work-cond.md#section-00617bcf2c274f428686b2ec7f2d1db8)

## Agregar una condición a un archivo de configuración de conjunto de datos {#section-3e2a34db047b462585502f69722f6511}

1. Mientras trabaja en el perfil del conjunto de datos, utilice [!DNL Profile Manager] para abrir el archivo de configuración del conjunto de datos que desea editar.

   * Para abrir el archivo [!DNL Log Processing.cfg], consulte [Edición del archivo de configuración de procesamiento de registros](../../../home/c-dataset-const-proc/c-log-proc-config-file/t-edit-log-proc-config-file.md#task-6a2fa1b735cb4eefad730f0a3a7858e5).

   * Para abrir el archivo [!DNL Transformation.cfg], consulte [Edición del archivo de configuración de transformación](../../../home/c-dataset-const-proc/c-trans-config-file/t-edit-trans-config-file.md#task-cfef4142c1bf4437a669d1fdc75cabbc).

   * Para abrir un archivo [!DNL Dataset Include], consulte [Archivos de inclusión de conjunto de datos](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-abt-dataset-inc-files.md).

1. Dentro del archivo de configuración del conjunto de datos, busque la condición de entrada de registro o el parámetro de condición que desee definir.
1. Haga clic con el botón derecho en el parámetro y haga clic en **[!UICONTROL Add new]**. Elija uno de los siguientes tipos de condiciones:

   * [!DNL Not Empty]
   * [!DNL String Match]
   * [!DNL Regular Expression]
   * [!DNL Range]
   * [!DNL And]
   * [!DNL Or]
   * [!DNL Neither]
   * [!DNL Compare]

1. Edite los parámetros de la condición como desee. Para obtener descripciones de los parámetros de cada condición, consulte la sección correspondiente del presente apéndice.
1. Para guardar los cambios, haga clic con el botón derecho en **[!UICONTROL (modified)]** en la parte superior de la ventana y haga clic en **[!UICONTROL Save]**.

1. Para que los cambios realizados localmente tengan efecto, en [!DNL Profile Manager,] haga clic con el botón derecho en la marca de verificación del archivo en la columna [!DNL User] y, a continuación, haga clic en **[!UICONTROL Save to]** > &lt;* **[!UICONTROL profile name]***>, donde el nombre del perfil es el nombre del perfil del conjunto de datos o el perfil heredado al que pertenece el archivo.

   >[!NOTE]
   >
   >No guarde el archivo de configuración modificado en ninguno de los perfiles internos proporcionados por Adobe, ya que los cambios se sobrescriben al instalar actualizaciones en estos perfiles.

## Quitar una condición de un archivo de configuración de conjunto de datos {#section-677270f93f1648c3a268ca2aea7d4540}

1. Haga clic con el botón derecho en el nombre de la condición o en el número correspondiente a la condición que desee eliminar.
1. Haga clic en **[!UICONTROL Remove]** &lt;* **[!UICONTROL #number]***>, donde número es el número correspondiente a la condición que desea eliminar.

## Para copiar una condición {#section-00617bcf2c274f428686b2ec7f2d1db8}

Puede copiar una condición de una ubicación a otra en el mismo archivo o copiar una condición de un archivo de configuración de conjuntos de datos a otro.

1. Haga clic con el botón derecho en el nombre de la condición o en el número correspondiente a la condición que desea copiar y haga clic en **[!UICONTROL Copy]**.
1. Haga clic con el botón derecho en el nombre o número de la condición debajo de la cual desea colocar la condición copiada y haga clic en **[!UICONTROL Paste]**.
