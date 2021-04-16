---
description: La transformación URI Unescape evita cualquier carácter de una cadena que se haya escapado.
title: UnescapeURI
uuid: 25e87cc7-812d-4d77-be94-16093e8955fe
exl-id: abf20906-5052-4bbe-9ffb-522b850669a6
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '160'
ht-degree: 6%

---

# UnescapeURI{#unescapeuri}

La transformación URI Unescape evita cualquier carácter de una cadena que se haya escapado.

>[!NOTE]
>
>Los caracteres de escape reemplazan a los caracteres no seguros en una cadena URI. Están representados por un triplete que consta de un signo de porcentaje seguido de dos dígitos hexadecimales (por ejemplo, %20).

| Parámetro | Descripción | Predeterminado |
|---|---|---|
| Nombre | Nombre descriptivo de la transformación. Puede introducir cualquier nombre aquí. |  |
| Comentarios | Opcional. Notas sobre la transformación. |  |
| Condición | Condiciones en las que se aplica esta transformación. |  |
| Predeterminado | El valor predeterminado que se debe utilizar si se cumple la condición y el valor de entrada no está disponible. |  |
| Entrada | La cadena de URI que se va a omitir. |  |
| Salida | Nombre del campo en el que se almacenará la cadena sin escape. |  |

La siguiente transformación evita el escape del valor docname en un campo de encabezado HTTP y almacena el resultado en el campo x-docname-unescaped:

![](assets/cfg_TransformationType_UnescapeURI.png)

Si el valor docname fuera

* [!DNL mysite.net/lending%20and%20leasing%20forms/document%20library/credit%20application.doc]

entonces el valor de x-docname-unescape sería

* [!DNL mysite.net/lending and leasing forms/document library/credit application.doc]
