---
description: Similar a la transformación AppendURI, la transformación PrependURI afecta al campo interno utilizado por el servidor de Data Workbench para construir la dimensión URI.
title: PrependURI
uuid: 3f2fb1a7-83f7-481e-b892-0937acd379f9
exl-id: c39d9241-ed66-446e-b59d-fdb11942d0e8
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '183'
ht-degree: 6%

---

# PrependURI{#prependuri}

Similar a la transformación AppendURI, la transformación PrependURI afecta al campo interno utilizado por el servidor de Data Workbench para construir la dimensión URI.

La transformación [!DNL PrependURI] funciona añadiendo el valor del campo de entrada identificado al frente del valor que se encuentra en el URI.

| Parámetro | Descripción | Predeterminado |
|---|---|---|
| Nombre | Nombre descriptivo de la transformación. Puede introducir cualquier nombre aquí. |  |
| Comentarios | Opcional. Notas sobre la transformación. |  |
| Condición | Condiciones en las que se aplica esta transformación. |  |
| Predeterminado | El valor predeterminado que se debe utilizar si se cumple la condición y el valor de entrada no está disponible. |  |
| Entrada | Nombre del campo cuyo valor va precedido del URI. |  |

El siguiente ejemplo simplemente antepone el campo s-dns al URI, ampliando la representación de la dimensión URI para incluir el dominio solicitado por el dispositivo cliente.

![](assets/cfg_TransformationType_PrependURI.png)

En este ejemplo, anteponiendo el campo s-dns al URI

* [!DNL /modelview.asp&id=login]

da como resultado la siguiente dirección URL:

* [!DNL www.adobe.com/modelview.asp?id=login]

Ahora el URI se amplía para incluir el dominio solicitado.
