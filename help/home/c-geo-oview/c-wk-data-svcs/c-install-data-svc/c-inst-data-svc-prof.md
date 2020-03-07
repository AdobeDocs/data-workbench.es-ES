---
description: Los perfiles del servicio de datos (Geo-Intelligence IP y Geo-location de IP) son perfiles internos que proporcionan funcionalidad adicional a la aplicación de Adobe.
solution: Analytics
title: Instalación del perfil del servicio de datos
topic: Data workbench
uuid: 1c03d0cd-7eaa-4e48-bbff-8bfad8fed9e9
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Instalación del perfil del servicio de datos{#installing-the-data-service-profile}

Los perfiles del servicio de datos (Geo-Intelligence IP y Geo-location de IP) son perfiles internos que proporcionan funcionalidad adicional a la aplicación de Adobe.

Al igual que con todos los demás perfiles internos proporcionados por Adobe, estos perfiles no deben modificarse. Toda la personalización debe producirse en el conjunto de datos o en los perfiles específicos de funciones u otros perfiles que cree.

Los perfiles del servicio de datos incluyen los siguientes conjuntos de datos: archivos que se instalarán en un servidor del área de trabajo de datos:

* **Profiles\*nombre *de perfil\Dataset\Log Processing\Traffic\IP.cfg:** Enumera el campo c-ip que se pasará del procesamiento de registros a la transformación.
* **Profiles\*nombre *de perfil\Dataset\Transformation\Geography\IPLookup.cfg:** Define una transformación IPLookup que produce varios campos de datos geográficos mediante el archivo de búsqueda Geo-Intelligence IP o Geo-location IP proporcionado.

Para obtener información sobre los archivos de inclusión de conjuntos de datos de transformación, consulte la Guía *de configuración de* conjuntos de datos.

Además, cada perfil de servicio de datos proporciona un archivo de capa de punto de elemento denominado [!DNL IP Coordinates.layer]. Este archivo de capa permite asignar de forma dinámica ubicaciones en el conjunto de datos del mundo mediante direcciones IP. Después de la instalación, la capa se almacena en la carpeta Profiles\*data service name*\Maps dentro del directorio de instalación del servidor del área de trabajo de datos.

El [!DNL IP Coordinates.layer] archivo hace referencia a la dimensión Coordenadas, que se define en el [!DNL Coordinates.cfg] archivo proporcionado con el [!DNL Geography] perfil y se encuentra en el directorio Dataset\Transformation\Geography folder. Cada elemento de la dimensión Coordenadas definida en el conjunto de datos se asigna en el globo usando la información de latitud y longitud contenida en ese elemento. Para obtener más información sobre las capas de puntos de elementos que utilizan puntos dinámicos, consulte [Definición de capas de puntos de elementos mediante puntos](../../../../home/c-geo-oview/c-wk-img-lyrs/c-elmt-pt-lyrs/c-elmt-pt-lyrs-ref-lkp-files/c-elmt-pt-lyr-file-frmt/c-dyn-pts.md#concept-77ae65bedc3f465489bc135ae7e3c2f3)dinámicos.

>[!NOTE]
>
>Si instaló el servicio de datos de Geo-Intelligence IP y Geo-location de IP antes de la versión 5.1, el archivo de capa de puntos del elemento hace referencia a un archivo de búsqueda en lugar de utilizar puntos dinámicos. Cada archivo de capa hace referencia al archivo de búsqueda de códigos geográficos IP y a la dimensión de código geográfico IP. El archivo de búsqueda de códigos geográficos IP contiene una lista de códigos geográficos IP (ubicaciones geográficas basadas en la dirección IP) y la latitud y longitud de cada uno. Cada elemento de una dimensión de geocódigo IP definida en el conjunto de datos se asigna en el globo usando la latitud y la longitud enumeradas para ese geocódigo IP en el archivo de búsqueda de códigos geográficos IP.

El nombre del archivo de capa y los archivos a los que hace referencia difieren en cada servicio de datos:

* El [!DNL IP Geocodes D.layer] archivo se instala con el perfil de inteligencia geográfica (Digital Envoy) de IP. Esta capa de punto de elemento hace referencia al archivo de [!DNL IP Geocodes D yyyymmdd.txt] búsqueda (que debe actualizar periódicamente) y a la dimensión D del código geográfico IP.

* El [!DNL IP Geocodes Q.layer] archivo se instala con el perfil Geo-location (Quova) de IP. Esta capa de punto de elemento hace referencia al archivo de [!DNL IP Geocodes Q yyyymmdd.txt] búsqueda (que debe actualizar periódicamente) y a la dimensión Q de código geográfico IP.

Para obtener más información sobre las capas de puntos de elementos que utilizan archivos de búsqueda, consulte [Definición de capas de puntos de elementos que hacen referencia a archivos](../../../../home/c-geo-oview/c-wk-img-lyrs/c-elmt-pt-lyrs/c-elmt-pt-lyrs-ref-lkp-files/c-elmt-pt-lyrs-ref-lkp-files.md#concept-c40bd0890a984112bce831b596827f0f)de búsqueda.

## Para instalar el perfil de geolocalización IP o de geoubicación IP {#section-6dff402ffdcb4b31b9bcd0c40a5f7625}

>[!NOTE]
>
>Las siguientes instrucciones de instalación suponen que ha instalado el área de trabajo de datos y ha establecido una conexión entre el área de trabajo de datos y el servidor del área de trabajo de datos en el que está instalando el área de trabajo de datos [!DNL Geography]. Si no lo ha hecho, consulte la Guía *del usuario de*&#x200B;Área de trabajo de datos.

1. Abra la carpeta Perfiles desde el [!DNL .zip] archivo que ha recibido de Adobe.
1. Copie la carpeta IP Geo-Intelligence o IP Geo-location en la carpeta Profiles del directorio de instalación del servidor del área de trabajo de datos. Quieres terminar con un ...\Profiles\IP Geo-intelligence folder or a ...\Profiles\IP Geo-location on your data workbench server as shown in the following example. Los nombres de las otras carpetas de la [!DNL Profiles] carpeta pueden diferir de los que se muestran.

   ![](assets/Geo_installProfiles_dirIP.png)

1. Siga estos pasos para actualizar el [!DNL profile.cfg] archivo de cada perfil con el que desee utilizar el [!DNL IP Geo-intelligence] o [!DNL IP Geo-location] .

   1. Abra el **[!UICONTROL Profile Manager]**.
   1. Haga clic con el botón secundario en la marca de verificación situada junto a [!DNL profile.cfg] y haga clic en **[!UICONTROL Make Local]**. En la [!DNL User] columna aparece una marca de verificación para este archivo.

   1. Haga clic con el botón secundario en la marca de verificación recién creada y haga clic en **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**. Aparecerá la [!DNL profile.cfg] ventana.

   1. En la [!DNL profile.cfg]ventana, haga clic con el botón derecho **[!UICONTROL Directories]** y haga clic en **[!UICONTROL Add new]** > **[!UICONTROL Directory]**.

      Para agregar el nuevo directorio al final de la lista de directorios, haga clic con el botón derecho en el número o nombre del último directorio de la lista y haga clic en **[!UICONTROL Add new]** > **[!UICONTROL Directory]**.

   1. Escriba el nombre del nuevo directorio: [!DNL IP Geo-intelligence] o yo [!DNL P Geo-location].

   1. Haga clic con el botón secundario **[!UICONTROL (modified)]** en la parte superior de la ventana y haga clic en **[!UICONTROL Save]**.

   1. En la [!DNL Profile Manager], haga clic con el botón secundario en la marca de verificación de [!DNL profile.cfg] la [!DNL User] columna y, a continuación, haga clic en **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]**>*.

>[!NOTE]
>
>No guarde el archivo de configuración modificado en ninguno de los perfiles internos proporcionados por Adobe (incluido el perfil [!DNL IP Geo-location] o [!DNL IP Geo-intelligence] ), ya que los cambios se sobrescriben al instalar actualizaciones en estos perfiles.

