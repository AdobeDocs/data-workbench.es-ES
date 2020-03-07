---
description: Una capa de imagen del terreno muestra imágenes del terreno de la Tierra.
solution: Analytics
title: Capas de imagen de terreno
topic: Data workbench
uuid: 17968293-1ad2-4040-a174-d33f418af9b7
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Capas de imagen de terreno{#terrain-image-layers}

Una capa de imagen del terreno muestra imágenes del terreno de la Tierra.

[!DNL Terrain image layers] se almacenan en el [!DNL Geography] perfil en un formato personalizado. Adobe puede generar estas capas de imagen, o bien el servidor de Área de trabajo de datos puede transformar las imágenes de terreno suministradas por el usuario en capas de terreno adecuadas para su uso en la visualización del globo.

>[!NOTE]
>
>Para trabajar con [!DNL terrain image layers], debe instalar el [!DNL Terrain Images.cfg] archivo proporcionado por Adobe.

Para definir una capa de imagen de terreno, debe tener lo siguiente:

* **Uno o más archivos** de imagen de terreno que contienen las imágenes que se van a mostrar en el globo.
* **Un[!DNL Terrain Images.cfg]archivo** que especifica los archivos de imagen de terreno que se utilizarán para las capas. El [!DNL Terrain Images.cfg] archivo permite agregar una o más fuentes para crear una [!DNL terrain image layer]. El formato del archivo de imagen de terreno determina el tipo de origen que se debe agregar. La siguiente tabla proporciona descripciones de los orígenes de capas de imagen de terreno disponibles, incluidos los formatos de archivo de imagen de terreno admitidos:

<table id="table_CFDF5E61FCCD40B29A9D35FFA42F68D1"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Tipo </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Mapa de bits sin proyectar </p> </td> 
   <td colname="col2"> <p>Crea capas <span class="wintitle"> de imagen de</span> terreno a partir de archivos RGB sin encabezado de 24 bits alineados (no proyectados) con longitud de latitud, donde el norte es la parte superior de la imagen y el este es la derecha. </p> <p>Formatos de imagen admitidos: RAW </p> <p> <p>Nota: Esta fuente requiere información de proyección. Para obtener información sobre los formatos de proyección, consulte <a href="../../../../home/c-get-started/c-im-layers/c-ter-img-layers/c-proj-info-ter-imgs.md#concept-eec35baa01744895b847a02e69dad04e"> Especificación de información de proyección para imágenes</a>de terreno. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Imagen general, no proyectada </p> </td> 
   <td colname="col2"> <p>Crea capas <span class="wintitle"> de imagen de</span> terreno a partir de formatos de imagen alineados (no proyectados) de 24 bits y longitud de latitud, donde el norte es la parte superior de la imagen y el este es la derecha. </p> <p>Formatos de imagen admitidos: BMP, JPG, PNG, TIFF </p> <p> <p>Nota: Esta fuente requiere información de proyección. Para obtener información sobre los formatos de proyección, consulte <a href="../../../../home/c-get-started/c-im-layers/c-ter-img-layers/c-proj-info-ter-imgs.md#concept-eec35baa01744895b847a02e69dad04e"> Especificación de información de proyección para imágenes</a>de terreno. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Imagen con proyección incrustada </p> </td> 
   <td colname="col2"> <p>Crea <span class="wintitle"> capas</span> de imagen de terreno a partir de formatos de imagen que incrustan datos geodésicos en el archivo de imagen. La información de proyección se extrae de la imagen. </p> <p>Formatos de imagen admitidos: Erdas (IMG), GeoTIFF </p> <p> <p>Nota: Esta fuente no suele requerir información de proyección, pero admite la adición de dicha información si es necesario. Para obtener información sobre los formatos de proyección, consulte <a href="../../../../home/c-get-started/c-im-layers/c-ter-img-layers/c-proj-info-ter-imgs.md#concept-eec35baa01744895b847a02e69dad04e"> Especificación de información de proyección para imágenes</a>de terreno. </p> </p> </td> 
  </tr> 
 </tbody> 
</table>

**Definición de una capa de imagen de terreno**

1. En Área de trabajo de datos, en la ficha **[!UICONTROL Admin]** > **[!UICONTROL Dataset and Profile]** , haga clic en la **[!UICONTROL Servers Manager]** miniatura para abrir el [!DNL Servers Manager] espacio de trabajo.
1. En la [!DNL Servers Manager] ventana, haga clic con el botón derecho en el icono del servidor del área de trabajo de datos deseado y haga clic en **[!UICONTROL Server Files]**.
1. En el [!DNL Server Files Manager], haga clic **[!UICONTROL Components]** para ver su contenido. El [!DNL Terrain Images.cfg] archivo se encuentra dentro de este directorio.
1. Haga clic con el botón secundario en la marca de verificación de la columna del nombre del servidor para [!DNL Terrain Images.cfg]y, a continuación, haga clic en **[!UICONTROL Make Local]**. Aparece una marca de verificación en la [!DNL Temp] columna para [!DNL Terrain Images.cfg].
1. Haga clic con el botón secundario en la marca de verificación recién creada en la **[!UICONTROL Temp]** columna y haga clic en **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**. Aparecerá la [!DNL Terrain Images.cfg] ventana.
1. En la [!DNL Terrain Images] ventana, haga clic en **[!UICONTROL component]** para ver su contenido.
1. Haga clic con el botón derecho **[!UICONTROL Sources]** > **[!UICONTROL Add new]** y elija uno de los siguientes tipos de origen:

   * **[!UICONTROL Raw unprojected bitmap]**. (Una vez agregado, este tipo de origen se etiqueta como RawTerrainSource en la [!DNL Terrain Images] ventana).

   * **[!UICONTROL General image, unprojected]**. (Una vez agregado, este tipo de origen se etiqueta [!DNL GDALTerrainSource] en la [!DNL Terrain Images] ventana).

   * **[!UICONTROL Image with embedded projection]**. (Una vez agregado, este tipo de origen se etiqueta [!DNL GDALTerrainSource] en la [!DNL Terrain Images] ventana).

1. Edite los parámetros del origen según sea necesario utilizando el siguiente archivo de ejemplo y la tabla de parámetros como guías.

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
   <td colname="col2"> <p>Opcional para todas las fuentes. Especifica la corrección gamma que se aplicará a la imagen de origen. Esto puede ser deseable debido al hecho de que Área de trabajo de datos se ejecuta normalmente con una configuración de gamma alta. El valor predeterminado es 1. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Altura </p> </td> 
   <td colname="col2"> <p>Necesario para imágenes de mapa de bits sin proyección. Altura de la imagen de origen en píxeles. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Información de proyección </p> </td> 
   <td colname="col2"> <p>Necesario para imágenes de mapa de bits sin proyección e imágenes generales, no proyectadas pero admitidas para imágenes con proyección incrustada. Área de trabajo de datos admite proyecciones de longitud de latitud y proyecciones de Mercator transversal (TM) para capas de imagen de terreno. El formato de proyección predeterminado es la proyección latitud-longitud (LatLonProjection). </p> <p>Para obtener información sobre los formatos de proyección, consulte <a href="../../../../home/c-get-started/c-im-layers/c-ter-img-layers/c-proj-info-ter-imgs.md#concept-eec35baa01744895b847a02e69dad04e"> Especificación de información de proyección para imágenes</a>de terreno. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Imagen de origen </p> </td> 
   <td colname="col2"> <p>Necesario para todas las fuentes. Nombre del archivo de imagen de origen. Puede ser un nombre de archivo o un patrón comodín. El uso de un patrón puede resultar útil si, por ejemplo, se cargan imágenes para la misma región en fechas diferentes, sin ningún cambio en los metadatos asociados. Por lo tanto, un patrón como <span class="filepath"> Tysons Corner *.raw</span> crearía capas a partir de <span class="filepath"> Tysons Corner 050211.raw</span>, <span class="filepath"> Tysons Corner 050218.raw</span>, y así sucesivamente, a medida que se añadan nuevas imágenes, sin necesidad de configuración adicional si los parámetros de los archivos son idénticos. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Calidad de compresión de mosaicos </p> </td> 
   <td colname="col2"> <p>Opcional para todas las fuentes. Para compresión JPEG, un entero de 0 a 100 que especifica cómo equilibrar el tamaño y la calidad de la imagen. (El valor predeterminado es cero.) Un número mayor da como resultado una mejor calidad de imagen, pero produce imágenes más grandes y tiempos de descarga más largos para los usuarios del Área de trabajo de datos. </p> <p> <p>Nota:  La compresión de imágenes por debajo de 70 puede provocar la degradación de la imagen. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Compresor de mosaico </p> </td> 
   <td colname="col2"> <p>Opcional para todas las fuentes. Especifica el método de compresión que se utiliza para escribir archivos de salida. Los únicos métodos admitidos actualmente son RAWRGB (predeterminado, sin compresión) y JPEG. Utilice la compresión JPEG para reducir el tamaño de las capas que se transmiten durante la sincronización de perfiles. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Anchura </p> </td> 
   <td colname="col2"> <p>Necesario para imágenes de mapa de bits sin proyección. Ancho de la imagen de origen en píxeles. </p> </td> 
  </tr> 
 </tbody> 
</table>

1. Edite los parámetros Ubicación de imagen de origen, Almacenamiento de imágenes temporal y Escribir capas en utilizando la siguiente tabla como guía. Estos parámetros se aplican a todos los orígenes de imagen de terreno que defina en la [!DNL Sources] sección de este archivo.

<table id="table_103F02C54ED94C6C922450F5B2781CAE"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parámetro </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Ubicación de imagen de origen </p> </td> 
   <td colname="col2"> <p>Requerido. El directorio que se escanea para que las imágenes se traduzcan en capas de terreno. Si no es una ruta absoluta, se interpreta en relación con el directorio de instalación del servidor de Área de trabajo de datos. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Almacenamiento de imágenes temporales </p> </td> 
   <td colname="col2"> <p>Opcional. Nombre de un directorio que se utiliza para almacenar archivos temporales utilizados en la traducción de imágenes de origen a capas de terreno. Si no es una ruta absoluta, se interpreta en relación con el directorio de instalación del servidor de Área de trabajo de datos. La ubicación predeterminada es el directorio <span class="wintitle"> Temp</span> . </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Escribir capas en </p> </td> 
   <td colname="col2"> <p>Requerido. Directorio en el que se generan las capas de terreno. Normalmente, este es el subdirectorio Mapas de un directorio de perfiles, de modo que la visualización de globos pueda encontrar las capas. </p> </td> 
  </tr> 
 </tbody> 
</table>

1. Para guardar el archivo, haga clic con el botón secundario **[!UICONTROL (modified)]** en la parte superior de la ventana y haga clic en **[!UICONTROL Save]**.
1. Para guardar un archivo actualizado en el equipo del servidor de Área de trabajo de datos, en la [!DNL Server Files Manager], haga clic con el botón secundario en la marca de verificación de [!DNL Terrain Images.cfg] la [!DNL Temp] columna y, a continuación, haga clic en **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>*.

