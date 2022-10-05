---
description: Reglas de sintaxis para fórmulas.
title: Sintaxis de cualquier expresión
uuid: 663e3fd2-80e5-4805-8706-34a0e02ebd0f
exl-id: ca1a52c1-b5bd-48bd-95cd-f8059913bd0a
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '89'
ht-degree: 13%

---

# Sintaxis de cualquier expresión{#syntax-for-any-expression}

{{eol}}

Reglas de sintaxis para fórmulas.

* En una fórmula, las palabras clave distinguen entre mayúsculas y minúsculas y deben escribirse exactamente como aparecen.
* En una fórmula, los nombres de métricas, dimensiones y filtros que incluyan espacios deben utilizar guiones bajos entre palabras. Por ejemplo: [!DNL Page_Views]
* Para cadenas dentro de expresiones, debe omitir ciertas comillas simples, comillas dobles y barras invertidas. Por ejemplo:

   * [!DNL “can’t”] es aceptable y no es necesario escapar, pero [!DNL ‘can’t’] es inaceptable y debe escapar como [!DNL ‘can\’t’].

   * [!DNL c:\windows] debe omitirse como [!DNL c:\\windows].
