---
description: Reglas de sintaxis para fórmulas.
solution: Analytics
title: Sintaxis de cualquier expresión
topic: Data workbench
uuid: 663e3fd2-80e5-4805-8706-34a0e02ebd0f
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Sintaxis de cualquier expresión{#syntax-for-any-expression}

Reglas de sintaxis para fórmulas.

* En una fórmula, las palabras clave distinguen entre mayúsculas y minúsculas y deben escribirse exactamente como aparecen.
* En una fórmula, los nombres de métricas, dimensiones y filtros que incluyan espacios deben utilizar caracteres de subrayado entre palabras. Por ejemplo: [!DNL Page_Views]
* Para cadenas dentro de expresiones, debe omitir ciertas comillas simples, comillas dobles y barras invertidas. Por ejemplo:

   * [!DNL “can’t”] es aceptable y no necesita ser eludido, pero [!DNL ‘can’t’] es inaceptable y debe eludirse como [!DNL ‘can\’t’].

   * [!DNL c:\windows] debe ser escapada como [!DNL c:\\windows].

