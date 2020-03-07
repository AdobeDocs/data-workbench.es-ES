---
description: La transformación Tokenize aplica de forma iterativa una expresión regular a la cadena de entrada.
solution: Analytics
title: Tokenize
topic: Data workbench
uuid: f8430e6c-ec14-4ba6-aeae-92c9f2520a63
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Tokenize{#tokenize}

La transformación Tokenize aplica de forma iterativa una expresión regular a la cadena de entrada.

Sin embargo, a diferencia de [!DNL RETransform], [!DNL Tokenize] no tiene que coincidir con toda la cadena: la expresión regular utilizada para la [!DNL Tokenize] transformación puede coincidir con un subconjunto de la entrada. Una vez encontrada una coincidencia, aplica la expresión regular de nuevo, empezando por el carácter después del final de la última coincidencia. [!DNL Tokenize]

| Parámetro | Descripción | Valor predeterminado |
|---|---|---|
| Nombre | Nombre descriptivo de la transformación. Aquí puede introducir cualquier nombre. |  |
| Distinción entre mayúsculas y minúsculas | True o false. Especifica si la coincidencia distingue entre mayúsculas y minúsculas. |  |
| Comentarios | Opcional. Notas sobre la transformación. |  |
| Condición | Condiciones en las que se aplica esta transformación. |  |
| Valor predeterminado | El valor predeterminado que se usará si se cumple la condición y el valor de entrada no está disponible o la expresión regular no coincide con el valor de entrada. |  |
| Expresión | Expresión regular utilizada para la coincidencia. |  |
| Salidas | Nombres de las cadenas de salida. Puede tener varias salidas para una cadena de entrada determinada. El número de salidas debe corresponder al número de subpatrones de captura en la expresión regular. |  |

En el ejemplo siguiente, la [!DNL Tokenize] transformación utiliza una expresión regular para capturar los nombres de las cadenas de consulta (en cs-uri-query) y genera el subpatrón capturado (el nombre de la consulta) en x-Pull-query-name.

![](assets/cfg_TransformationType_Tokenize.png)

Para la cadena de consulta &quot;a=b&amp;c=d&quot;, el resultado sería un vector que contuviera &quot;a&quot; y &quot;c&quot;.

Para obtener información sobre las expresiones regulares, consulte Expresiones [regulares](../../../../../home/c-dataset-const-proc/c-reg-exp.md#concept-070077baa419475094ef0469e92c5b9c).
