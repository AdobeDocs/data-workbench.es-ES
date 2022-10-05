---
description: Los perfiles del servicio de datos (Geo-Intelligence IP y Geolocalización IP) son perfiles internos que proporcionan funcionalidad adicional a la aplicación de Adobe.
title: Instalación del perfil del servicio de datos
uuid: 1c03d0cd-7eaa-4e48-bbff-8bfad8fed9e9
exl-id: 51d080bb-f874-426c-91ea-3912ffd38419
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '746'
ht-degree: 1%

---

# Instalación del perfil del servicio de datos{#installing-the-data-service-profile}

{{eol}}

Los perfiles del servicio de datos (Geo-Intelligence IP y Geolocalización IP) son perfiles internos que proporcionan funcionalidad adicional a la aplicación de Adobe.

Al igual que con todos los demás perfiles internos proporcionados por Adobe, estos perfiles no deben cambiarse. Toda la personalización debe producirse en el conjunto de datos o en los perfiles específicos de funciones u otros perfiles que cree.

Los perfiles del servicio de datos incluyen los siguientes conjuntos de datos que incluyen archivos que se van a instalar en un servidor de Data Workbench:

* **Perfiles\*nombre de perfil *\Dataset\Log Processing\Traffic\IP.cfg:** Muestra el campo c-ip que se pasará del procesamiento de registros a la transformación.
* **Perfiles\*nombre de perfil *\Dataset\Transformation\Geography\IPLookup.cfg:** Define una transformación IPLookup que produce varios campos de datos geográficos utilizando el archivo de búsqueda de Geo-Intelligence IP o Geo-location de IP proporcionado.

Para obtener información sobre los archivos de inclusión de conjuntos de datos de transformación, consulte la *Guía de configuración de conjuntos de datos*.

Además, cada perfil de servicio de datos proporciona un archivo de capa de punto de elemento denominado [!DNL IP Coordinates.layer]. Este archivo de capa le permite asignar ubicaciones en su conjunto de datos en el globo dinámicamente mediante direcciones IP. Después de la instalación, la capa se almacena en la carpeta Profiles\*data service name*\Maps dentro del directorio de instalación del servidor de Data Workbench.

