---
description: Al crear una capa vectorial que haga referencia a un archivo de valores separados por tabulaciones (.tsv), los datos vectoriales se obtienen recuperando las instrucciones de dibujo, así como los datos de longitud y latitud del archivo .tsv.
title: Capas vectoriales que hacen referencia a archivos de valores separados por tabuladores
uuid: 42607b34-e9f2-420a-ba5a-05562598b480
exl-id: be16ba73-4a98-472b-98f1-1b32e671b763,7b0b0286-072b-4b31-b6ec-ced322da5236
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '352'
ht-degree: 6%

---

# Capas vectoriales que hacen referencia a archivos de valores separados por tabuladores{#vector-layers-referencing-tab-separated-values-files}

Al crear una capa vectorial que haga referencia a un archivo de valores separados por tabulaciones (.tsv), los datos vectoriales se obtienen recuperando las instrucciones de dibujo, así como los datos de longitud y latitud del archivo .tsv.

Para definir una capa vectorial que haga referencia a un archivo [!DNL .tsv], debe tener lo siguiente:

* **Un  [!DNL .tsv]** archivo que contiene los datos utilizados para dibujar los vectores en el globo, incluidos los datos de longitud y latitud. Para obtener más información sobre el formato requerido del archivo [!DNL .tsv], consulte [Formato de archivo TSV vectorial](../../../../home/c-geo-oview/c-wk-img-lyrs/c-wk-vctr-lyrs/c-tab-sep-val-files.md#section-a29012c9ff4444ac8a6d41c68482828e).

* **Un** archivo de capa que especifica la ubicación del  [!DNL .tsv] archivo. Para obtener más información sobre el formato requerido del archivo de capa, consulte [Formato del archivo de capa vectorial](../../../../home/c-geo-oview/c-wk-img-lyrs/c-wk-vctr-lyrs/c-tab-sep-val-files.md#section-c430923f341f4c93852e9f24b61e82bf).

## Formato de archivo Vector TSV {#section-a29012c9ff4444ac8a6d41c68482828e}

El archivo [!DNL .tsv] debe contener las tres columnas separadas por tabulaciones siguientes:

* **[!DNL Begin]:** Esta columna debe indicar si se inicia una línea nueva. Los valores de esta columna pueden ser 0 (no comenzar una línea nueva) o 1 (comenzar una línea nueva).
* **[!DNL Longitude]:** Esta columna debe contener valores de longitud.
* **[!DNL Latitude]:** Esta columna debe contener valores de latitud.

>[!NOTE]
>
>Se ignorarán las columnas adicionales.

A continuación se muestra un archivo [!DNL .tsv] de muestra que contiene datos para una capa vectorial:

![](assets/tsv_vectorlayer.png)

## Formato de archivo de capa vectorial {#section-c430923f341f4c93852e9f24b61e82bf}

Cada archivo de capa vectorial que haga referencia a archivos [!DNL .tsv] debe tener el formato siguiente:

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
   <td colname="col2"> <p>Rutas a los <span class="filepath"> archivos .tsv</span> que contienen los datos del vector. </p> <p>Ejemplo: <span class="filepath"> Mapas\\USVectorData.tsv</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Color </td> 
   <td colname="col2"> El vector de color RGB, que se expresa como (rojo, verde, azul). Para cada color del vector, se puede introducir un valor de 0,0 a 1,0. Por ejemplo, (1,0, 0,0, 0,0) es de color rojo claro y (0,5, 0,5, 0,5) es de color gris. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Alpha </td> 
   <td colname="col2"> Controla la transparencia de los vectores mostrados en el globo. El rango es de 0 a 1, siendo 0 el más transparente. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Anchura </td> 
   <td colname="col2"> Opcional. Define la anchura de los datos en píxeles. El rango recomendado es de 1 a 4. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Factor de error </td> 
   <td colname="col2"> Controla la precisión con la que se dibujan los vectores. Para valores más grandes, los vectores se dibujan con menos precisión pero más rápido. El valor predeterminado es 5. </td> 
  </tr> 
 </tbody> 
</table>
