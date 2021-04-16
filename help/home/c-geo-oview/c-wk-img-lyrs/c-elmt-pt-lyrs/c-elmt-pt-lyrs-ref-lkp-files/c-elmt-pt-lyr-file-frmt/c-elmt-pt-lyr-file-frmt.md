---
description: Formato de información sobre el archivo de capa de punto de elemento.
title: Formato de archivo de capa de punto de elemento
uuid: a8b3d2f4-0ed2-480d-a2a6-75d43025a579
exl-id: 125796f6-a447-4f12-bcf2-3e669783cf1e
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '418'
ht-degree: 5%

---

# Formato de archivo de capa de punto de elemento{#element-point-layer-file-format}

Formato de información sobre el archivo de capa de punto de elemento.

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

<table id="table_B2BC5FE8C80E4680B9A565878192D75B"> 
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
   <td colname="col2"> <p>Nombre de la columna del archivo de búsqueda que contiene los datos de clave comunes, lo que permite al servidor de Data Workbench integrar los datos en el archivo de búsqueda en el conjunto de datos. Debe ser la primera columna del archivo de búsqueda. </p> <p>Cada fila de esta columna es un elemento de una dimensión. Esta dimensión debe definirse en el archivo <span class="filepath"> Transformation.cfg</span> o en un archivo de inclusión de conjunto de datos de transformación y especificarse en el parámetro de Dimension de este archivo. Para obtener más información sobre los archivos de configuración de transformación, consulte la <i>Guía de configuración de conjuntos de datos</i>. </p> </td> 
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
     <ul id="ul_CBB26B32505846A39FEB85E831E1C7AB"> 
      <li id="li_B31528A8858C4418ABCDFF0B4EFB25D7">Modo de procesamiento 1. El tamaño de los puntos se define en el espacio de pantalla (los puntos permanecen en un tamaño constante en relación con la pantalla del equipo). Los puntos se representan con polígonos, por lo que no hay límite superior en el tamaño de punto. Este es el modo de renderización predeterminado. </li> 
      <li id="li_CA0C3E0DBF004ADBB4D7819C0BF192FC">Modo de procesamiento 2. El tamaño del punto se define en el espacio del mundo (los puntos permanecen con un tamaño constante en relación con el globo). Los puntos se representan con polígonos, por lo que no hay límite superior en el tamaño de punto. </li> 
      <li id="li_8F8729976DDB434D869E81D4381E2688">Modo de procesamiento 3. El tamaño de punto se define en el espacio de pantalla. Los puntos se procesan mediante puntos suaves de OpenGL. </li> 
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
