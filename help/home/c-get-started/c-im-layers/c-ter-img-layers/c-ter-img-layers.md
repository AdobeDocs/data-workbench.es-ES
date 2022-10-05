---
description: Una capa de imagen del terreno muestra imágenes del terreno de la Tierra.
title: Capas de imagen del terreno
uuid: 17968293-1ad2-4040-a174-d33f418af9b7
exl-id: 754211a7-0b1f-4353-86f8-9c634d70cd83
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '992'
ht-degree: 2%

---

# Capas de imagen del terreno{#terrain-image-layers}

{{eol}}

Una capa de imagen del terreno muestra imágenes del terreno de la Tierra.

[!DNL Terrain image layers] se almacenan en la variable [!DNL Geography] en un formato personalizado. Estas capas de imagen pueden generarse por Adobe, o el servidor de Data Workbench puede transformar las imágenes de terreno suministradas por el usuario en capas de terreno adecuadas para su uso en la visualización del globo.

>[!NOTE]
>
>Para trabajar con [!DNL terrain image layers], debe instalar la variable [!DNL Terrain Images.cfg] archivo proporcionado por Adobe.

Para definir una capa de imagen de terreno, debe tener lo siguiente:

* **Uno o varios archivos de imagen de terreno** que contienen las imágenes que se van a mostrar en el globo.
* **A [!DNL Terrain Images.cfg] file** que especifica los archivos de imagen de terreno que se utilizarán para las capas. La variable [!DNL Terrain Images.cfg] permite agregar una o más fuentes para crear una [!DNL terrain image layer]. El formato del archivo de imagen de terreno determina el tipo de origen que debe añadir. La siguiente tabla proporciona descripciones de los orígenes de capa de imagen de terreno disponibles, incluidos los formatos de archivo de imagen de terreno admitidos:

<table id="table_CFDF5E61FCCD40B29A9D35FFA42F68D1"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Tipo </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Mapa de bits sin procesar </p> </td> 
   <td colname="col2"> <p>Crea <span class="wintitle"> capas de imagen del terreno</span> a partir de archivos RGB sin encabezado de 24 bits alineados (no proyectados) con longitud de latitud, donde el norte es la parte superior de la imagen y el este es la derecha. </p> <p>Formatos de imagen compatibles: RAW </p> <p> <p>Nota: Esta fuente requiere información de proyección. Para obtener información sobre los formatos de proyección, consulte <a href="../../../../home/c-get-started/c-im-layers/c-ter-img-layers/c-proj-info-ter-imgs.md#concept-eec35baa01744895b847a02e69dad04e"> Especificación de la información de proyección para imágenes de terreno</a>. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Imagen general, no proyectada </p> </td> 
   <td colname="col2"> <p>Crea <span class="wintitle"> capas de imagen del terreno</span> desde formatos de imagen alineados (no proyectados) de 24 bits, latitud-longitud, donde norte es la parte superior de la imagen y este es la derecha. </p> <p>Formatos de imagen compatibles: BMP, JPG, PNG, TIFF </p> <p> <p>Nota: Esta fuente requiere información de proyección. Para obtener información sobre los formatos de proyección, consulte <a href="../../../../home/c-get-started/c-im-layers/c-ter-img-layers/c-proj-info-ter-imgs.md#concept-eec35baa01744895b847a02e69dad04e"> Especificación de la información de proyección para imágenes de terreno</a>. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Imagen con proyección incrustada </p> </td> 
   <td colname="col2"> <p>Crea <span class="wintitle"> capas de imagen del terreno</span> desde formatos de imagen que incrustan datos geodésicos en el archivo de imagen. La información de la proyección se extrae de la imagen. </p> <p>Formatos de imagen compatibles: Erdas (IMG), GeoTIFF </p> <p> <p>Nota: Esta fuente no suele requerir información de proyección, pero admite la adición de dicha información si es necesario. Para obtener información sobre los formatos de proyección, consulte <a href="../../../../home/c-get-started/c-im-layers/c-ter-img-layers/c-proj-info-ter-imgs.md#concept-eec35baa01744895b847a02e69dad04e"> Especificación de la información de proyección para imágenes de terreno</a>. </p> </p> </td> 
  </tr> 
 </tbody> 
</table>

**Definición de una capa de imagen de terreno**

1. En Data Workbench, en la **[!UICONTROL Admin]** > **[!UICONTROL Dataset and Profile]** , haga clic en la pestaña **[!UICONTROL Servers Manager]** miniatura para abrir el [!DNL Servers Manager] espacio de trabajo.
1. Dentro de [!DNL Servers Manager] , haga clic con el botón derecho en el icono del servidor de Data Workbench deseado y haga clic en **[!UICONTROL Server Files]**.
1. En el [!DNL Server Files Manager], haga clic en **[!UICONTROL Components]** para ver su contenido. La variable [!DNL Terrain Images.cfg] se encuentra dentro de este directorio.
1. Haga clic con el botón derecho en la marca de verificación de la columna de nombre del servidor para [!DNL Terrain Images.cfg]y haga clic en **[!UICONTROL Make Local]**. Aparece una marca de verificación en la variable [!DNL Temp] para [!DNL Terrain Images.cfg].
1. Haga clic con el botón derecho en la marca de verificación recién creada en la **[!UICONTROL Temp]** y haga clic en **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**. La variable [!DNL Terrain Images.cfg] se abre.
1. En el [!DNL Terrain Images] ventana, haga clic en **[!UICONTROL component]** para ver su contenido.
1. Clic con el botón derecho **[!UICONTROL Sources]** > **[!UICONTROL Add new]** y elija uno de los siguientes tipos de origen:

   * **[!UICONTROL Raw unprojected bitmap]**. (Una vez agregado, este tipo de origen se etiqueta como RawTerrainSource en la variable [!DNL Terrain Images] ).

   * **[!UICONTROL General image, unprojected]**. (Una vez añadido, este tipo de origen se etiqueta [!DNL GDALTerrainSource] en el [!DNL Terrain Images] ).

   * **[!UICONTROL Image with embedded projection]**. (Una vez añadido, este tipo de origen se etiqueta [!DNL GDALTerrainSource] en el [!DNL Terrain Images] ).

