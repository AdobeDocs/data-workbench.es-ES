---
description: Puede crear una capa vectorial que haga referencia a uno o más archivos vectoriales (.vec), que contenga los datos que definen los vectores que se dibujarán en el globo.
title: Definición de capas vectoriales que hacen referencia a archivos vectoriales
uuid: 162d4ecc-d305-42e3-a5d4-0c1609a40f29
exl-id: c6da3cd9-f42a-4e9c-ae48-9f4ffdc42f7b
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '281'
ht-degree: 7%

---

# Definición de capas vectoriales que hacen referencia a archivos vectoriales{#defining-vector-layers-referencing-vector-files}

{{eol}}

Puede crear una capa vectorial que haga referencia a uno o más archivos vectoriales (.vec), que contenga los datos que definen los vectores que se dibujarán en el globo.

Definición de una capa vectorial que haga referencia a una o más [!DNL .vec]debe tener lo siguiente:

* Uno o más [!DNL .vec]archivos que contienen los datos utilizados para dibujar los vectores en el globo.

   >[!NOTE]
   >
   >Para obtener [!DNL .vec] archivos para usar con las capas vectoriales, póngase en contacto con el Adobe.

* Un archivo de capa que especifica la ubicación del [!DNL .vec] archivos. Para obtener más información sobre el formato requerido del archivo de capa, consulte [Formato de archivo de capa vectorial](../../../../home/c-geo-oview/c-wk-img-lyrs/c-wk-vctr-lyrs/c-def-vctr-files.md#section-530d03f41ede4a339aebbb680e15240a).

   >[!NOTE]
   >
   >La variable [!DNL Boundaries.layer] , que se proporciona con la variable [!DNL Geography] perfil, es una capa vectorial que hace referencia al [!DNL mwnation.vec], [!DNL mwstate.vec], [!DNL mwcoast.vec], [!DNL mwlake.vec]y [!DNL mwisland.vec] archivos.

## Formato de archivo de capa vectorial {#section-530d03f41ede4a339aebbb680e15240a}

Cada archivo de capa vectorial que hace referencia a [!DNL .vec]Los archivos deben tener el formato siguiente:

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
| Archivos Vec | Ruta(s) al [!DNL .vec] archivos que contienen los datos vectoriales. |
| Color | El vector de color RGB, que se expresa como (rojo, verde, azul). Para cada color del vector, se puede introducir un valor de 0,0 a 1,0. Por ejemplo, (1,0, 0,0, 0,0) es de color rojo claro y (0,5, 0,5, 0,5) es de color gris. |
| Alpha | Controla la transparencia de los vectores mostrados en el globo. El rango es de 0 a 1, siendo 0 el más transparente. |
| Anchura | Opcional. Define la anchura de los datos en píxeles. El rango recomendado es de 1 a 4. |
| Factor de error | Controla la precisión con la que se dibujan los vectores. Para valores más grandes, los vectores se dibujan con menos precisión pero más rápido. El valor predeterminado es 5. |

La variable [!DNL Boundaries.layer] tiene el formato siguiente:

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