La variable [!DNL IP Coordinates.layer] hace referencia a la dimensión Coordenadas , que se define en la variable [!DNL Coordinates.cfg] archivo proporcionado con la variable [!DNL Geography] y se encuentra en la carpeta Dataset\Transformation\Geography . Cada elemento de la dimensión Coordenadas definida en el conjunto de datos se asigna en el globo utilizando la información de latitud y longitud contenida en ese elemento. Para obtener más información sobre las capas de puntos de elementos que utilizan puntos dinámicos, consulte [Definición de capas de puntos de elementos mediante puntos dinámicos](../../../../home/c-geo-oview/c-wk-img-lyrs/c-elmt-pt-lyrs/c-elmt-pt-lyrs-ref-lkp-files/c-elmt-pt-lyr-file-frmt/c-dyn-pts.md#concept-77ae65bedc3f465489bc135ae7e3c2f3).

>[!NOTE]
>
>Si ha instalado el servicio de inteligencia geográfica IP y el servicio de ubicación geográfica IP antes de la versión 5.1, el archivo de capa de puntos de elemento hace referencia a un archivo de búsqueda en lugar de utilizar puntos dinámicos. Cada archivo de capa hace referencia al archivo de búsqueda de códigos geográficos IP y a la dimensión Código geográfico IP . El archivo de búsqueda de códigos geográficos de IP contiene una lista de códigos geográficos de IP (ubicaciones geográficas basadas en la dirección IP) y la latitud y longitud de cada uno. Cada elemento de una dimensión de código geográfico de IP definida en su conjunto de datos se asigna en el globo utilizando la latitud y longitud enumeradas para ese código geográfico de IP en el archivo de búsqueda de códigos geográficos de IP.

El nombre del archivo de capa y los archivos a los que hace referencia difieren para cada servicio de datos:

* La variable [!DNL IP Geocodes D.layer] se instala con el perfil de inteligencia geográfica IP (Digital Envoy). Esta capa de punto de elemento hace referencia al [!DNL IP Geocodes D yyyymmdd.txt] archivo de búsqueda (que debe actualizar periódicamente) y la dimensión IP Geocode D .

* La variable [!DNL IP Geocodes Q.layer] se instala con el perfil de geolocalización de IP (Quova). Esta capa de punto de elemento hace referencia al [!DNL IP Geocodes Q yyyymmdd.txt] archivo de búsqueda (que debe actualizar periódicamente) y la dimensión IP Geocode Q .

Para obtener más información sobre las capas de puntos de elementos que utilizan archivos de búsqueda, consulte [Definición de capas de punto de elementos que hacen referencia a archivos de búsqueda](../../../../home/c-geo-oview/c-wk-img-lyrs/c-elmt-pt-lyrs/c-elmt-pt-lyrs-ref-lkp-files/c-elmt-pt-lyrs-ref-lkp-files.md#concept-c40bd0890a984112bce831b596827f0f).

## Para instalar el perfil IP Geo-Intelligence o Geo-location IP {#section-6dff402ffdcb4b31b9bcd0c40a5f7625}

>[!NOTE]
>
>Las siguientes instrucciones de instalación suponen que ha instalado Data Workbench y ha establecido una conexión entre Data Workbench y el servidor de Data Workbench en el que está instalando Data Workbench [!DNL Geography]. Si no lo ha hecho, consulte la *Guía del usuario de Data Workbench*.

1. Abra la carpeta Perfiles en la carpeta [!DNL .zip] archivo que recibió de Adobe.
1. Copie la carpeta IP Geo-Intelligence o Geo-location de IP a la carpeta Profiles del directorio de instalación del servidor de Data Workbench. Desea terminar con un ...\Profiles\IP Geo-Intelligence folder o un ...\Profiles\Geolocalización de IP en el servidor de Data Workbench como se muestra en el siguiente ejemplo. Los nombres de las otras carpetas dentro de la [!DNL Profiles] puede diferir de las que se muestran.

   ![](assets/Geo_installProfiles_dirIP.png)

1. Siga estos pasos para actualizar el [!DNL profile.cfg] para cada perfil con el que desee usar el [!DNL IP Geo-intelligence] o [!DNL IP Geo-location] perfil.

   1. Abra el **[!UICONTROL Profile Manager]**.
   1. Haga clic con el botón derecho en la marca de verificación situada junto a [!DNL profile.cfg] y haga clic en **[!UICONTROL Make Local]**. Aparece una marca de verificación para este archivo en la variable [!DNL User] para abrir el Navegador.

   1. Haga clic con el botón derecho en la marca de verificación recién creada y haga clic en **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**. La variable [!DNL profile.cfg] se abre.

   1. En el [!DNL profile.cfg]ventana, clic con el botón derecho **[!UICONTROL Directories]** y haga clic en **[!UICONTROL Add new]** > **[!UICONTROL Directory]**.

      Para añadir el nuevo directorio al final de la lista de directorios, haga clic con el botón derecho en el número o nombre del último directorio de la lista y haga clic en **[!UICONTROL Add new]** > **[!UICONTROL Directory]**.

   1. Escriba el nombre del nuevo directorio: [!DNL IP Geo-intelligence] o I [!DNL P Geo-location].

   1. Clic con el botón derecho **[!UICONTROL (modified)]** en la parte superior de la ventana y haga clic en **[!UICONTROL Save]**.

   1. En el [!DNL Profile Manager], haga clic con el botón derecho en la marca de verificación de [!DNL profile.cfg] en el [!DNL User] y, a continuación, haga clic en **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]**>*.

>[!NOTE]
>
>No guarde el archivo de configuración modificado en ninguno de los perfiles internos proporcionados por el Adobe (incluido el [!DNL IP Geo-location] o [!DNL IP Geo-intelligence] ), ya que los cambios se sobrescriben al instalar actualizaciones en estos perfiles.
