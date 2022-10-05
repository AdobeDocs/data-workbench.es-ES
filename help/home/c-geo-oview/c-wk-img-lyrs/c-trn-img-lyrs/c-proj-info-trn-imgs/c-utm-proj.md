---
description: La proyección del Universal Transverse Mercator (UTM) se define mediante ocho parámetros.
title: Proyecciones de Universal Transverse Mercator
uuid: 55421412-5c68-4a4f-88d6-650d5999a77c
exl-id: 7d7610c3-14e7-474e-b792-ad413c86a2ef
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '333'
ht-degree: 3%

---

# Proyecciones de Universal Transverse Mercator{#universal-transverse-mercator-projections}

{{eol}}

La proyección del Universal Transverse Mercator (UTM) se define mediante ocho parámetros.

Al especificar una proyección de Universal Transverse Mercator para una capa de imagen de terreno, los archivos de imagen de terreno deben alinearse con false (proyectado) al norte hacia la parte superior de la imagen y false al este hacia la derecha de la imagen.

Para especificar una proyección de UTM para cualquier origen de imagen de terreno, debe abrir el [!DNL Terrain Images.cfg] en un editor de texto como el Bloc de notas, establezca el parámetro Información de proyección en &quot;TransverseMercatorProjection&quot; y agregue la configuración para la proyección de UTM.

**Especificación de una proyección de Universal Transverse Mercator**

1. En el [!DNL Server Files Manager], haga clic en **[!UICONTROL Components]** para ver su contenido. La variable [!DNL Terrain Images.cfg] se encuentra dentro de este directorio.

1. Haga clic con el botón derecho en la marca de verificación de la *nombre del servidor* para [!DNL Terrain Images.cfg]y haga clic en **[!UICONTROL Make Local]**. Aparece una marca de verificación en la variable [!DNL Temp] para [!DNL Terrain Images.cfg].

1. Haga clic con el botón derecho en la marca de verificación recién creada en la [!DNL Temp] y haga clic en **[!UICONTROL Open]** > **[!UICONTROL in Notepad]**. La variable [!DNL Terrain Images.cfg]aparece en la ventana Bloc de notas.

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

| Parámetro | Descripción |
|---|---|
| Alturador de la marcha atrás elípsoide, eje del semimajor elípsoide | Parámetros del elipsoid utilizado para la proyección. El eje semimajor se especifica en metros. |
| Falso ayuno | El falso tostado del meridiano central de la proyección, en metros. Para UTM, esto siempre es 500.000. |
| False Northing | El falso northing del ecuador en la proyección, en metros. Para la UTM, es 0 para las zonas del hemisferio norte y 10.000 para las zonas del hemisferio sur. |
| Coordenadas de la esquina noroeste, coordenadas de la esquina sudeste | Coordenadas (en metros proyectados) de las esquinas superior izquierda e inferior derecha de la imagen. |
| Prime Meridian | Longitud del meridiano central de la proyección, especificada en grados este de Greenwich. Se pueden utilizar números negativos para especificar grados oeste. |
| Factor de escala | Relación entre el radio del cilindro de la proyección y el eje semimajor del elipsoide. Para las proyecciones de Universal Transverse Mercator (UTM), siempre es 0,9996. |
