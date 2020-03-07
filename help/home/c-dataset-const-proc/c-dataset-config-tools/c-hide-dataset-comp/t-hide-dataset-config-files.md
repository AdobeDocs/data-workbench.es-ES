---
description: Si no desea heredar un archivo de configuración de un perfil interno o heredado de otro tipo (es decir, desea que las instrucciones del archivo se ignoren durante la construcción del conjunto de datos), pero no desea modificar el archivo, puede crear un archivo vacío (de byte cero) con el mismo nombre y almacenar el archivo en otro perfil.
solution: Analytics
title: Ocultar archivos de configuración de conjuntos de datos
topic: Data workbench
uuid: eb33cf54-e067-4af2-a10e-7ffe43910e4f
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Ocultar archivos de configuración de conjuntos de datos{#hiding-dataset-configuration-files}

Si no desea heredar un archivo de configuración de un perfil interno o heredado de otro tipo (es decir, desea que las instrucciones del archivo se ignoren durante la construcción del conjunto de datos), pero no desea modificar el archivo, puede crear un archivo vacío (de byte cero) con el mismo nombre y almacenar el archivo en otro perfil.

**Para un archivo de configuración de conjuntos de datos de byte cero**

1. En la carpeta [!DNL Profile Manager], abra las carpetas y subcarpetas necesarias para localizar el archivo de byte cero.
1. Haga clic con el botón derecho en la marca de verificación situada junto al nombre del archivo y haga clic en **[!UICONTROL Make Local]**.
1. Abra el archivo local en un editor de texto como Bloc de notas y elimine su contenido.
1. Guarde y cierre el archivo.
1. En el [!DNL Profile Manager], guarde el archivo de byte cero en un perfil a la derecha del perfil en el que reside el archivo original. (Desea que el archivo de byte cero tenga prioridad sobre el archivo original).

   En la columna [!DNL Profile Manager], un guión (-), en lugar de una marca de verificación, identifica el archivo de byte cero como se muestra en el ejemplo siguiente.

   ![](assets/vis_ProfileManager_ZeroByteFile.png)

Al volver a procesar el conjunto de datos, éste no contiene los componentes del conjunto de datos que define el archivo original.

>[!NOTE]
>
>Si un archivo de configuración de byte cero define una dimensión extendida que se utiliza en una visualización o una definición de métrica, el área de trabajo de datos generará un error para esa visualización o métrica, respectivamente.

También puede utilizar archivos de byte cero para mover una métrica, dimensión o filtro a otra ubicación del perfil o para ocultar elementos de menú. For information, see the *Data Workbench User Guide*.
