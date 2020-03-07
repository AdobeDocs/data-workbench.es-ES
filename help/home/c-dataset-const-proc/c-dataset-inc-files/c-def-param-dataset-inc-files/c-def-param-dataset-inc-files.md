---
description: Al configurar el conjunto de datos, puede definir variables, denominadas parámetros, para representar valores significativos.
solution: Analytics
title: Definición de parámetros en archivos de inclusión de conjuntos de datos
topic: Data workbench
uuid: 1eb7d48c-a107-4b32-abca-55d30586813f
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Definición de parámetros en archivos de inclusión de conjuntos de datos{#defining-parameters-in-dataset-include-files}

Al configurar el conjunto de datos, puede definir variables, denominadas parámetros, para representar valores significativos.

Para asignar un valor a un parámetro (es decir, para definir el parámetro), debe agregar el nombre y el valor del parámetro al vector Parameters en un archivo o procesamiento de registro. [!DNL Transformation Dataset Include] Una vez definidos los parámetros, puede hacer referencia a ellos en los archivos de configuración del perfil del conjunto de datos. La definición y referencia de estos parámetros se denomina sustitución de parámetros. El uso de la sustitución de parámetros al configurar el conjunto de datos permite crear una ubicación centralizada para las definiciones de parámetros. Cuando necesite actualizar un parámetro al que se hace referencia varias veces o en varios archivos, sólo tendrá que realizar el cambio una vez.

>[!NOTE]
>
>En esta guía, el parámetro de término se ha utilizado para hacer referencia al nombre de cualquier configuración de un archivo de configuración (como Condición de entrada de registro, Reprocesamiento o Transformaciones). Sin embargo, como se utiliza en esta sección, el parámetro se refiere específicamente a un miembro del vector Parameters en un archivo de inclusión de conjuntos de datos y no al nombre de una configuración en un archivo de configuración.

Debe tener en cuenta los siguientes puntos al definir un parámetro:

* Un parámetro debe definirse exactamente una vez. Por lo tanto, no puede definir la misma variable en varios archivos de inclusión de conjuntos de datos.
* Cualquier parámetro que defina será local para las fases de procesamiento del registro o de transformación, pero será global en varios archivos de configuración de conjuntos de datos para esa fase. Por ejemplo, si define un parámetro en un [!DNL Transformation Dataset Include] archivo, el parámetro se define para toda la fase de transformación y puede hacer referencia a él en el [!DNL Transformation.cfg] archivo y en todos los demás [!DNL Transformation Dataset Include] archivos para los perfiles heredados. El parámetro no se definiría para el procesamiento de registros; por lo tanto, cualquier referencia al parámetro en el [!DNL Log Processing.cfg] archivo o en un [!DNL Log Processing Dataset Include] archivo generaría un error de procesamiento.

**Definición de un parámetro**

Puede definir parámetros de cadena, numéricos y vectoriales en [!DNL Log Processing] y [!DNL Transformation Include] archivos.

1. En la ventana del área de trabajo de datos del archivo [!DNL Log Processing] o [!DNL Transformation Dataset Include] , haga clic con el botón secundario **[!UICONTROL Parameters]** y, a continuación, haga clic en **[!UICONTROL Add new]** > **[!UICONTROL Parameter]**.

1. Seleccione **[!UICONTROL String Parameter]** o **[!UICONTROL Numeric Parameter]****[!UICONTROL Vector Parameter]** y complete los parámetros Nombre y Valor como se describe en las siguientes secciones.

1. Para guardar el archivo de inclusión de conjuntos de datos en el que ha definido el parámetro, haga clic con el botón secundario **[!UICONTROL (modified)]** en la parte superior de la ventana y haga clic en **[!UICONTROL Save]**.

1. Para que los cambios realizados localmente surtan efecto, en la columna [!DNL Profile Manager], haga clic con el botón secundario en la marca de verificación del archivo en la [!DNL User] columna y, a continuación, haga clic en **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]**>*, donde nombre de perfil es el nombre del perfil del conjunto de datos o el perfil heredado al que pertenece el archivo de inclusión del conjunto de datos.

>[!NOTE]
>
>No guarde el archivo de configuración modificado en ninguno de los perfiles internos proporcionados por Adobe, ya que los cambios se sobrescriben al instalar actualizaciones en estos perfiles.

**Para hacer referencia a un parámetro**

* Al hacer referencia a un parámetro definido en otro archivo de configuración de conjunto de datos, debe escribir su nombre como [!DNL $(parameter name)].

Las siguientes secciones describen los tipos de parámetros que puede definir.

* [Parámetros numéricos y de cadena](../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-def-param-dataset-inc-files/c-string-num-param.md#concept-14f391ce107c4a3dad827ec7967f1080)
* [Parámetros vectoriales](../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-def-param-dataset-inc-files/c-vector-param.md#concept-adb42a5474e245a9996d0aa8d5d522d0)

