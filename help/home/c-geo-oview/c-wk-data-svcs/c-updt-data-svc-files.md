---
description: Si se suscribe a cualquiera de los servicios de datos, deberá actualizar periódicamente los archivos de servicio de datos proporcionados por Adobe.
solution: Analytics
title: Actualización de archivos del servicio de datos
topic: Data workbench
uuid: 8c14be34-fde3-4c4c-9c22-739863317d6e
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Actualización de archivos del servicio de datos{#updating-data-service-files}

Si se suscribe a cualquiera de los servicios de datos, deberá actualizar periódicamente los archivos de servicio de datos proporcionados por Adobe.

Para ello, debe tener acceso a los archivos del servidor del área de trabajo de datos.

Para cargar [!DNL IP Geo-location] o [!DNL IP Geo-intelligence] archivos de datos, debe completar los siguientes procedimientos.

## Reemplazo del archivo de datos {#section-2b53c2951ae04c6fa8b3bdf080469ff6}

1. En el área de trabajo de datos, en la ficha [!DNL Admin] > [!DNL Dataset and Profile] , haga clic en la **[!UICONTROL Servers Manager]** miniatura para abrir el [!DNL Servers Manager] espacio de trabajo.

1. Dentro de la [!DNL Servers Manager] ventana, haga clic con el botón derecho en el icono del servidor del área de trabajo de datos en el que desea cargar los archivos y haga clic en **[!UICONTROL Server Files]**.

1. En la [!DNL Server Files Manager], haga clic con el botón derecho en la **[!UICONTROL Temp]** columna para **[!UICONTROL Lookups\IP Geo-location]** o **[!UICONTROL Lookups\IP Geo-intelligence]** y haga clic en **[!UICONTROL Open]** > *&lt;**[!UICONTROL folder]**>*.

1. Copie el archivo de datos proporcionado por Adobe en la ventana de la carpeta Lookups\IP Geo-location o Lookups\IP Geo-Intelligence. [!DNL .bin]
1. Guarde el archivo en el equipo del servidor del área de trabajo de datos haciendo clic con el botón secundario en la columna del [!DNL Temp] archivo de datos y haciendo clic en **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>*.

   Si está ejecutando un clúster, cargue los archivos en el servidor maestro del área de trabajo de datos del clúster.

## Actualización de la transformación IPLookup {#section-a8b99afe3eb04afabe88e15bd465f935}

1. En la [!DNL Profile Manager], haga clic en **[!UICONTROL Dataset]**, **[!UICONTROL Transformation]** y **[!UICONTROL Geography]**.

1. Haga clic con el botón secundario en la marca de verificación situada junto a [!DNL IP Lookup.cfg] y haga clic en **[!UICONTROL Make Local]**. En la [!DNL User] columna aparece una marca de verificación para este archivo.

1. Haga clic con el botón secundario en la nueva marca de verificación y haga clic en **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**. Aparece una ventana de configuración de transformación.

1. En la ventana, haga clic en **[!UICONTROL Transformation]** y, a continuación, en **[!UICONTROL Transformations]**.

1. Busque y haga clic en **[!UICONTROL IPLookup Quova]** o **[!UICONTROL IPLookup Digital Envoy]**.

1. Para el parámetro File, actualice el nombre del archivo para que coincida con el nombre del nuevo archivo de datos ( [!DNL .bin]) proporcionado por Adobe.
1. Para guardar el archivo de configuración de transformación, haga clic con el botón derecho **[!UICONTROL (modified)]** en la parte superior de la ventana de configuración y haga clic en **[!UICONTROL Save]**.

1. Guarde el archivo de configuración modificado en cada perfil que utilice el servicio de datos haciendo clic con el botón derecho en la marca de verificación situada junto a [!DNL IP Lookup.cfg] la [!DNL User] columna y haciendo clic en **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]**>*. La retransformación de los datos comienza después de la sincronización del perfil del conjunto de datos.

   Para obtener información sobre la retransformación de su conjunto de datos, consulte el capítulo Reprocesamiento y retransformación de la Guía *de configuración de* dataset.

   >[!NOTE]
   >
   >No guarde el archivo de configuración modificado en ninguno de los perfiles internos proporcionados por Adobe (incluido el perfil [!DNL IP Geo-location] o [!DNL IP Geo-intelligence] ), ya que los cambios se sobrescriben al instalar actualizaciones en estos perfiles.