1. Edite los parámetros del origen según sea necesario utilizando el siguiente archivo de muestra y la tabla de parámetros como guías.

   ![](assets/cfg_TerrainImages_ALL.png)

<table id="table_345ACB4C48524516AADB731D87FC6792"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parámetro </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Gamma </p> </td> 
   <td colname="col2"> <p>Opcional para todas las fuentes. Especifica la corrección gamma que se aplicará a la imagen de origen. Esto puede ser deseable debido al hecho de que la Data Workbench normalmente se ejecuta con una configuración de gamma alta. El valor predeterminado es 1. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Altura </p> </td> 
   <td colname="col2"> <p>Necesario para imágenes de mapa de bits sin proyectar sin procesar. Altura de la imagen de origen en píxeles. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Información de proyección </p> </td> 
   <td colname="col2"> <p>Necesaria para imágenes de mapa de bits sin proyectar e imágenes generales, no proyectadas, pero compatible con imágenes con proyección incrustada. La Data Workbench admite proyecciones de latitud-longitud y proyecciones de Mercator transversal (TM) para capas de imagen de terreno. El formato de proyección predeterminado es la proyección latitude-longitude (LatLonProjection). </p> <p>Para obtener información sobre los formatos de proyección, consulte <a href="../../../../home/c-get-started/c-im-layers/c-ter-img-layers/c-proj-info-ter-imgs.md#concept-eec35baa01744895b847a02e69dad04e"> Especificación de la información de proyección para imágenes de terreno</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Imagen de origen </p> </td> 
   <td colname="col2"> <p>Necesario para todas las fuentes. Nombre del archivo de imagen de origen. Puede ser un nombre de archivo o un patrón comodín. El uso de un patrón puede resultar útil si, por ejemplo, se cargan imágenes para la misma región en fechas diferentes, sin ningún cambio en los metadatos asociados. Por lo tanto, un patrón como <span class="filepath"> Tysons Corner *.raw</span> crearía capas a partir de <span class="filepath"> Tysons Corner 050211.raw</span>, <span class="filepath"> Tysons Corner 050218.raw</span>, etc. a medida que se añaden nuevas imágenes, sin necesidad de configuración adicional si los parámetros de los archivos son idénticos en los demás casos. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Calidad de compresión de mosaicos </p> </td> 
   <td colname="col2"> <p>Opcional para todas las fuentes. Para la compresión del JPEG, un entero de 0 a 100 que especifica cómo equilibrar el tamaño y la calidad de la imagen. (El valor predeterminado es cero.) Un número mayor mejora la calidad de la imagen, pero genera imágenes más grandes y tiempos de descarga más largos para los usuarios de la Data Workbench. </p> <p> <p>Nota: La compresión de imágenes por debajo de 70 puede causar una degradación de la imagen. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Compresor de mosaicos </p> </td> 
   <td colname="col2"> <p>Opcional para todas las fuentes. Especifica qué método de compresión se utiliza para escribir archivos de salida. Los únicos métodos admitidos actualmente son RAWRGB (el valor predeterminado, sin compresión) y JPEG. Utilice la compresión del JPEG para reducir el tamaño de las capas que se transmiten durante la sincronización de perfiles. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Anchura </p> </td> 
   <td colname="col2"> <p>Necesario para imágenes de mapa de bits sin proyectar sin procesar. Ancho de la imagen de origen en píxeles. </p> </td> 
  </tr> 
 </tbody> 
</table>

1. Edite los parámetros Ubicación de la imagen de origen, Almacenamiento de imágenes temporales y Escribir capas en utilizando la siguiente tabla como guía. Estos parámetros se aplican a todas las fuentes de imagen de terreno que defina en la variable [!DNL Sources] de este archivo.

<table id="table_103F02C54ED94C6C922450F5B2781CAE"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parámetro </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Ubicación de la imagen de origen </p> </td> 
   <td colname="col2"> <p>Requerido. El directorio que se analiza en busca de imágenes para traducirlas en capas de terreno. Si no es una ruta absoluta, se interpreta en relación con el directorio de instalación del servidor de Data Workbench. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Almacenamiento de imágenes temporales </p> </td> 
   <td colname="col2"> <p>Opcional. El nombre de un directorio que se utiliza para almacenar archivos temporales utilizados en la traducción de imágenes de origen a capas de terreno. Si no es una ruta absoluta, se interpreta en relación con el directorio de instalación del servidor de Data Workbench. La ubicación predeterminada es la <span class="wintitle"> Temp</span> directorio. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Escribir capas en </p> </td> 
   <td colname="col2"> <p>Requerido. Directorio en el que se generan las capas de terreno. Normalmente, este es el subdirectorio Mapas de un directorio de perfiles, para que la visualización de Globe pueda encontrar las capas. </p> </td> 
  </tr> 
 </tbody> 
</table>

1. Guarde el archivo haciendo clic con el botón derecho **[!UICONTROL (modified)]** en la parte superior de la ventana y haga clic en **[!UICONTROL Save]**.
1. Para guardar un archivo actualizado en el equipo servidor de Data Workbench, en la [!DNL Server Files Manager], haga clic con el botón derecho en la marca de verificación de [!DNL Terrain Images.cfg] en el [!DNL Temp] y, a continuación, haga clic en **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>*.
