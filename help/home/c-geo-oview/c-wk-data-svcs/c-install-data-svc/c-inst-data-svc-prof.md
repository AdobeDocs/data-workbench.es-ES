---
description: Los perfiles del servicio de datos (Geo-Intelligence IP y Geolocalización IP) son perfiles internos que proporcionan funcionalidad adicional a la aplicación de Adobe.
title: Instalación del perfil del servicio de datos
uuid: 1c03d0cd-7eaa-4e48-bbff-8bfad8fed9e9
exl-id: 51d080bb-f874-426c-91ea-3912ffd38419
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '746'
ht-degree: 1%

---

# Instalación del perfil del servicio de datos{#installing-the-data-service-profile}

Los perfiles del servicio de datos (Geo-Intelligence IP y Geolocalización IP) son perfiles internos que proporcionan funcionalidad adicional a la aplicación de Adobe.

Al igual que con todos los demás perfiles internos proporcionados por Adobe, estos perfiles no deben cambiarse. Toda la personalización debe producirse en el conjunto de datos o en los perfiles específicos de funciones u otros perfiles que cree.

Los perfiles del servicio de datos incluyen los siguientes conjuntos de datos que incluyen archivos que se van a instalar en un servidor de Data Workbench:

* **Profiles\*nombre de perfil *\Dataset\Log Processing\Traffic\IP.cfg:** Enumera el campo c-ip que se pasará del procesamiento de registros a la transformación.
* **Profiles\*nombre de perfil *\Dataset\Transformation\Geography\IPLookup.cfg:** Define una transformación IPLookup que produce varios campos de datos geográficos utilizando el archivo de búsqueda Geo-Intelligence IP o Geo-location IP proporcionado.

Para obtener información acerca de los archivos de inclusión de conjuntos de datos de transformación, consulte la *Guía de configuración de conjuntos de datos*.

Además, cada perfil de servicio de datos proporciona un archivo de capa de punto de elemento llamado [!DNL IP Coordinates.layer]. Este archivo de capa le permite asignar ubicaciones en su conjunto de datos en el globo dinámicamente mediante direcciones IP. Después de la instalación, la capa se almacena en la carpeta Profiles\*data service name*\Maps dentro del directorio de instalación del servidor de Data Workbench.

