---
description: Al crear una capa vectorial que haga referencia a un archivo de valores separados por tabulaciones (.tsv), los datos vectoriales se obtienen recuperando las instrucciones de dibujo, así como los datos de longitud y latitud del archivo .tsv.
title: Capas vectoriales que hacen referencia a archivos de valores separados por tabuladores
uuid: 42607b34-e9f2-420a-ba5a-05562598b480
exl-id: be16ba73-4a98-472b-98f1-1b32e671b763
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '352'
ht-degree: 6%

---

# Capas vectoriales que hacen referencia a archivos de valores separados por tabuladores{#vector-layers-referencing-tab-separated-values-files}

{{eol}}

Al crear una capa vectorial que haga referencia a un archivo de valores separados por tabulaciones (.tsv), los datos vectoriales se obtienen recuperando las instrucciones de dibujo, así como los datos de longitud y latitud del archivo .tsv.

Definición de una capa vectorial que haga referencia a una [!DNL .tsv] debe tener lo siguiente:

* **A [!DNL .tsv] file** que contiene los datos utilizados para dibujar los vectores en el globo, incluidos los datos de longitud y latitud. Para obtener más información sobre el formato requerido de la variable [!DNL .tsv] archivo, consulte [Formato de archivo TSV vectorial](../../../../home/c-geo-oview/c-wk-img-lyrs/c-wk-vctr-lyrs/c-tab-sep-val-files.md#section-a29012c9ff4444ac8a6d41c68482828e).

* **Un archivo de capa** que especifica la ubicación de la variable [!DNL .tsv] archivo. Para obtener más información sobre el formato requerido del archivo de capa, consulte [Formato de archivo de capa vectorial](../../../../home/c-geo-oview/c-wk-img-lyrs/c-wk-vctr-lyrs/c-tab-sep-val-files.md#section-c430923f341f4c93852e9f24b61e82bf).

## Formato de archivo TSV vectorial {#section-a29012c9ff4444ac8a6d41c68482828e}

La variable [!DNL .tsv] debe contener las tres columnas separadas por tabulaciones siguientes:

* **[!DNL Begin]:** Esta columna debe indicar si se inicia una línea nueva. Los valores de esta columna pueden ser 0 (no comenzar una línea nueva) o 1 (comenzar una línea nueva).
* **[!DNL Longitude]:** Esta columna debe contener valores de longitud.
* **[!DNL Latitude]:** Esta columna debe contener valores de latitud.

>[!NOTE]
>
>Se ignorarán las columnas adicionales.

A continuación se muestra un ejemplo [!DNL .tsv] archivo que contiene datos para una capa vectorial:

![](assets/tsv_vectorlayer.png)

## Formato de archivo de capa vectorial {#section-c430923f341f4c93852e9f24b61e82bf}

Cada archivo de capa vectorial que hace referencia a [!DNL .tsv] Los archivos deben tener el formato siguiente:

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
   <td colname="col2"> <p>Ruta(s) al <span class="filepath"> .tsv</span> archivos que contienen los datos vectoriales. </p> <p>Ejemplo: <span class="filepath"> Mapas\\USVectorData.tsv</span> </p> </td> 
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
