---
description: Las transformaciones y dimensiones utilizan condiciones para determinar cuándo determinadas instrucciones o acciones se aplican a los campos de registro.
solution: Analytics
title: Acerca de las condiciones
topic: Data workbench
uuid: 882fe761-895c-4226-a019-270c50ae6da2
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Acerca de las condiciones{#about-conditions}

Las transformaciones y dimensiones utilizan condiciones para determinar cuándo determinadas instrucciones o acciones se aplican a los campos de registro.

El parámetro Condición de entrada de registro utiliza condiciones para determinar qué entradas de registro deben incluirse en el proceso de construcción del conjunto de datos. Este apéndice describe los diferentes tipos de condiciones disponibles en el servidor del área de trabajo de datos.

Una condición se divide en dos categorías:

* **[!DNL Test Operations]::**[!DNL Compare],[!DNL Not Empty],[!DNL Range],[!DNL Regular Expression]y[!DNL String Match]condiciones se utilizan para probar distintos estados en los campos de registro disponibles.

* **[!DNL Boolean Operations]::**Las condiciones[!DNL And],[!DNL Or]y[!DNL Neither]se utilizan para combinar las operaciones de ensayo descritas anteriormente. Por ejemplo, si tiene una[!DNL Range]condición y una condición[!DNL String Match]que deben ser ambas falsas para realizar la acción adecuada, haría que estas dos operaciones sean secundarias de la[!DNL Neither]condición. Tenga en cuenta que la[!DNL And]condición se utiliza como raíz de todas las pruebas de condición en el sistema.

