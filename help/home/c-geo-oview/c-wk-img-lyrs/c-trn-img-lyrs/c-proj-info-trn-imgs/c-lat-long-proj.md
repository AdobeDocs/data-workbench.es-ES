---
description: El formato de proyección latitud-longitud (LatLonProjection) del archivo Terrain Images.cfg se define mediante cuatro parámetros de latitud y longitud.
solution: Analytics
title: Proyecciones de latitud y longitud
topic: Data workbench
uuid: 0ac947d6-3cd6-4272-96ae-456d2835e63f
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Proyecciones de latitud y longitud{#latitude-longitude-projections}

El formato de proyección latitud-longitud (LatLonProjection) del archivo Terrain Images.cfg se define mediante cuatro parámetros de latitud y longitud.

Para especificar una proyección LatLon para imágenes no proyectadas (mapas de bits sin proyección e imágenes generales, no proyectadas), puede introducir la configuración de la proyección LatLonProjection en la [!DNL Terrain Images.cfg] ventana del área de trabajo de datos. Consulte [Especificación de una proyección LatLon para imágenes](../../../../../home/c-geo-oview/c-wk-img-lyrs/c-trn-img-lyrs/c-proj-info-trn-imgs/c-lat-long-proj.md#section-26554eefe645481faba68396fa13756a)no proyectadas.

Para especificar una proyección LatLonProjection para imágenes con información de proyección incrustada, debe abrir el [!DNL Terrain Images.cfg] archivo en un editor de texto como Notepad, establecer el parámetro Información de proyección en &quot;LatLonProjection&quot; y agregar la configuración para LatLonProjection. Consulte [Especificación de una proyección LatLonProjection para imágenes dentro de la información de proyección incrustada...](../../../../../home/c-geo-oview/c-wk-img-lyrs/c-trn-img-lyrs/c-proj-info-trn-imgs/c-lat-long-proj.md#section-174f4e00fad84a7ca0c995423dd37ae1).

* [Especificación de una proyección de LatLon para imágenes no proyectadas](../../../../../home/c-geo-oview/c-wk-img-lyrs/c-trn-img-lyrs/c-proj-info-trn-imgs/c-lat-long-proj.md#section-26554eefe645481faba68396fa13756a)
* [Para especificar una proyección LatLonProjection para imágenes dentro de la información de proyección incrustada...](../../../../../home/c-geo-oview/c-wk-img-lyrs/c-trn-img-lyrs/c-proj-info-trn-imgs/c-lat-long-proj.md#section-174f4e00fad84a7ca0c995423dd37ae1)

## Especificación de una proyección de LatLon para imágenes no proyectadas {#section-26554eefe645481faba68396fa13756a}

1. Abra el [!DNL Terrain Images.cfg] archivo en el área de trabajo de datos y agregue un origen de capa de imagen de terreno como se describe en [Definición de una capa](../../../../../home/c-geo-oview/c-wk-img-lyrs/c-trn-img-lyrs/c-trn-img-lyrs.md#concept-8a0a16013e824ac29f35a0349b5d8ccf)de imagen de terreno.

1. Edite los parámetros de Información de proyección utilizando la siguiente tabla de parámetros como guía:

   | Parámetro | Descripción |
   |---|---|
   | Lat0 | La latitud del borde superior de la imagen, en grados, donde 90 es el Polo Norte y -90 es el Polo Sur. |
   | Lat1 | La latitud del borde inferior de la imagen. |
   | Lon0 | Longitud del borde izquierdo de la imagen, en grados, donde los números positivos son orientales y los negativos son longitudes occidentales. |
   | Lon1 | Longitud del borde derecho de la imagen. |

1. Para guardar el archivo, haga clic con el botón secundario **[!UICONTROL (modified)]** en la parte superior de la ventana y haga clic en **[!UICONTROL Save]**.

1. Para guardar los cambios realizados localmente en el equipo del servidor del área de trabajo de datos, en la [!DNL Server Files Manager], haga clic con el botón secundario en la marca de verificación de [!DNL Terrain Images.cfg] la [!DNL Temp] columna y, a continuación, haga clic en **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>*.

## Especificación de una proyección de LatLon para imágenes dentro de la información de proyección incrustada {#section-174f4e00fad84a7ca0c995423dd37ae1}

1. En el [!DNL Server Files Manager], haga clic **[!UICONTROL Components]** para ver su contenido. El [!DNL Terrain Images.cfg] archivo se encuentra dentro de este directorio.

1. Haga clic con el botón secundario en la marca de verificación de la columna del nombre del servidor para [!DNL Terrain Images.cfg]y, a continuación, haga clic en **[!UICONTROL Make Local]**. Aparece una marca de verificación en la [!DNL Temp] columna para [!DNL Terrain Images.cfg].

1. Haga clic con el botón secundario en la marca de verificación recién creada en la [!DNL Temp] columna y haga clic en **[!UICONTROL Open]** > **[!UICONTROL in Notepad]**. El [!DNL Terrain Images.cfg] archivo aparece en una ventana del Bloc de notas.

1. Edite los parámetros de Información de proyección utilizando el siguiente fragmento de archivo de ejemplo como guía. Asegúrese de especificar el tipo de proyección como se resalta a continuación. Para obtener descripciones de los parámetros, consulte la tabla Parámetros de LatLonProjection del procedimiento anterior.

   ```
   Projection Info = LatLonProjection: 
     Lat0 = double: 90
     Lat1 = double: -90
     Lon0 = double: -180
     Lon1 = double: 180
   ```