El archivo [!DNL IP Coordinates.layer] hace referencia a la dimensión Coordenadas, que se define en el archivo [!DNL Coordinates.cfg] proporcionado con el perfil [!DNL Geography] y se encuentra en la carpeta Dataset\Transformation\Geography folder. Cada elemento de la dimensión Coordenadas definida en el conjunto de datos se asigna en el globo utilizando la información de latitud y longitud contenida en ese elemento. Para obtener más información sobre las capas de puntos de elementos que utilizan puntos dinámicos, consulte [Definición de capas de puntos de elementos mediante puntos dinámicos](../../../../home/c-geo-oview/c-wk-img-lyrs/c-elmt-pt-lyrs/c-elmt-pt-lyrs-ref-lkp-files/c-elmt-pt-lyr-file-frmt/c-dyn-pts.md#concept-77ae65bedc3f465489bc135ae7e3c2f3).

>[!NOTE]
>
>Si ha instalado el servicio de inteligencia geográfica IP y el servicio de ubicación geográfica IP antes de la versión 5.1, el archivo de capa de puntos de elemento hace referencia a un archivo de búsqueda en lugar de utilizar puntos dinámicos. Cada archivo de capa hace referencia al archivo de búsqueda de códigos geográficos IP y a la dimensión Código geográfico IP . El archivo de búsqueda de códigos geográficos de IP contiene una lista de códigos geográficos de IP (ubicaciones geográficas basadas en la dirección IP) y la latitud y longitud de cada uno. Cada elemento de una dimensión de código geográfico de IP definida en su conjunto de datos se asigna en el globo utilizando la latitud y longitud enumeradas para ese código geográfico de IP en el archivo de búsqueda de códigos geográficos de IP.

El nombre del archivo de capa y los archivos a los que hace referencia difieren para cada servicio de datos:

* El archivo [!DNL IP Geocodes D.layer] se instala con el perfil de inteligencia geográfica (Digital Envoy) de IP. Esta capa de punto de elemento hace referencia al archivo de búsqueda [!DNL IP Geocodes D yyyymmdd.txt] (que debe actualizar periódicamente) y a la dimensión de código geográfico IP D.

* El archivo [!DNL IP Geocodes Q.layer] se instala con el perfil de geolocalización de IP (Quova). Esta capa de punto de elemento hace referencia al archivo de búsqueda [!DNL IP Geocodes Q yyyymmdd.txt] (que debe actualizar periódicamente) y a la dimensión Q de código geográfico IP.

Para obtener más información sobre las capas de puntos de elementos que utilizan archivos de búsqueda, consulte [Definición de capas de punto de elementos que hacen referencia a archivos de búsqueda](../../../../home/c-geo-oview/c-wk-img-lyrs/c-elmt-pt-lyrs/c-elmt-pt-lyrs-ref-lkp-files/c-elmt-pt-lyrs-ref-lkp-files.md#concept-c40bd0890a984112bce831b596827f0f).

## Para instalar el perfil de Geo-Intelligence o Geo-location de IP {#section-6dff402ffdcb4b31b9bcd0c40a5f7625}

>[!NOTE]
>
>Las siguientes instrucciones de instalación suponen que ha instalado Data Workbench y ha establecido una conexión entre Data Workbench y el servidor de Data Workbench en el que está instalando Data Workbench [!DNL Geography]. Si no lo ha hecho, consulte la *Guía del usuario de Data Workbench*.

1. Abra la carpeta Perfiles desde el archivo [!DNL .zip] que recibió de Adobe.
1. Copie la carpeta IP Geo-Intelligence o Geo-location de IP a la carpeta Profiles del directorio de instalación del servidor de Data Workbench. Desea terminar con un ...\Profiles\IP Geo-intelligence folder or a ...\Profiles\IP Geo-location on your data workbench server as shown in the following example. Los nombres de las otras carpetas dentro de la carpeta [!DNL Profiles] pueden diferir de los que se muestran.

   ![](assets/Geo_installProfiles_dirIP.png)

1. Siga estos pasos para actualizar el archivo [!DNL profile.cfg] para cada perfil con el que desee utilizar el perfil [!DNL IP Geo-intelligence] o [!DNL IP Geo-location].

   1. Abra el **[!UICONTROL Profile Manager]**.
   1. Haga clic con el botón derecho en la marca de verificación situada junto a [!DNL profile.cfg] y haga clic en **[!UICONTROL Make Local]**. En la columna [!DNL User] aparece una marca de verificación para este archivo.

   1. Haga clic con el botón derecho en la marca de verificación recién creada y haga clic en **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**. Aparece la ventana [!DNL profile.cfg].

   1. En la ventana [!DNL profile.cfg], haga clic con el botón derecho en **[!UICONTROL Directories]** y haga clic en **[!UICONTROL Add new]** > **[!UICONTROL Directory]**.

      Para añadir el nuevo directorio al final de la lista de directorios, haga clic con el botón derecho en el número o nombre del último directorio de la lista y haga clic en **[!UICONTROL Add new]** > **[!UICONTROL Directory]**.

   1. Escriba el nombre del nuevo directorio: [!DNL IP Geo-intelligence] o I [!DNL P Geo-location].

   1. Haga clic con el botón derecho **[!UICONTROL (modified)]** en la parte superior de la ventana y haga clic en **[!UICONTROL Save]**.

   1. En [!DNL Profile Manager], haga clic con el botón derecho en la marca de verificación de [!DNL profile.cfg] en la columna [!DNL User] y, a continuación, haga clic en **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]**>*.

>[!NOTE]
>
>No guarde el archivo de configuración modificado en ninguno de los perfiles internos proporcionados por Adobe (incluido el perfil [!DNL IP Geo-location] o [!DNL IP Geo-intelligence]), ya que los cambios se sobrescriben al instalar actualizaciones en estos perfiles.
