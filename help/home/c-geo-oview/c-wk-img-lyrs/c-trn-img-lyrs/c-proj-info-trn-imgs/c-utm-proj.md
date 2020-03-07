---
description: La proyección de Universal Transverse Mercator (UTM) está definida por ocho parámetros.
solution: Analytics
title: Proyecciones de Mercator Universal Transversal
topic: Data workbench
uuid: 55421412-5c68-4a4f-88d6-650d5999a77c
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Proyecciones de Mercator Universal Transversal{#universal-transverse-mercator-projections}

La proyección de Universal Transverse Mercator (UTM) está definida por ocho parámetros.

Al especificar una proyección Universal Transverse Mercator para una capa de imagen de terreno, los archivos de imagen de terreno deben alinearse con false (proyectado) hacia el norte hacia la parte superior de la imagen y false hacia el este hacia la derecha de la imagen.

Para especificar una proyección UTM para cualquier origen de imagen de terreno, debe abrir el [!DNL Terrain Images.cfg] archivo en un editor de texto como Bloc de notas, establecer el parámetro Información de proyección en &quot;TransverseMercatorProjection&quot; y agregar la configuración para la proyección UTM.

**Especificación de una proyección de Mercator universal transversal**

1. En el [!DNL Server Files Manager], haga clic **[!UICONTROL Components]** para ver su contenido. El [!DNL Terrain Images.cfg] archivo se encuentra dentro de este directorio.

1. Haga clic con el botón secundario en la marca de verificación de la columna del nombre *del* servidor para [!DNL Terrain Images.cfg]y, a continuación, haga clic en **[!UICONTROL Make Local]**. Aparece una marca de verificación en la [!DNL Temp] columna para [!DNL Terrain Images.cfg].

1. Haga clic con el botón secundario en la marca de verificación recién creada en la [!DNL Temp] columna y haga clic en **[!UICONTROL Open]** > **[!UICONTROL in Notepad]**. El [!DNL Terrain Images.cfg]archivo aparece en una ventana del Bloc de notas.

1. Edite los parámetros de Información de proyección utilizando como guías el siguiente fragmento de archivo de muestra y la tabla de parámetros. Asegúrese de especificar el tipo de proyección como se resalta a continuación.

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

| Parámetro | Descripción |
|---|---|
| Acoplamiento inverso elípsoide, eje semimajor elípsoide | Parámetros del elipsoide utilizado para la proyección. El eje semimajor se especifica en metros. |
| Falso ayuno | El falso ayuno del meridiano central de la proyección, en metros. Para la UTM, esto es siempre 500.000. |
| False Northing | El falso northing del ecuador en la proyección, en metros. Para la UTM, este es 0 para las zonas del hemisferio norte y 10.000 para las zonas del hemisferio sur. |
| Coordenadas de la esquina noroeste, coordenadas de la esquina sudeste | Coordenadas (en metros proyectados) de las esquinas superior izquierda e inferior derecha de la imagen. |
| Primer meridiano | Longitud del meridiano central de la proyección, especificada en grados al este de Greenwich. Los números negativos pueden utilizarse para especificar grados oeste. |
| Factor de escala | Relación entre el radio del cilindro de proyección y el eje semimajor del elipsoide. Para las proyecciones de Universal Transverse Mercator (UTM), esto es siempre 0,9996. |

