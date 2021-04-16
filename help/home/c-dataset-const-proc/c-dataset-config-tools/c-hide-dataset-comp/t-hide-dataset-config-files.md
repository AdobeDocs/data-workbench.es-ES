---
description: Si no desea heredar un archivo de configuración de un perfil interno u otro perfil heredado (es decir, desea que las instrucciones del archivo se ignoren durante la construcción del conjunto de datos), pero no desea modificarlo, puede crear un archivo vacío (byte cero) con el mismo nombre y almacenar el archivo en otro perfil.
title: Ocultar archivos de configuración de conjuntos de datos
uuid: eb33cf54-e067-4af2-a10e-7ffe43910e4f
exl-id: 327847d1-421a-4ed1-9a5f-2491765a34bd
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '319'
ht-degree: 2%

---

# Ocultar archivos de configuración de conjuntos de datos{#hiding-dataset-configuration-files}

Si no desea heredar un archivo de configuración de un perfil interno u otro perfil heredado (es decir, desea que las instrucciones del archivo se ignoren durante la construcción del conjunto de datos), pero no desea modificarlo, puede crear un archivo vacío (byte cero) con el mismo nombre y almacenar el archivo en otro perfil.

**Para un archivo de configuración de conjunto de datos de byte cero**

1. En [!DNL Profile Manager], abra las carpetas y subcarpetas necesarias para localizar el archivo que desea bytes cero.
1. Haga clic con el botón derecho en la marca de verificación situada junto al nombre del archivo y haga clic en **[!UICONTROL Make Local]**.
1. Abra el archivo local en un editor de texto como el Bloc de notas y elimine su contenido.
1. Guarde y cierre el archivo.
1. En [!DNL Profile Manager], guarde el archivo de byte cero en un perfil a la derecha del perfil en el que reside el archivo original. (Desea que el archivo de byte cero tenga prioridad sobre el archivo original).

   En [!DNL Profile Manager], un guión (-), en lugar de una marca de verificación, en una columna identifica el archivo de byte cero como se muestra en el ejemplo siguiente.

   ![](assets/vis_ProfileManager_ZeroByteFile.png)

Cuando vuelve a procesar el conjunto de datos, el conjunto de datos no contiene los componentes del conjunto de datos que define el archivo original.

>[!NOTE]
>
>Si genera un byte cero en un archivo de configuración que define una dimensión ampliada que se utiliza en una visualización o una definición de métrica, Data Workbench genera un error para esa visualización o métrica, respectivamente.

También puede utilizar archivos de byte cero para mover una métrica, dimensión o filtro a otra ubicación del perfil o para ocultar elementos del menú. Para obtener más información, consulte la *Guía del usuario de Data Workbench*.
