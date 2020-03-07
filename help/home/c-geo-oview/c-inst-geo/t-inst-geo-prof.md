---
description: El perfil Geografía proporcionado con el área de trabajo de datosGeografía es un perfil interno que proporciona funcionalidad adicional a la aplicación de Adobe.
solution: Analytics
title: Instalación del perfil geográfico
topic: Data workbench
uuid: afc0699d-e58b-481b-a3f2-ab6d6998bdd8
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Instalación del perfil geográfico{#installing-the-geography-profile}

El perfil Geografía proporcionado con el área de trabajo de datosGeografía es un perfil interno que proporciona funcionalidad adicional a la aplicación de Adobe.

Al igual que con todos los demás perfiles internos proporcionados por Adobe, no se debe cambiar el [!DNL Geography] perfil. Toda la personalización debe producirse en el conjunto de datos o en los perfiles específicos de funciones u otros perfiles que cree.

El [!DNL Geography] perfil incluye varios conjuntos de datos de transformación que incluyen archivos (ubicados en la [!DNL Dataset\Transformation\Geography] carpeta) que definen las dimensiones geográficas. A continuación se muestra una lista del conjunto de datos de transformación que incluye archivos proporcionados con el [!DNL Geography] perfil:

* [!DNL City.cfg]
* [!DNL Coordinates.cfg]
* [!DNL Country.cfg]
* [!DNL DMA.cfg]
* [!DNL Domain.cfg]

Cada uno de los archivos recibe el nombre de la dimensión ampliada que define. Un archivo adicional [!DNL IPLookup.cfg], define varios campos de datos geográficos que se utilizan para definir dimensiones en el otro conjunto de datos de transformación que incluye archivos.

Para obtener información sobre los archivos de inclusión de conjuntos de datos de transformación, consulte la Guía *de configuración de* conjuntos de datos.

**Para instalar el[!DNL Geography]perfil en el servidor del área de trabajo de datos**

>[!NOTE]
>
>Las siguientes instrucciones de instalación suponen que ha instalado el área de trabajo de datos y ha establecido una conexión entre el área de trabajo de datos y el servidor del área de trabajo de datos en el que está instalando el área de trabajo de datos [!DNL Geography]. Si no lo ha hecho, consulte la Guía *del usuario de*&#x200B;Área de trabajo de datos.

1. Abra la carpeta Perfiles del [!DNL .zip] archivo que le proporcione Adobe.
1. Copie la [!DNL Geography] carpeta en la carpeta Perfiles del directorio de instalación del servidor del área de trabajo de datos. Desea terminar con una [!DNL ...\Profiles\Geography] carpeta en el servidor del área de trabajo de datos, como se muestra en el siguiente ejemplo. Los nombres de las otras carpetas de la carpeta Perfiles pueden diferir de los que se muestran.

   ![Información sobre los pasos](assets/Geo_installProfiles_dir.png)

1. Siga estos pasos para actualizar el [!DNL profile.cfg] archivo de cada perfil con el que desee utilizar el área de trabajo de datos [!DNL Geography].

   1. Abra el [!DNL Profile Manager].
   1. Haga clic con el botón secundario en la marca de verificación situada junto a [!DNL profile.cfg] y haga clic en **[!UICONTROL Make Local]**. En la [!DNL User] columna aparece una marca de verificación para este archivo.

   1. Haga clic con el botón secundario en la marca de verificación recién creada y haga clic en **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**. Aparecerá la [!DNL profile.cfg] ventana.

   1. En la [!DNL profile.cfg] ventana, haga clic con el botón derecho **[!UICONTROL Directories]** y haga clic en **[!UICONTROL Add new]** > **[!UICONTROL Directory]**.

      Para agregar el nuevo directorio al final de la lista de directorios, haga clic con el botón derecho en el número o nombre del último directorio de la lista y haga clic en **[!UICONTROL Add new]** > **[!UICONTROL Directory]**.

   1. Escriba el nombre del nuevo directorio: [!DNL Geography].
   1. Haga clic con el botón secundario **[!UICONTROL (modified)]** en la parte superior de la ventana y haga clic en **[!UICONTROL Save]**.

   1. En la [!DNL Profile Manager], haga clic con el botón secundario en la marca de verificación de [!DNL profile.cfg] la [!DNL User] columna y, a continuación, haga clic en **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]**>*.

      >[!NOTE]
      >
      >No guarde el archivo de configuración modificado en ninguno de los perfiles internos proporcionados por Adobe (incluido el [!DNL Geography] perfil), ya que los cambios se sobrescriben al instalar actualizaciones en estos perfiles.

