---
description: Al configurar el conjunto de datos, puede definir variables, referidas como parámetros, para representar valores significativos.
title: Definición de parámetros en archivos de inclusión de conjuntos de datos
uuid: 1eb7d48c-a107-4b32-abca-55d30586813f
exl-id: 80bb77e1-a157-4e16-9519-6d0e2ce17fe1
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '493'
ht-degree: 3%

---

# Definición de parámetros en archivos de inclusión de conjuntos de datos{#defining-parameters-in-dataset-include-files}

Al configurar el conjunto de datos, puede definir variables, referidas como parámetros, para representar valores significativos.

Para asignar un valor a un parámetro (es decir, para definir el parámetro), agregue el nombre y el valor del parámetro al vector Parameters en un archivo de procesamiento de registros o [!DNL Transformation Dataset Include]. Después de definir parámetros, puede hacer referencia a ellos en los archivos de configuración del perfil del conjunto de datos. La definición y referencia de estos parámetros se denomina sustitución de parámetros. El uso de la sustitución de parámetros al configurar el conjunto de datos permite crear una ubicación centralizada para las definiciones de parámetros. Cuando necesite actualizar un parámetro al que se hace referencia varias veces o en varios archivos, solo deberá realizar el cambio una vez.

>[!NOTE]
>
>En esta guía, el término parámetro se ha utilizado para hacer referencia al nombre de cualquier configuración de un archivo de configuración (como Condición de entrada de registro, Reprocesamiento o Transformaciones). Sin embargo, como se utiliza en esta sección, el parámetro hace referencia específicamente a un miembro del vector Parameters en un archivo de inclusión de conjunto de datos y no al nombre de un ajuste en un archivo de configuración.

Al definir un parámetro, debe tener en cuenta los siguientes puntos:

* Un parámetro debe definirse exactamente una vez. Por lo tanto, no puede definir la misma variable en varios archivos de inclusión de conjuntos de datos.
* Cualquier parámetro que defina es local para las fases de procesamiento de registros o de transformación, pero es global en varios archivos de configuración de conjuntos de datos para esa fase. Por ejemplo, si define un parámetro en un archivo [!DNL Transformation Dataset Include] , el parámetro se define para toda la fase de transformación y puede hacer referencia a él en el archivo [!DNL Transformation.cfg] y en todos los demás archivos [!DNL Transformation Dataset Include] para los perfiles heredados. El parámetro no se definiría para el procesamiento de registros; por lo tanto, cualquier referencia al parámetro en el archivo [!DNL Log Processing.cfg] o en un archivo [!DNL Log Processing Dataset Include] generaría un error de procesamiento.

**Definición de un parámetro**

Puede definir parámetros de cadena, numéricos y vectoriales en archivos [!DNL Log Processing] y [!DNL Transformation Include].

1. En la ventana del área de trabajo de datos para el archivo [!DNL Log Processing] o [!DNL Transformation Dataset Include], haga clic con el botón secundario en **[!UICONTROL Parameters]** y, a continuación, haga clic en **[!UICONTROL Add new]** > **[!UICONTROL Parameter]**.

1. Seleccione **[!UICONTROL String Parameter]**, **[!UICONTROL Numeric Parameter]** o **[!UICONTROL Vector Parameter]** y complete los parámetros Nombre y Valor como se describe en las secciones siguientes.

1. Para guardar el archivo de inclusión del conjunto de datos en el que ha definido el parámetro, haga clic con el botón derecho en **[!UICONTROL (modified)]** en la parte superior de la ventana y haga clic en **[!UICONTROL Save]**.

1. Para que los cambios realizados localmente surtan efecto, en [!DNL Profile Manager], haga clic con el botón derecho en la marca de verificación del archivo en la columna [!DNL User] y, a continuación, haga clic en **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]**>*, donde el nombre del perfil es el nombre del perfil del conjunto de datos o del perfil heredado al que pertenece el archivo de inclusión del conjunto de datos.

>[!NOTE]
>
>No guarde el archivo de configuración modificado en ninguno de los perfiles internos proporcionados por Adobe, ya que los cambios se sobrescriben al instalar actualizaciones en estos perfiles.

**Referencia a un parámetro**

* Cuando hace referencia a un parámetro definido en otro archivo de configuración de conjunto de datos, debe escribir su nombre como [!DNL $(parameter name)].

Las secciones siguientes describen los tipos de parámetros que puede definir.

* [Parámetros numéricos y de cadena](../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-def-param-dataset-inc-files/c-string-num-param.md#concept-14f391ce107c4a3dad827ec7967f1080)
* [Parámetros vectoriales](../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-def-param-dataset-inc-files/c-vector-param.md#concept-adb42a5474e245a9996d0aa8d5d522d0)
