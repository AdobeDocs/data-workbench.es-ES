---
description: Las transformaciones y dimensiones utilizan condiciones para determinar cuándo se aplican determinadas instrucciones o acciones a los campos de registro.
title: Acerca de las condiciones
uuid: 882fe761-895c-4226-a019-270c50ae6da2
exl-id: 0d44282f-1327-4f11-90fc-7e6a2ef8dc76
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '149'
ht-degree: 2%

---

# Acerca de las condiciones{#about-conditions}

{{eol}}

Las transformaciones y dimensiones utilizan condiciones para determinar cuándo se aplican determinadas instrucciones o acciones a los campos de registro.

El parámetro Condición de entrada de registro utiliza condiciones para determinar qué entradas de registro deben incluirse en el proceso de construcción del conjunto de datos. Este apéndice describe los distintos tipos de condiciones disponibles en el servidor de Data Workbench.

Una condición se clasifica en una de las dos categorías siguientes:

* **[!DNL Test Operations]:** [!DNL Compare], [!DNL Not Empty], [!DNL Range], [!DNL Regular Expression]y [!DNL String Match] se utilizan condiciones para probar diferentes estados en los campos de registro disponibles.

* **[!DNL Boolean Operations]:** La variable [!DNL And], [!DNL Or]y [!DNL Neither] para combinar las operaciones de prueba descritas anteriormente. Por ejemplo, si tiene un [!DNL Range] condición y [!DNL String Match] condición que debe ser falsa para realizar la acción adecuada, haría que estas dos operaciones fueran secundarias a la [!DNL Neither] condición. Tenga en cuenta que [!DNL And] se utiliza como la raíz de todas las pruebas de condición en el sistema.
