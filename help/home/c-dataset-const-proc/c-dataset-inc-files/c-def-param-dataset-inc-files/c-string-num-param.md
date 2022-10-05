---
description: Los parámetros numéricos y de cadena toman como valores las cadenas y los números, respectivamente.
title: Parámetros numéricos y de cadena
uuid: 2840967e-dd9e-40b2-91e4-3fdfa38f88e7
exl-id: 37d004da-cde7-4b67-b0cb-0acbb6d8ad68
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '147'
ht-degree: 5%

---

# Parámetros numéricos y de cadena{#string-and-numeric-parameters}

{{eol}}

Los parámetros numéricos y de cadena toman como valores las cadenas y los números, respectivamente.

Puede utilizarlos de forma intercambiable, pero los parámetros numéricos deben definirse para tener un valor numérico. Puede hacer referencia a parámetros numéricos y de cadena al definir transformaciones, condiciones y dimensiones extendidas, y puede hacer referencia a más de un parámetro en la misma línea.

No puede hacer referencia a parámetros numéricos ni de cadena en [!DNL Input] o [!DNL Output] , pero puede utilizar un parámetro de cadena para definir un campo de entrada constante. Además, no se puede hacer referencia a parámetros numéricos y de cadena en los decodificadores o grupos de decodificadores.

Este ejemplo muestra un [!DNL Log Processing Dataset Include] que define un parámetro de cadena y un parámetro numérico. Tenga en cuenta que el parámetro de cadena, llamado &quot;Valores de búsqueda&quot;, define una ubicación de archivo (Valores de búsqueda\Valores) en relación con el directorio de instalación del servidor de Data Workbench.

![](assets/cfg_Parameters_StringNumeric.png)
