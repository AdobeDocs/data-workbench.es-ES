---
description: Información sobre cómo agregar, quitar o copiar una condición.
solution: Analytics
title: Trabajar con condiciones
topic: Data workbench
uuid: b6f52b40-26aa-429b-9ff5-3f3b9c9d57a9
translation-type: tm+mt
source-git-commit: 27600561841db3705f4eee6ff0aeb8890444bbc9

---


# Trabajar con condiciones{#working-with-conditions}

Información sobre cómo agregar, quitar o copiar una condición.

* [Adición de una condición a un archivo de configuración de conjunto de datos](../../../home/c-dataset-const-proc/c-conditions/c-work-cond.md#section-3e2a34db047b462585502f69722f6511)
* [Quitar una condición de un archivo de configuración de conjunto de datos](../../../home/c-dataset-const-proc/c-conditions/c-work-cond.md#section-677270f93f1648c3a268ca2aea7d4540)
* [Para copiar una condición](../../../home/c-dataset-const-proc/c-conditions/c-work-cond.md#section-00617bcf2c274f428686b2ec7f2d1db8)

## Adición de una condición a un archivo de configuración de conjunto de datos {#section-3e2a34db047b462585502f69722f6511}

1. Mientras trabaja en su perfil de conjunto de datos, utilice el [!DNL Profile Manager] para abrir el archivo de configuración de conjunto de datos que desee editar.

   * Para abrir el [!DNL Log Processing.cfg] archivo, consulte [Edición del archivo](../../../home/c-dataset-const-proc/c-log-proc-config-file/t-edit-log-proc-config-file.md#task-6a2fa1b735cb4eefad730f0a3a7858e5)de configuración de procesamiento de registros.

   * Para abrir el [!DNL Transformation.cfg] archivo, consulte [Edición del archivo](../../../home/c-dataset-const-proc/c-trans-config-file/t-edit-trans-config-file.md#task-cfef4142c1bf4437a669d1fdc75cabbc)de configuración de transformación.

   * Para abrir un [!DNL Dataset Include] archivo, consulte [Conjunto de datos Incluir archivos](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-abt-dataset-inc-files.md).

1. Dentro del archivo de configuración del conjunto de datos, localice el parámetro Condición de entrada de registro o Condición que desee definir.
1. Haga clic con el botón secundario en el parámetro y haga clic en **[!UICONTROL Add new]**. Elija uno de los siguientes tipos de condición:

   * [!DNL Not Empty]
   * [!DNL String Match]
   * [!DNL Regular Expression]
   * [!DNL Range]
   * [!DNL And]
   * [!DNL Or]
   * [!DNL Neither]
   * [!DNL Compare]

1. Edite los parámetros de la condición como desee. Para obtener descripciones de los parámetros de cada condición, consulte la sección correspondiente de este apéndice.
1. Para guardar los cambios, haga clic con el botón derecho del ratón **[!UICONTROL (modified)]** en la parte superior de la ventana y haga clic en **[!UICONTROL Save]**.

1. Para que los cambios realizados localmente surtan efecto, haga clic con el botón [!DNL Profile Manager,] secundario en la marca de verificación del archivo en la [!DNL User] columna y, a continuación, haga clic en **[!UICONTROL Save to]** > &lt;* **[!UICONTROL profile name]***>, donde nombre de perfil es el nombre del perfil del conjunto de datos o el perfil heredado al que pertenece el archivo.

   >[!NOTE]
   >
   >No guarde el archivo de configuración modificado en ninguno de los perfiles internos proporcionados por Adobe, ya que los cambios se sobrescriben al instalar actualizaciones en estos perfiles.

## Quitar una condición de un archivo de configuración de conjunto de datos {#section-677270f93f1648c3a268ca2aea7d4540}

1. Haga clic con el botón secundario en el nombre de la condición o en el número correspondiente a la condición que desee eliminar.
1. Haga clic en **[!UICONTROL Remove]** &lt;* **[!UICONTROL #number]***>, donde número es el número correspondiente a la condición que desee eliminar.

## Para copiar una condición {#section-00617bcf2c274f428686b2ec7f2d1db8}

Puede copiar una condición de una ubicación a otra en el mismo archivo, o bien puede copiar una condición de un archivo de configuración de conjunto de datos a otro.

1. Haga clic con el botón secundario en el nombre de la condición o en el número correspondiente a la condición que desee copiar y haga clic en **[!UICONTROL Copy]**.
1. Haga clic con el botón secundario en el nombre o número de la condición debajo de la cual desee colocar la condición copiada y haga clic en **[!UICONTROL Paste]**.

