---
description: Al crear una capa de punto de elemento que haga referencia a un archivo de búsqueda para obtener datos de latitud y longitud, la ubicación del punto se obtiene recuperando cada elemento y su latitud y longitud asociadas del archivo de búsqueda.
title: Definición de capas de puntos de elementos que hacen referencia a archivos de búsqueda
uuid: 32c8de7a-4316-4f91-9810-7f584bc7fb0b
exl-id: 2275fa8e-82fe-49e4-ab3e-91ec6ecb6233
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '846'
ht-degree: 3%

---

# Definición de capas de puntos de elementos que hacen referencia a archivos de búsqueda{#define-element-point-layers-referencing-lookup-files}

Al crear una capa de punto de elemento que haga referencia a un archivo de búsqueda para obtener datos de latitud y longitud, la ubicación del punto se obtiene recuperando cada elemento y su latitud y longitud asociadas del archivo de búsqueda.

>[!NOTE]
>
>En lugar de utilizar un archivo de búsqueda, puede utilizar la funcionalidad Puntos dinámicos, que incrusta la latitud y longitud de una ubicación en el nombre de cada elemento de una dimensión. Consulte [Definición de capas de puntos de elementos mediante puntos dinámicos](../../../../home/c-get-started/c-im-layers/c-elmt-pt-layers/c-elmt-pt-dyn-pts.md#concept-51adc5e1df8a48e7bd7a582967e4c512).

Para definir una capa de punto de elemento que haga referencia a un archivo de búsqueda, debe crear o tener ya disponible lo siguiente:

* **Una** dimensión definida en  [!DNL Transformation.cfg file] o un  [!DNL transformation dataset include] archivo. Para obtener información sobre los archivos de configuración de transformación, consulte la *Guía de configuración de conjuntos de datos*.

* **Un** archivo de búsqueda que contiene los datos utilizados para trazar cada punto de datos. Este archivo debe contener al menos tres columnas de datos por cada punto de datos: la clave, la longitud y la latitud. Para obtener más información sobre el formato requerido del archivo de búsqueda, consulte [Formato del archivo de capa de punto de elemento](../../../../home/c-get-started/c-im-layers/c-elmt-pt-layers/c-elp-ref-lkup-files.md#section-52d7e92be8354d979af9e7a2210b76f2).

* **Un** archivo de capa que especifica la ubicación del archivo de búsqueda e identifica la dimensión y métrica relacionadas, así como los nombres de columna de clave, longitud y latitud en el archivo de búsqueda. Para obtener más información sobre el formato requerido del archivo de capa, consulte [Formato del archivo de capa de punto de elemento](../../../../home/c-get-started/c-im-layers/c-elmt-pt-layers/c-elp-ref-lkup-files.md#section-52d7e92be8354d979af9e7a2210b76f2).

   >[!NOTE]
   >
   >El archivo [!DNL Zip Points.layer], proporcionado con el perfil [!DNL Geography], es una capa de punto de elemento que identifica el archivo [!DNL Zipcode.dim], el archivo [!DNL Sessions.metric], el archivo de búsqueda [!DNL Zip Points.txt] y los nombres de las columnas de clave, longitud, latitud y nombre del archivo de búsqueda.

## Formato del archivo de búsqueda de puntos de elemento {#section-0bc8c652c1bd40eb84078f2af71a5c06}

El archivo de búsqueda de capas de punto de elemento debe contener al menos las tres columnas siguientes:

* **[!DNL Key]columna:** Esta columna debe contener datos de clave comunes, lo que permite al servidor de Data Workbench conectar los datos del archivo de búsqueda con los del conjunto de datos. La columna [!DNL key] debe ser la primera columna del archivo de búsqueda. Cada fila de esta columna identifica un elemento de la dimensión.

* **[!DNL Longitude]columna:** Esta columna debe contener la longitud de cada punto de datos de la  [!DNL Key] columna.

* **[!DNL Latitude]columna:** Esta columna debe contener la latitud de cada punto de datos de la  [!DNL Key] columna.

* **[!DNL Name]columna (Opcional):** si desea especificar un nombre para que se muestre en el mapa para cada punto de datos, puede incluir una  [!DNL Name] columna en el archivo de búsqueda.

Cada fila del archivo de búsqueda [!DNL Zip Points.txt] contiene un código postal en la primera columna seguido de la longitud, la latitud y el nombre de ciudad asociado.

```
tude, and associated city name.
ZIP_CODE LATITUDE LONGITUDE NAME
00210 +43.005895 -071.013202 PORTSMOUTH, NH
00211 +43.005895 -071.013202 PORTSMOUTH, NH
...
```

## Formato de archivo de capa de punto de elemento {#section-52d7e92be8354d979af9e7a2210b76f2}

Cada archivo de capa de punto de elemento [!DNL .layer] que hace referencia a un archivo de búsqueda debe tener el formato siguiente:

```
Layer = ElementPointLayer:
  Data Paths = vector: 1 items
    0 = Path: Maps\\Lookup File Name.txt
  Longitude Column = string: Longitude Column Name
  Latitude Column = string: Latitude Column Name
  Name Column = string: Location Column Name
  Key Column = string: Key Column Name
  Dimension = ref: wdata/model/dim/Dimension Name
  Metric = ref: wdata/model/metric/Metric Name
  Scale = double: Scale
  Color = v3d: RGB Color Vector
  Rendering Mode = int: Mode Number
```

<table id="table_7287F8869DD04886BE1477CBB11EB796"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parámetro </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Rutas de datos </td> 
   <td colname="col2"> Ruta al archivo de búsqueda que contiene datos de latitud y longitud. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Columna de longitud </td> 
   <td colname="col2"> Nombre de la columna del archivo de búsqueda que contiene los datos de longitud. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Columna Latitude </td> 
   <td colname="col2"> Nombre de la columna del archivo de búsqueda que contiene los datos de latitud. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Columna Nombre </td> 
   <td colname="col2"> Opcional. Nombre de la columna del archivo de búsqueda que contiene los nombres de las ubicaciones representadas por los datos de latitud y longitud. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Columna clave </td> 
   <td colname="col2"> <p>Nombre de la columna del archivo de búsqueda que contiene los datos de clave comunes, lo que permite al servidor de Data Workbench integrar los datos en el archivo de búsqueda en el conjunto de datos. Debe ser la primera columna del archivo de búsqueda. </p> <p>Cada fila de esta columna es un elemento de una dimensión. Esta dimensión debe definirse en el archivo <span class="filepath"> Transformation.cfg</span> o en un archivo <span class="wintitle"> conjunto de datos de transformación include</span> y especificarse en el parámetro de Dimension de este archivo. Para obtener más información sobre los archivos de configuración de transformación, consulte la <i>Guía de configuración de conjuntos de datos</i>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Dimensión </td> 
   <td colname="col2">Nombre de la dimensión (definida en un archivo de configuración de transformación) que contiene elementos que corresponden a las filas de datos de la columna <span class="wintitle"> Clave</span>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Métrica </td> 
   <td colname="col2"> Nombre de la métrica que se evalúa sobre la dimensión especificada en el parámetro de Dimension. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Escala </td> 
   <td colname="col2"> Opcional. Valor utilizado para cambiar el tamaño de los puntos de la capa. El valor predeterminado es 100. Los valores más grandes hacen que los puntos sean más grandes y los valores más pequeños los hacen más pequeños. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Color </td> 
   <td colname="col2"> Opcional. El vector de color RGB, que se expresa como (rojo, verde, azul). Para cada color del vector, se puede introducir un valor de 0,0 a 1,0. Por ejemplo, (1,0, 0,0, 0,0) es de color rojo claro y (0,5, 0,5, 0,5) es de color gris. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Modo de procesamiento </td> 
   <td colname="col2"> <p>Opcional. Valor entero que representa el modo de renderización que se utilizará para la capa. Los tres modos disponibles son los siguientes: 
     <ul id="ul_F15E43B3BFE54CDD8026837027E25819"> 
      <li id="li_5405D939540E4D0FA7828D2623D72C44">Modo de procesamiento 1. El tamaño de los puntos se define en el espacio de pantalla (los puntos permanecen en un tamaño constante en relación con la pantalla del equipo). Los puntos se representan con polígonos, por lo que no hay límite superior en el tamaño de punto. Este es el modo de renderización predeterminado. </li> 
      <li id="li_61C5AA926777449E8804C7BCE9E46F9B">Modo de procesamiento 2. El tamaño del punto se define en el espacio del mundo (los puntos permanecen con un tamaño constante en relación con el globo). Los puntos se representan con polígonos, por lo que no hay límite superior en el tamaño de punto. </li> 
      <li id="li_C00527F959354D3BB7422EFFE1FB5135">Modo de procesamiento 3. El tamaño de punto se define en el espacio de pantalla. Los puntos se procesan mediante puntos suaves de OpenGL. </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

El archivo [!DNL Zip Points.layer] tiene el formato siguiente:

```
Layer = ElementPointLayer:
  Data Paths = vector: 1 items
    0 = Path: Maps\\Zip Points.txt
  Longitude Column = string: LONGITUDE
  Latitude Column = string: LATITUDE
  Name Column = string: NAME
  Key Column = string: ZIP_CODE
  Dimension = ref: wdata/model/dim/Zipcode
  Metric = ref: wdata/model/metric/Sessions
```
