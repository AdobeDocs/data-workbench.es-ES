---
description: Data Workbench admite proyecciones de longitud de latitud y proyecciones de Universal Transverse Mercator (UTM) para todas las fuentes de capa de imagen de terreno.
title: Especificación de información de proyección para imágenes de terreno
uuid: cc1e1e35-6b23-4121-a9f5-489001cb2ef8
exl-id: 2638c5d4-164d-411b-8464-0a3af81b6537
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '751'
ht-degree: 3%

---

# Especificación de información de proyección para imágenes de terreno{#specify-projection-information-for-terrain-images}

{{eol}}

Data Workbench admite proyecciones de longitud de latitud y proyecciones de Universal Transverse Mercator (UTM) para todas las fuentes de capa de imagen de terreno.

La información de proyección es necesaria para los mapas de bits sin proyectar e imágenes generales, no proyectados. Puede especificar información de proyección para imágenes con información de proyección incrustada, aunque normalmente no es necesaria, ya que los parámetros de la proyección se determinan automáticamente a partir de datos geodésicos incrustados en la propia imagen. Las secciones siguientes proporcionan detalles sobre cómo especificar estos formatos de proyección en la variable [!DNL Terrain Images.cfg] archivo.

## Proyecciones de latitud y longitud {#section-6e335357ec28462ba39c565e0a5986c7}

El formato de proyección de latitud-longitud (LatLonProjection) en la variable [!DNL Terrain Images.cfg] está definido por cuatro parámetros para latitud y longitud.

Para especificar una LatLonProjection para imágenes no proyectadas (mapas de bits sin procesar ni imágenes generales, no proyectadas), puede introducir la configuración de LatLonProjection dentro de la variable [!DNL Terrain Images.cfg] en la Data Workbench.

Para especificar un LatLonProjection para imágenes con información de proyección incrustada, debe abrir el [!DNL Terrain Images.cfg] en un editor de texto como Notepad, establezca el parámetro Información de proyección en LatLonProjection y agregue la configuración para [!DNL LatLonProjection].

**Especificación de LatLonProjection para imágenes no proyectadas**