Si ha instalado el servicio [!DNL IP Geo-intelligence] de datos y [!DNL IP Geo-location] para la versión 5.1 o posterior, habrá completado la actualización del servicio de datos. Sin embargo, si instaló el servicio de datos [!DNL IP Geo-intelligence] y [!DNL IP Geo-location] antes de la versión 5.1, debe completar los siguientes procedimientos adicionales.

## Sustitución del archivo de búsqueda {#section-ced1efa38a76419d812edd35423dbff7}

Debe completar los siguientes pasos sólo si instaló el servicio [!DNL IP Geo-intelligence] de datos y [!DNL IP Geo-location] antes de la versión 5.1.

1. En el [!DNL Server Files Manager], haga clic en **[!UICONTROL Profiles]** > **[!UICONTROL IP Geo-intelligence]** o **[!UICONTROL Profiles]** > **[!UICONTROL IP Geo-location]** y, a continuación, haga clic en **[!UICONTROL Maps]** para ver su contenido.

1. Haga clic con el botón secundario en la **[!UICONTROL Temp]** columna para **[!UICONTROL Maps]** y haga clic en **[!UICONTROL Open]** > *&lt;**[!UICONTROL folder]**>*.

1. Copie el nuevo [!DNL .txt] archivo proporcionado por Adobe en la ventana de la carpeta Mapas.
1. Guarde el archivo en el equipo del servidor del área de trabajo de datos haciendo clic con el botón secundario en la marca de verificación de la [!DNL Temp] columna del [!DNL .txt] archivo y haciendo clic en **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>*.

>[!NOTE]
>
>Si está ejecutando un clúster, cargue los archivos en el servidor maestro del área de trabajo de datos del clúster.

## Actualización de los archivos de capa {#section-8b84e7099bad40c9a69665a4890fe66e}

>[!NOTE]
>
>Debe completar los siguientes pasos sólo si instaló el servicio [!DNL IP Geo-intelligence] de datos y [!DNL IP Geo-location] antes de la versión 5.1.

Complete estos pasos para cada archivo de capa ( [!DNL .layer]) que haga referencia al archivo [!DNL IP Geo-intelligence] o [!DNL IP Geo-location] de búsqueda ( [!DNL .txt]).

1. En la carpeta Profiles\*data service name*\Maps del directorio de instalación del servidor del área de trabajo de datos, abra el [!DNL .layer] archivo en un editor de texto como Notepad.

1. En el [!DNL Data Paths] vector, actualice el nombre del archivo de [!DNL .txt] búsqueda para que coincida con el nombre del nuevo [!DNL .txt] archivo proporcionado por Adobe, como se muestra resaltado en el siguiente ejemplo de archivo:

   ```
   Layer = ElementPointLayer:
     Data Paths = vector: 1 items
       0 = Path: Maps\\LookupFileName.txt
     Longitude Column = string: LongitudeColumnName
     Latitude Column = string: LatitudeColumnName
     Name Column = string: LocationColumnName
     Key Column = string: KeyColumnName
     Dimension = ref: wdata/model/dim/DimensionName
     Metric = ref: wdata/model/metric/MetricName
   ```

1. Guarde el archivo de capa actualizado.
1. Repita los pasos 2 y 3 para cada [!DNL .layer] archivo que haga referencia al [!DNL IP Geo-intelligence] archivo o [!DNL IP Geo-location][!DNL .txt] .

