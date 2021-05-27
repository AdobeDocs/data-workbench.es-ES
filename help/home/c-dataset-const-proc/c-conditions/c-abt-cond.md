---
description: Las transformaciones y dimensiones utilizan condiciones para determinar cuándo se aplican determinadas instrucciones o acciones a los campos de registro.
title: Acerca de las condiciones
uuid: 882fe761-895c-4226-a019-270c50ae6da2
exl-id: 0d44282f-1327-4f11-90fc-7e6a2ef8dc76
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '149'
ht-degree: 2%

---

# Acerca de las condiciones{#about-conditions}

Las transformaciones y dimensiones utilizan condiciones para determinar cuándo se aplican determinadas instrucciones o acciones a los campos de registro.

El parámetro Condición de entrada de registro utiliza condiciones para determinar qué entradas de registro deben incluirse en el proceso de construcción del conjunto de datos. Este apéndice describe los distintos tipos de condiciones disponibles en el servidor de Data Workbench.

Una condición se clasifica en una de las dos categorías siguientes:

* **[!DNL Test Operations]:** [!DNL Compare],  [!DNL Not Empty],  [!DNL Range],  [!DNL Regular Expression] y  [!DNL String Match] condiciones se utilizan para probar distintos estados en los campos de registro disponibles.

* **[!DNL Boolean Operations]:** Las  [!DNL And]condiciones  [!DNL Or],  [!DNL Neither]  y se utilizan para combinar las operaciones de prueba descritas anteriormente. Por ejemplo, si tiene una condición [!DNL Range] y una condición [!DNL String Match] que deben ser ambas falsas para realizar la acción adecuada, haría que estas dos operaciones sean secundarias de la condición [!DNL Neither] . Tenga en cuenta que la condición [!DNL And] se utiliza como raíz de todas las pruebas de condición en el sistema.
