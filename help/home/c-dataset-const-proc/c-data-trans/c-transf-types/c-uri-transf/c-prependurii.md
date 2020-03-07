---
description: De forma similar a la transformación AppendURI, la transformación PrependURI afecta al campo interno utilizado por el servidor del área de trabajo de datos para construir la dimensión URI.
solution: Analytics
title: PrependURI
topic: Data workbench
uuid: 3f2fb1a7-83f7-481e-b892-0937acd379f9
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# PrependURI{#prependuri}

De forma similar a la transformación AppendURI, la transformación PrependURI afecta al campo interno utilizado por el servidor del área de trabajo de datos para construir la dimensión URI.

La [!DNL PrependURI] transformación funciona agregando el valor en el campo de entrada identificado al principio del valor que se encuentra actualmente en el URI.

| Parámetro | Descripción | Valor predeterminado |
|---|---|---|
| Nombre | Nombre descriptivo de la transformación. Aquí puede introducir cualquier nombre. |  |
| Comentarios | Opcional. Notas sobre la transformación. |  |
| Condición | Condiciones en las que se aplica esta transformación. |  |
| Valor predeterminado | El valor predeterminado que se usará si se cumple la condición y el valor de entrada no está disponible. |  |
| Entrada | Nombre del campo cuyo valor va precedido del URI. |  |

El siguiente ejemplo simplemente antepone el campo s-dns al URI, extendiendo la representación de la dimensión URI para incluir el dominio solicitado por el dispositivo cliente.

![](assets/cfg_TransformationType_PrependURI.png)

En este ejemplo, anteponiendo el campo s-dns al URI

* [!DNL /modelview.asp&id=login]

da como resultado la siguiente dirección URL:

* [!DNL www.adobe.com/modelview.asp?id=login]

Ahora el URI se amplía para incluir el dominio solicitado.
