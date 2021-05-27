---
description: Si se suscribe a cualquiera de los servicios de datos, deberá actualizar periódicamente los archivos de servicio de datos proporcionados por el Adobe.
title: Actualización de archivos del servicio de datos
uuid: 8c14be34-fde3-4c4c-9c22-739863317d6e
exl-id: bb92d40c-cc8d-4ecf-bd48-ed962fd5d73b
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '577'
ht-degree: 1%

---

# Actualización de archivos del servicio de datos{#updating-data-service-files}

Si se suscribe a cualquiera de los servicios de datos, deberá actualizar periódicamente los archivos de servicio de datos proporcionados por el Adobe.

Para ello, debe tener acceso a los archivos del servidor de Data Workbench.

Para cargar archivos de datos [!DNL IP Geo-location] o [!DNL IP Geo-intelligence], debe completar los siguientes procedimientos.

## Reemplazar el archivo de datos {#section-2b53c2951ae04c6fa8b3bdf080469ff6}

1. En Data Workbench, en la pestaña [!DNL Admin] > [!DNL Dataset and Profile], haga clic en la miniatura **[!UICONTROL Servers Manager]** para abrir el espacio de trabajo [!DNL Servers Manager].

1. En la ventana [!DNL Servers Manager], haga clic con el botón derecho en el icono del servidor de Data Workbench en el que desea cargar los archivos y haga clic en **[!UICONTROL Server Files]**.

1. En [!DNL Server Files Manager], haga clic con el botón derecho en la columna **[!UICONTROL Temp]** para **[!UICONTROL Lookups\IP Geo-location]** o **[!UICONTROL Lookups\IP Geo-intelligence]** y haga clic en **[!UICONTROL Open]** > *&lt;**[!UICONTROL folder]**>*.

1. Copie el archivo de datos [!DNL .bin] proporcionado por el Adobe en la ventana Lookups\IP Geo-location o Lookups\IP Geo-Intelligence folder .
1. Guarde el archivo en el equipo del servidor de Data Workbench haciendo clic con el botón derecho en la columna [!DNL Temp] del archivo de datos y haciendo clic en **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>*.

   Si está ejecutando un clúster, cargue los archivos en el servidor maestro de Data Workbench del clúster.

## Actualización de la transformación IPLookup {#section-a8b99afe3eb04afabe88e15bd465f935}

1. En [!DNL Profile Manager], haga clic en **[!UICONTROL Dataset]**, **[!UICONTROL Transformation]** y **[!UICONTROL Geography]**.

1. Haga clic con el botón derecho en la marca de verificación situada junto a [!DNL IP Lookup.cfg] y haga clic en **[!UICONTROL Make Local]**. En la columna [!DNL User] aparece una marca de verificación para este archivo.

1. Haga clic con el botón derecho en la nueva marca de verificación y haga clic en **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**. Aparece una ventana de configuración de transformación.

1. En la ventana , haga clic en **[!UICONTROL Transformation]** y, a continuación, haga clic en **[!UICONTROL Transformations]**.

1. Busque y haga clic en **[!UICONTROL IPLookup Quova]** o **[!UICONTROL IPLookup Digital Envoy]**.

1. Para el parámetro File , actualice el nombre del archivo para que coincida con el nombre del nuevo archivo de datos ( [!DNL .bin]) proporcionado por Adobe.
1. Guarde el archivo de configuración de transformación haciendo clic con el botón derecho en **[!UICONTROL (modified)]** en la parte superior de la ventana de configuración y haciendo clic en **[!UICONTROL Save]**.

1. Guarde el archivo de configuración modificado en cada perfil que utilice el servicio de datos haciendo clic con el botón derecho en la marca de verificación situada junto a [!DNL IP Lookup.cfg] en la columna [!DNL User] y haciendo clic en **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]**>*. La retransformación de los datos comienza después de la sincronización del perfil del conjunto de datos.

   Para obtener información sobre la retransformación del conjunto de datos, consulte el capítulo Reprocessing and Retransformation (Reprocesamiento y retransformación) de la *Dataset Configuration Guide*.

   >[!NOTE]
   >
   >No guarde el archivo de configuración modificado en ninguno de los perfiles internos proporcionados por Adobe (incluido el perfil [!DNL IP Geo-location] o [!DNL IP Geo-intelligence]), ya que los cambios se sobrescriben al instalar actualizaciones en estos perfiles.

Si ha instalado el servicio de datos [!DNL IP Geo-intelligence] y [!DNL IP Geo-location] para la versión 5.1 o posterior, ha completado la actualización del servicio de datos. Sin embargo, si ha instalado el servicio de datos [!DNL IP Geo-intelligence] y [!DNL IP Geo-location] antes de la versión 5.1, debe completar los siguientes procedimientos adicionales.

## Reemplazar el archivo de búsqueda {#section-ced1efa38a76419d812edd35423dbff7}

Sólo debe completar los siguientes pasos si ha instalado el servicio de datos [!DNL IP Geo-intelligence] y [!DNL IP Geo-location] antes de la versión 5.1.

1. En [!DNL Server Files Manager], haga clic en **[!UICONTROL Profiles]** > **[!UICONTROL IP Geo-intelligence]** o **[!UICONTROL Profiles]** > **[!UICONTROL IP Geo-location]** y, a continuación, haga clic en **[!UICONTROL Maps]** para ver su contenido.

1. Haga clic con el botón derecho en la columna **[!UICONTROL Temp]** para **[!UICONTROL Maps]** y haga clic en **[!UICONTROL Open]** > *&lt;**[!UICONTROL folder]**>*.

1. Copie el nuevo archivo [!DNL .txt] proporcionado por el Adobe en la ventana de carpeta Mapas.
1. Guarde el archivo en el equipo del servidor de Data Workbench haciendo clic con el botón derecho en la marca de verificación de la columna [!DNL Temp] del archivo [!DNL .txt] y haciendo clic en **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>*.

>[!NOTE]
>
>Si está ejecutando un clúster, cargue los archivos en el servidor maestro de Data Workbench del clúster.

## Actualización de los archivos de capa {#section-8b84e7099bad40c9a69665a4890fe66e}

>[!NOTE]
>
>Sólo debe completar los siguientes pasos si ha instalado el servicio de datos [!DNL IP Geo-intelligence] y [!DNL IP Geo-location] antes de la versión 5.1.

Complete estos pasos para cada archivo de capa ( [!DNL .layer]) que haga referencia al archivo de búsqueda [!DNL IP Geo-intelligence] o [!DNL IP Geo-location] ( [!DNL .txt]).

1. En la carpeta Profiles\*data service name*\Maps del directorio de instalación del servidor de Data Workbench, abra el archivo [!DNL .layer] en un editor de texto como el Bloc de notas.

1. En el vector [!DNL Data Paths], actualice el nombre del archivo de búsqueda [!DNL .txt] para que coincida con el nombre del nuevo archivo [!DNL .txt] proporcionado por el Adobe, como se muestra resaltado en el siguiente ejemplo de archivo:

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
1. Repita los pasos 2 y 3 para cada archivo [!DNL .layer] que haga referencia al archivo [!DNL IP Geo-intelligence] o [!DNL IP Geo-location] [!DNL .txt].
