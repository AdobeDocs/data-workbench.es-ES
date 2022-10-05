---
description: Las expresiones de métricas, dimensiones y filtros pueden utilizar identificadores para hacer referencia a métricas, dimensiones y filtros con nombre.
title: Sintaxis para identificadores
uuid: 9cfa188a-05ca-4163-a268-e33fce9a1929
exl-id: 79bc5585-7b21-4a9d-b044-28ff4bc5a885
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '168'
ht-degree: 3%

---

# Sintaxis para identificadores{#syntax-for-identifiers}

{{eol}}

Las expresiones de métricas, dimensiones y filtros pueden utilizar identificadores para hacer referencia a métricas, dimensiones y filtros con nombre.

Estos identificadores distinguen entre mayúsculas y minúsculas y deben escribirse exactamente como están definidos.

Un identificador válido puede contener uno o más de los siguientes elementos:

* Guiones bajos (_). Las puntuaciones de subrayado de un identificador representan espacios en el nombre de la métrica, la dimensión o el filtro. Por ejemplo, la dimensión Referente de sesión sería referida como [!DNL Session_Referrer] en una expresión.
* Signos de porcentaje (%)
* Mayúsculas (A-Z)
* Letra minúscula (a-z)
* Signos del dólar ($)
* Números (0-9), excepto como el primer carácter de un identificador.
* Caracteres no ASCII

Todos los demás caracteres no son válidos en un identificador.

Estas mismas reglas se aplican a los nombres de métricas, dimensiones y filtros cuando se utilizan fuera de las expresiones, excepto que los nombres pueden contener espacios pero no guiones bajos. Por ejemplo, puede definir la dimensión Referente de sesión en el [!DNL Transformation.cfg] como referente de sesión, pero no [!DNL Session_Referrer].
