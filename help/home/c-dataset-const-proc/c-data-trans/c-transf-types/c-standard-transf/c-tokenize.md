---
description: La transformación Tokenize aplica iterativamente una expresión regular a la cadena de entrada.
title: Tokenize
uuid: f8430e6c-ec14-4ba6-aeae-92c9f2520a63
exl-id: c1f39b5b-4717-44f6-99c7-4e6a215f3542
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '237'
ht-degree: 4%

---

# Tokenize{#tokenize}

{{eol}}

La transformación Tokenize aplica iterativamente una expresión regular a la cadena de entrada.

Sin embargo, a diferencia de [!DNL RETransform], [!DNL Tokenize] no tiene que coincidir con toda la cadena: la expresión regular utilizada para la variable [!DNL Tokenize] la transformación puede coincidir con un subconjunto de la entrada. Después de encontrar una coincidencia, [!DNL Tokenize] vuelve a aplicar la expresión regular, empezando por el carácter después del final de la última coincidencia.

| Parámetro | Descripción | Predeterminado |
|---|---|---|
| Nombre | Nombre descriptivo de la transformación. Puede introducir cualquier nombre aquí. |  |
| Distinción entre mayúsculas y minúsculas | Verdadero o falso. Especifica si la coincidencia distingue entre mayúsculas y minúsculas. |  |
| Comentarios | Opcional. Notas sobre la transformación. |  |
| Condición | Condiciones en las que se aplica esta transformación. |  |
| Predeterminado | El valor predeterminado que se debe utilizar si se cumple la condición y el valor de entrada no está disponible o la expresión regular no coincide con el valor de entrada. |  |
| Expresión | Expresión regular utilizada para la coincidencia. |  |
| Salidas | Nombres de las cadenas de salida. Puede tener varias salidas para una cadena de entrada determinada. El número de salidas debe corresponder al número de subpatrones de captura en la expresión regular. |  |

En el siguiente ejemplo, la variable [!DNL Tokenize] la transformación utiliza una expresión regular para capturar los nombres de las cadenas de consulta (en cs-uri-query) y mostrar el subpatrón capturado (el nombre de la consulta) en x-pull-query-name.

![](assets/cfg_TransformationType_Tokenize.png)

Para la cadena de consulta &quot;a=b&amp;c=d&quot;, el resultado sería un vector que contenía &quot;a&quot; y &quot;c&quot;.

Para obtener información sobre las expresiones regulares, consulte [Expresiones regulares](../../../../../home/c-dataset-const-proc/c-reg-exp.md#concept-070077baa419475094ef0469e92c5b9c).
