---
description: Al crear una capa vectorial que hace referencia a un archivo de valores separados por tabuladores (.tsv), los datos vectoriales se obtienen recuperando las instrucciones de dibujo, así como los datos de longitud y latitud del archivo .tsv.
solution: Analytics
title: Capas vectoriales que hacen referencia a archivos de valores separados por tabuladores
topic: Data workbench
uuid: 42607b34-e9f2-420a-ba5a-05562598b480
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Capas vectoriales que hacen referencia a archivos de valores separados por tabuladores{#vector-layers-referencing-tab-separated-values-files}

Al crear una capa vectorial que hace referencia a un archivo de valores separados por tabuladores (.tsv), los datos vectoriales se obtienen recuperando las instrucciones de dibujo, así como los datos de longitud y latitud del archivo .tsv.

Para definir una capa vectorial que haga referencia a un [!DNL .tsv] archivo, debe tener lo siguiente:

* **Un[!DNL .tsv]archivo** que contiene los datos utilizados para dibujar los vectores en el globo, incluidos los datos de longitud y latitud. Para obtener más información sobre el formato requerido del [!DNL .tsv] archivo, consulte Formato [de archivo](../../../../home/c-geo-oview/c-wk-img-lyrs/c-wk-vctr-lyrs/c-tab-sep-val-files.md#section-a29012c9ff4444ac8a6d41c68482828e)Vector TSV.

* **Archivo** de capa que especifica la ubicación del [!DNL .tsv] archivo. Para obtener más información sobre el formato requerido del archivo de capa, consulte Formato [de archivo de capa](../../../../home/c-geo-oview/c-wk-img-lyrs/c-wk-vctr-lyrs/c-tab-sep-val-files.md#section-c430923f341f4c93852e9f24b61e82bf)vectorial.

## Formato de archivo Vector TSV {#section-a29012c9ff4444ac8a6d41c68482828e}

El [!DNL .tsv] archivo debe contener las tres columnas separadas por tabuladores siguientes:

* **[!DNL Begin]::**Esta columna debe indicar si se debe comenzar una nueva línea. Los valores de esta columna pueden ser 0 (no comenzar una nueva línea) o 1 (comenzar una nueva línea).
* **[!DNL Longitude]::**Esta columna debe contener valores de longitud.
* **[!DNL Latitude]::**Esta columna debe contener valores de latitud.

>[!NOTE]
>
>Se omiten las columnas adicionales.

A continuación se muestra un archivo de muestra [!DNL .tsv] que contiene datos para una capa vectorial:

![](assets/tsv_vectorlayer.png)

## Formato de archivo de capa vectorial {#section-c430923f341f4c93852e9f24b61e82bf}

Cada archivo de capa vectorial que hace referencia a [!DNL .tsv] archivos debe tener el formato siguiente:

```
Layer = VectorLayer:
  TSV Files = vector: n items
    0 = string: Maps\\File Name.tsv
    1 = string: Maps\\File Name.tsv
    . . .
    n-1 = string: Maps\\File Name.tsv
  Color = v3d: color vector
  Alpha = double: alpha
  Width = double: width
  Error Factor = double: error factor
```

<table id="table_152F73536AB9403AB43854B81D6A9A15"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parámetro </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Archivos TSV </td> 
   <td colname="col2"> <p>Rutas a los archivos <span class="filepath"> .tsv</span> que contienen los datos del vector. </p> <p>Ejemplo: <span class="filepath"> Mapas\\USVectorData.tsv</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Color </td> 
   <td colname="col2"> El vector de color RGB, que se expresa como (rojo, verde, azul). Para cada color del vector, puede introducir un valor de 0,0 a 1,0. Por ejemplo, (1.0, 0.0, 0.0) es rojo brillante y (0.5, 0.5, 0.5) es gris. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Alfa </td> 
   <td colname="col2"> Controla la transparencia de los vectores mostrados en el globo. El intervalo es de 0 a 1, siendo 0 la más transparente. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Anchura </td> 
   <td colname="col2"> Opcional. Define la anchura de los datos en píxeles. El intervalo recomendado es de 1 a 4. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Factor de error </td> 
   <td colname="col2"> Controla la precisión con la que se dibujan los vectores. Para valores más grandes, los vectores se dibujan con menos precisión pero más rápido. El valor predeterminado es 5. </td> 
  </tr> 
 </tbody> 
</table>

