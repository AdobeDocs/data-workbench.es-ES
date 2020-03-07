---
description: Las expresiones de métrica, dimensión y filtro pueden utilizar identificadores para hacer referencia a métricas, dimensiones y filtros con nombre.
solution: Analytics
title: Sintaxis para identificadores
topic: Data workbench
uuid: 9cfa188a-05ca-4163-a268-e33fce9a1929
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Sintaxis para identificadores{#syntax-for-identifiers}

Las expresiones de métrica, dimensión y filtro pueden utilizar identificadores para hacer referencia a métricas, dimensiones y filtros con nombre.

Estos identificadores distinguen entre mayúsculas y minúsculas y deben escribirse exactamente como están definidos.

Un identificador válido puede contener uno o varios de los siguientes elementos:

* Subrayados (_). Los subrayados de un identificador representan espacios en la métrica, dimensión o nombre del filtro. Por ejemplo, la dimensión Referente de sesión se denominaría [!DNL Session_Referrer] en una expresión.
* Signos porcentuales (%)
* Mayúsculas (A-Z)
* Letra minúscula (a-z)
* Signos de dólar ($)
* Números (0-9), excepto como el primer carácter de un identificador.
* Caracteres no ASCII

El resto de caracteres no son válidos en un identificador.

Estas mismas reglas se aplican a los nombres de métricas, dimensiones y filtros cuando se utilizan fuera de las expresiones, excepto que los nombres pueden contener espacios pero no subrayados. Por ejemplo, puede definir la dimensión Referente de sesión en el [!DNL Transformation.cfg] archivo como Referente de sesión, pero no [!DNL Session_Referrer].
