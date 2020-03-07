---
description: La transformación URI Unescape anula los caracteres de una cadena que se han escapado.
solution: Analytics
title: UnescapeURI
topic: Data workbench
uuid: 25e87cc7-812d-4d77-be94-16093e8955fe
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# UnescapeURI{#unescapeuri}

La transformación URI Unescape anula los caracteres de una cadena que se han escapado.

>[!NOTE]
>
>Los caracteres de escape sustituyen a los caracteres no seguros en una cadena URI. Están representados por un triplete que consta de un signo de porcentaje seguido de dos dígitos hexadecimales (por ejemplo, %20).

| Parámetro | Descripción | Valor predeterminado |
|---|---|---|
| Nombre | Nombre descriptivo de la transformación. Aquí puede introducir cualquier nombre. |  |
| Comentarios | Opcional. Notas sobre la transformación. |  |
| Condición | Condiciones en las que se aplica esta transformación. |  |
| Valor predeterminado | El valor predeterminado que se usará si se cumple la condición y el valor de entrada no está disponible. |  |
| Entrada | La cadena URI que se va a evitar. |  |
| Salida | Nombre del campo en el que se va a almacenar la cadena sin escape. |  |

La siguiente transformación anula el valor docname en un campo de encabezado HTTP y almacena el resultado en el campo x-docname-unescaped:

![](assets/cfg_TransformationType_UnescapeURI.png)

Si el valor docname fuera

* [!DNL mysite.net/lending%20and%20leasing%20forms/document%20library/credit%20application.doc]

entonces el valor de x-docname-unescape sería

* [!DNL mysite.net/lending and leasing forms/document library/credit application.doc]

