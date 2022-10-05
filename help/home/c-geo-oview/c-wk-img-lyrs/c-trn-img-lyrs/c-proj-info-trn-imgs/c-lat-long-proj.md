---
description: El formato de proyección latitud-longitud (LatLonProjection) del archivo Terrain Images.cfg se define mediante cuatro parámetros para latitud y longitud.
title: Proyecciones de latitud y longitud
uuid: 0ac947d6-3cd6-4272-96ae-456d2835e63f
exl-id: 67ebc7a8-3046-4524-b3a0-0b6da2f235fc
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '386'
ht-degree: 2%

---

# Proyecciones de latitud y longitud{#latitude-longitude-projections}

{{eol}}

El formato de proyección latitud-longitud (LatLonProjection) del archivo Terrain Images.cfg se define mediante cuatro parámetros para latitud y longitud.

Para especificar una LatLonProjection para imágenes no proyectadas (mapas de bits sin procesar ni imágenes generales, no proyectadas), puede introducir la configuración de LatLonProjection dentro de la variable [!DNL Terrain Images.cfg] en data workbench. Consulte [Especificación de LatLonProjection para imágenes no proyectadas](../../../../../home/c-geo-oview/c-wk-img-lyrs/c-trn-img-lyrs/c-proj-info-trn-imgs/c-lat-long-proj.md#section-26554eefe645481faba68396fa13756a).

Para especificar un LatLonProjection para imágenes con información de proyección incrustada, debe abrir el [!DNL Terrain Images.cfg] en un editor de texto como Notepad, establezca el parámetro Información de proyección en &quot;LatLonProjection&quot; y agregue la configuración para LatLonProjection. Consulte [Para especificar un LatLonProjection para imágenes dentro de la información de proyección incrustada...](../../../../../home/c-geo-oview/c-wk-img-lyrs/c-trn-img-lyrs/c-proj-info-trn-imgs/c-lat-long-proj.md#section-174f4e00fad84a7ca0c995423dd37ae1).

* [Especificación de LatLonProjection para imágenes no proyectadas](../../../../../home/c-geo-oview/c-wk-img-lyrs/c-trn-img-lyrs/c-proj-info-trn-imgs/c-lat-long-proj.md#section-26554eefe645481faba68396fa13756a)
* [Para especificar una proyección LatLonProjection para imágenes dentro de la información de proyección integrada...](../../../../../home/c-geo-oview/c-wk-img-lyrs/c-trn-img-lyrs/c-proj-info-trn-imgs/c-lat-long-proj.md#section-174f4e00fad84a7ca0c995423dd37ae1)

## Especificación de LatLonProjection para imágenes no proyectadas {#section-26554eefe645481faba68396fa13756a}

1. Abra el [!DNL Terrain Images.cfg] en Data Workbench y añada un origen de capa de imagen de terreno como se describe en [Definición de una capa de imagen de terreno](../../../../../home/c-geo-oview/c-wk-img-lyrs/c-trn-img-lyrs/c-trn-img-lyrs.md#concept-8a0a16013e824ac29f35a0349b5d8ccf).

1. Edite los parámetros de Información de proyección utilizando la siguiente tabla de parámetros como guía:

   | Parámetro | Descripción |
   |---|---|
   | Lat0 | La latitud del borde superior de la imagen, en grados, donde 90 es el Polo Norte y -90 es el Polo Sur. |
   | Lat1 | Latitud del borde inferior de la imagen. |
   | Lon0 | Longitud del borde izquierdo de la imagen, en grados, donde los números positivos son orientales y los negativos son longitudes occidentales. |
   | Lon1 | Longitud del borde derecho de la imagen. |

1. Guarde el archivo haciendo clic con el botón derecho **[!UICONTROL (modified)]** en la parte superior de la ventana y haga clic en **[!UICONTROL Save]**.

1. Para guardar los cambios realizados localmente en el equipo del servidor de Data Workbench, en la variable [!DNL Server Files Manager], haga clic con el botón derecho en la marca de verificación de [!DNL Terrain Images.cfg] en el [!DNL Temp] y, a continuación, haga clic en **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>*.

## Especificación de una proyección LatLonProjection para imágenes dentro de información de proyección integrada {#section-174f4e00fad84a7ca0c995423dd37ae1}

1. En el [!DNL Server Files Manager], haga clic en **[!UICONTROL Components]** para ver su contenido. La variable [!DNL Terrain Images.cfg] se encuentra dentro de este directorio.

1. Haga clic con el botón derecho en la marca de verificación de la columna de nombre del servidor para [!DNL Terrain Images.cfg]y haga clic en **[!UICONTROL Make Local]**. Aparece una marca de verificación en la variable [!DNL Temp] para [!DNL Terrain Images.cfg].

1. Haga clic con el botón derecho en la marca de verificación recién creada en la [!DNL Temp] y haga clic en **[!UICONTROL Open]** > **[!UICONTROL in Notepad]**. La variable [!DNL Terrain Images.cfg] aparece en la ventana Bloc de notas.

1. Edite los parámetros de Información de proyección utilizando el siguiente fragmento de archivo de ejemplo como guía. Asegúrese de especificar el tipo de proyección como se indica a continuación. Para obtener descripciones de los parámetros, consulte la tabla Parámetros de LatLonProjection del procedimiento anterior.

   ```
   Projection Info = LatLonProjection: 
     Lat0 = double: 90
     Lat1 = double: -90
     Lon0 = double: -180
     Lon1 = double: 180
   ```
