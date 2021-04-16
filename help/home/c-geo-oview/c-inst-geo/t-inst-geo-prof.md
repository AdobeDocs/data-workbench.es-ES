---
description: El perfil Geografía proporcionado con Data WorkbenchGeography es un perfil interno que proporciona funcionalidad adicional a la aplicación de Adobe.
title: Instalación del perfil de geografía
uuid: afc0699d-e58b-481b-a3f2-ab6d6998bdd8
exl-id: 9ab07fd4-d6e7-495e-ba34-04e53c9b0aa3
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '409'
ht-degree: 2%

---

# Instalación del perfil de geografía{#installing-the-geography-profile}

El perfil Geografía proporcionado con Data WorkbenchGeography es un perfil interno que proporciona funcionalidad adicional a la aplicación de Adobe.

Al igual que con todos los demás perfiles internos proporcionados por Adobe, el perfil [!DNL Geography] no debe cambiarse. Toda la personalización debe producirse en el conjunto de datos o en los perfiles específicos de funciones u otros perfiles que cree.

El perfil [!DNL Geography] incluye varios conjuntos de datos de transformación que incluyen archivos (ubicados en la carpeta [!DNL Dataset\Transformation\Geography]) que definen dimensiones geográficas. A continuación se muestra una lista de los archivos de inclusión del conjunto de datos de transformación proporcionados con el perfil [!DNL Geography]:

* [!DNL City.cfg]
* [!DNL Coordinates.cfg]
* [!DNL Country.cfg]
* [!DNL DMA.cfg]
* [!DNL Domain.cfg]

Cada uno de los archivos recibe el nombre de la dimensión ampliada que define. Un archivo adicional, [!DNL IPLookup.cfg], define varios campos de datos geográficos que se utilizan para definir dimensiones en el otro conjunto de datos de transformación que incluye archivos.

Para obtener información acerca de los archivos de inclusión de conjuntos de datos de transformación, consulte la *Guía de configuración de conjuntos de datos*.

**Para instalar el  [!DNL Geography] perfil en el servidor de Data Workbench**

>[!NOTE]
>
>Las siguientes instrucciones de instalación suponen que ha instalado Data Workbench y ha establecido una conexión entre Data Workbench y el servidor de Data Workbench en el que está instalando Data Workbench [!DNL Geography]. Si no lo ha hecho, consulte la *Guía del usuario de Data Workbench*.

1. Abra la carpeta Perfiles en el archivo [!DNL .zip] que se le proporciona por Adobe.
1. Copie la carpeta [!DNL Geography] en la carpeta Perfiles del directorio de instalación del servidor de Data Workbench. Desea terminar con una carpeta [!DNL ...\Profiles\Geography] en el servidor de Data Workbench como se muestra en el siguiente ejemplo. Los nombres de las otras carpetas de la carpeta Perfiles pueden diferir de los que se muestran.

   ![Información sobre los pasos](assets/Geo_installProfiles_dir.png)

1. Siga estos pasos para actualizar el archivo [!DNL profile.cfg] de cada perfil con el que desee utilizar Data Workbench [!DNL Geography].

   1. Abra el [!DNL Profile Manager].
   1. Haga clic con el botón derecho en la marca de verificación situada junto a [!DNL profile.cfg] y haga clic en **[!UICONTROL Make Local]**. En la columna [!DNL User] aparece una marca de verificación para este archivo.

   1. Haga clic con el botón derecho en la marca de verificación recién creada y haga clic en **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**. Aparece la ventana [!DNL profile.cfg].

   1. En la ventana [!DNL profile.cfg], haga clic con el botón derecho en **[!UICONTROL Directories]** y haga clic en **[!UICONTROL Add new]** > **[!UICONTROL Directory]**.

      Para añadir el nuevo directorio al final de la lista de directorios, haga clic con el botón derecho en el número o nombre del último directorio de la lista y haga clic en **[!UICONTROL Add new]** > **[!UICONTROL Directory]**.

   1. Escriba el nombre del nuevo directorio: [!DNL Geography].
   1. Haga clic con el botón derecho **[!UICONTROL (modified)]** en la parte superior de la ventana y haga clic en **[!UICONTROL Save]**.

   1. En [!DNL Profile Manager], haga clic con el botón derecho en la marca de verificación de [!DNL profile.cfg] en la columna [!DNL User] y, a continuación, haga clic en **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]**>*.

      >[!NOTE]
      >
      >No guarde el archivo de configuración modificado en ninguno de los perfiles internos proporcionados por Adobe (incluido el perfil [!DNL Geography]), ya que los cambios se sobrescriben al instalar actualizaciones en estos perfiles.
