---
description: Reglas de sintaxis para fórmulas.
title: Sintaxis de cualquier expresión
uuid: 663e3fd2-80e5-4805-8706-34a0e02ebd0f
exl-id: ca1a52c1-b5bd-48bd-95cd-f8059913bd0a
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '89'
ht-degree: 13%

---

# Sintaxis de cualquier expresión{#syntax-for-any-expression}

Reglas de sintaxis para fórmulas.

* En una fórmula, las palabras clave distinguen entre mayúsculas y minúsculas y deben escribirse exactamente como aparecen.
* En una fórmula, los nombres de métricas, dimensiones y filtros que incluyan espacios deben utilizar guiones bajos entre palabras. Por ejemplo: [!DNL Page_Views]
* Para cadenas dentro de expresiones, debe omitir ciertas comillas simples, comillas dobles y barras invertidas. Por ejemplo:

   * [!DNL “can’t”] es aceptable y no es necesario eludirlo, pero  [!DNL ‘can’t’] es inaceptable y debe escapar como  [!DNL ‘can\’t’].

   * [!DNL c:\windows] se debe escapar como  [!DNL c:\\windows].