1. Abra el [!DNL Terrain Images.cfg] en Data Workbench y añada un origen de capa de imagen de terreno como se describe en [Definición de una capa de imagen de terreno](../../../../home/c-get-started/c-im-layers/c-ter-img-layers/c-ter-img-layers.md#concept-f4b3a20969354ca38955e3fd5beb0f4f).
1. Edite los parámetros de Información de proyección utilizando la siguiente tabla de parámetros como guía:

<table id="table_32F6EADB2DA34592ABD6FFAC9E00BB27"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parámetro </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Lat0 </p> </td> 
   <td colname="col2"> <p>La latitud del borde superior de la imagen, en grados, donde 90 es el Polo Norte y -90 es el Polo Sur. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Lat1 </p> </td> 
   <td colname="col2"> <p>Latitud del borde inferior de la imagen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Lon0 </p> </td> 
   <td colname="col2"> <p>Longitud del borde izquierdo de la imagen, en grados, donde los números positivos son orientales y los negativos son longitudes occidentales. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Lon1 </p> </td> 
   <td colname="col2"> <p>Longitud del borde derecho de la imagen. </p> </td> 
  </tr> 
 </tbody> 
</table>

1. Guarde el archivo haciendo clic con el botón derecho **[!UICONTROL (modified)]** en la parte superior de la ventana y haga clic en **[!UICONTROL Save]**.
1. Para guardar los cambios realizados localmente en el equipo servidor de Data Workbench, en la [!DNL Server Files Manager], haga clic con el botón derecho en la marca de verificación de [!DNL Terrain Images.cfg] en el [!DNL Temp] y, a continuación, haga clic en **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>*.

**Especificación de LatLonProjection para imágenes dentro de la información de proyección incrustada**

En el [!DNL Server Files Manager], haga clic en **[!UICONTROL Components]** para ver su contenido. La variable [!DNL Terrain Images.cfg] se encuentra dentro de este directorio.

Haga clic con el botón derecho en la marca de verificación de la columna de nombre del servidor para [!DNL Terrain Images.cfg]y haga clic en **[!UICONTROL Make Local]**. Aparece una marca de verificación en la variable [!DNL Temp] para [!DNL Terrain Images.cfg].

Haga clic con el botón derecho en la marca de verificación recién creada en la [!DNL Temp] y haga clic en **[!UICONTROL Open]** > **[!UICONTROL in Notepad]**. La variable [!DNL Terrain Images.cfg] aparece en la ventana Bloc de notas.

Edite los parámetros de Información de proyección utilizando el siguiente fragmento de archivo de ejemplo como guía. Asegúrese de especificar el tipo de proyección como se indica a continuación. Para obtener descripciones de los parámetros, consulte la tabla Parámetros de LatLonProjection del procedimiento anterior.

```
Projection Info = LatLonProjection:
  Lat0 = double: 90
  Lat1 = double: -90
  Lon0 = double: -180
  Lon1 = double: 180
```

## Proyecciones de Universal Transverse Mercator {#section-606df0ed1c2d4a6bac3ff0fa2cfb3e82}

La proyección del Universal Transverse Mercator (UTM) se define mediante ocho parámetros. Al especificar una proyección de Universal Transverse Mercator para una capa de imagen de terreno, los archivos de imagen de terreno deben alinearse con false (proyectado) al norte hacia la parte superior de la imagen y false al este hacia la derecha de la imagen.

Para especificar una proyección de UTM para cualquier origen de imagen de terreno, debe abrir el [!DNL Terrain Images.cfg] en un editor de texto como el Bloc de notas, establezca el parámetro Información de proyección en &quot;TransverseMercatorProjection&quot; y agregue la configuración para la proyección de UTM.

**Especificación de una proyección de Universal Transverse Mercator**

1. En el [!DNL Server Files Manager], haga clic en **[!UICONTROL Components]** para ver su contenido. La variable [!DNL Terrain Images.cfg] se encuentra dentro de este directorio.
1. Haga clic con el botón derecho en la marca de verificación de la columna de nombre del servidor para [!DNL Terrain Images.cfg]y haga clic en **[!UICONTROL Make Local]**. Aparece una marca de verificación en la variable [!DNL Temp] para [!DNL Terrain Images.cfg.]
1. Haga clic con el botón derecho en la marca de verificación recién creada en la [!DNL Temp] y haga clic en **[!UICONTROL Open]** > **[!UICONTROL in Notepad]**. La variable [!DNL Terrain Images.cfg] aparece en la ventana Bloc de notas.
1. Edite los parámetros de Información de proyección utilizando la siguiente tabla de parámetros y fragmento de archivo de muestra como guías. Asegúrese de especificar el tipo de proyección como se indica a continuación.

   ```
   Projection Info = TransverseMercatorProjection:
     Ellipsoid Inverse Flattening = double: 294.9786982139006
     Ellipsoid Semimajor Axis = double: 6378206.4000000004
     False Easting = double: 500000
     False Northing = double: 0
     Northwest Corner Coordinates = v3d: (550339, 5.42059e+006, 0)
     Prime Meridian = double: -123
     Scale Factor = double: 0.9996
     Southeast Corner Coordinates = v3d: (555099, 5.41356e+006, 0)
   ```

<table id="table_71AEEAE808B9436B9846987A54D5D1D2"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parámetro </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Alturador de la marcha atrás elípsoide, eje del semimajor elípsoide </p> </td> 
   <td colname="col2"> <p>Parámetros del elipsoid utilizado para la proyección. El eje semimajor se especifica en metros. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Falso ayuno </p> </td> 
   <td colname="col2"> <p>El falso tostado del meridiano central de la proyección, en metros. Para UTM, esto siempre es 500.000. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>False Northing </p> </td> 
   <td colname="col2"> <p>El falso northing del ecuador en la proyección, en metros. Para la UTM, es 0 para las zonas del hemisferio norte y 10.000 para las zonas del hemisferio sur. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Coordenadas de la esquina noroeste, coordenadas de la esquina sudeste </p> </td> 
   <td colname="col2"> <p>Coordenadas (en metros proyectados) de las esquinas superior izquierda e inferior derecha de la imagen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Prime Meridian </p> </td> 
   <td colname="col2"> <p>Longitud del meridiano central de la proyección, especificada en grados este de Greenwich. Se pueden utilizar números negativos para especificar grados oeste. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Factor de escala </p> </td> 
   <td colname="col2"> <p>Relación entre el radio del cilindro de la proyección y el eje semimajor del elipsoide. Para las proyecciones de Universal Transverse Mercator (UTM), siempre es 0,9996. </p> </td> 
  </tr> 
 </tbody> 
</table>
