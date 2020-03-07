---
description: Los parámetros numéricos y de cadena toman como valores cadenas y números, respectivamente.
solution: Analytics
title: Parámetros numéricos y de cadena
topic: Data workbench
uuid: 2840967e-dd9e-40b2-91e4-3fdfa38f88e7
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Parámetros numéricos y de cadena{#string-and-numeric-parameters}

Los parámetros numéricos y de cadena toman como valores cadenas y números, respectivamente.

Puede utilizarlos de forma intercambiable, pero los parámetros numéricos deben definirse para que tengan un valor numérico. Puede hacer referencia a parámetros numéricos y de cadena al definir transformaciones, condiciones y dimensiones extendidas, y puede hacer referencia a más de un parámetro en la misma línea.

No se puede hacer referencia a parámetros numéricos [!DNL Input] ni de cadena en los campos o [!DNL Output] campos, pero se puede utilizar un parámetro de cadena para definir un campo de entrada constante. Además, no puede hacer referencia a parámetros numéricos y de cadena en los decodificadores o grupos de decodificadores.

Este ejemplo muestra un [!DNL Log Processing Dataset Include] archivo que define un parámetro de cadena y un parámetro numérico. Tenga en cuenta que el parámetro de cadena, denominado &quot;Valores de búsqueda&quot;, define una ubicación de archivo (Valores de búsqueda\Valores) relativa al directorio de instalación del servidor del área de trabajo de datos.

![](assets/cfg_Parameters_StringNumeric.png)

