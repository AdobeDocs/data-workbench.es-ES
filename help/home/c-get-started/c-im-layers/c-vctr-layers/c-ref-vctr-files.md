---
description: Puede crear una capa vectorial que haga referencia a uno o más archivos vectoriales (.vec), que contenga los datos que definen los vectores que se dibujarán en el globo.
title: Definición de capas vectoriales que hagan referencia a archivos vectoriales
uuid: fe6639fb-98fb-4246-9cc1-1a928df6ae0a
exl-id: d78fa7ea-e2a9-42b7-9071-5f72409c5b7a
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '281'
ht-degree: 7%

---

# Definición de capas vectoriales que hagan referencia a archivos vectoriales{#define-vector-layers-referencing-vector-files}

Puede crear una capa vectorial que haga referencia a uno o más archivos vectoriales (.vec), que contenga los datos que definen los vectores que se dibujarán en el globo.

Para definir una capa vectorial que haga referencia a uno o varios archivos [!DNL .vec], debe tener lo siguiente:

* **Uno o más  [!DNL .vec]** archivos que contienen los datos utilizados para dibujar los vectores en el globo.

   >[!NOTE]
   >
   >Para obtener archivos [!DNL .vec] que se van a usar con las capas vectoriales, póngase en contacto con el Adobe.

* **Un** archivo de capa que especifica la ubicación de los  [!DNL .vec] archivos. Para obtener más información sobre el formato requerido del archivo de capa, consulte [Formato del archivo de capa vectorial](../../../../home/c-get-started/c-im-layers/c-vctr-layers/c-ref-vctr-files.md#section-83a0077cf0c8479b9e7b2939bc761af1).

   >[!NOTE]
   >
   >El archivo [!DNL Boundaries.layer], proporcionado con el perfil [!DNL Geography], es una capa vectorial que hace referencia a los archivos [!DNL mwnation.vec], [!DNL mwstate.vec], [!DNL mwcoast.vec], [!DNL mwlake.vec] y [!DNL mwisland.vec].

## Formato de archivo de capa vectorial {#section-83a0077cf0c8479b9e7b2939bc761af1}

Cada archivo de capa vectorial que haga referencia a archivos [!DNL .vec] debe tener el formato siguiente:

```
Layer = VectorLayer:
  Vec Files = vector: n items
    0 = string: Maps\\.vec file 1
    1 = string: Maps\\.vec file 2
    . . .
    n-1 = string: Maps\\.vec file n
  Color = v3d: color vector
  Alpha = double: alpha
  Width = double: width
  Error Factor = double: error factor
```

| Parámetro | Descripción |
|---|---|
| Archivos Vec | Rutas a los [!DNL .vec] archivos que contienen los datos vectoriales. |
| Color | El vector de color RGB, que se expresa como (rojo, verde, azul). Para cada color del vector, se puede introducir un valor de 0,0 a 1,0. Por ejemplo, (1,0, 0,0, 0,0) es de color rojo claro y (0,5, 0,5, 0,5) es de color gris. |
| Alpha | Controla la transparencia de los vectores mostrados en el globo. El rango es de 0 a 1, siendo 0 el más transparente. |
| Anchura | Opcional. Define la anchura de los datos en píxeles. El rango recomendado es de 1 a 4. |
| Factor de error | Controla la precisión con la que se dibujan los vectores. Para valores más grandes, los vectores se dibujan con menos precisión pero más rápido. El valor predeterminado es 5. |

El archivo [!DNL Boundaries.layer] tiene el formato siguiente:

```
 Boundaries.layer file is formatted as follows:
Layer = VectorLayer:
  Vec Files = vector: 5 items
    0 = string: Maps\\mwnation.vec
    1 = string: Maps\\mwstate.vec
    2 = string: Maps\\mwcoast.vec
    3 = string: Maps\\mwlake.vec
    4 = string: Maps\\mwisland.vec
  Color = v3d: (.5,.5,1)
  Alpha = double: .5
  Error Factor = double: 4
```
