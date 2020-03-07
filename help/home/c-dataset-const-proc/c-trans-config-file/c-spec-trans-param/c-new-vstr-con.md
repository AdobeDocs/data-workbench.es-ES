---
description: La condición de nuevo visitante es una operación de condición que se utiliza con los datos del sitio web para determinar qué visitantes se consideran para la inclusión en el conjunto de datos.
solution: Analytics
title: Nueva condición de visitante
topic: Data workbench
uuid: e9733109-5bf3-47ce-974c-d68264291f19
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Nueva condición de visitante{#new-visitor-condition}

La condición de nuevo visitante es una operación de condición que se utiliza con los datos del sitio web para determinar qué visitantes se consideran para la inclusión en el conjunto de datos.

La [!DNL New Visitor Condition] define la primera entrada de registro (ordenada por tiempo) para un visitante que se va a utilizar en el conjunto de datos y todas las entradas de registro subsiguientes para este visitante se incluyen en el conjunto de datos independientemente de si cumplen esta condición. Debido a que el visitante y el tiempo [!DNL New Visitor Condition] requieren que los datos se ordenen, solo se aplican durante la fase de transformación de la construcción de conjuntos de datos.

El ejemplo [!DNL New Visitor Condition] que se muestra crea un conjunto de datos que incluye solo las entradas de registro de los visitantes que responden a las campañas de correo electrónico. Esto se logra utilizando la [!DNL NotEmptyCondition] prueba (consulte [No vacío](../../../../home/c-dataset-const-proc/c-conditions/c-test-ops/c-test-op-con.md#section-1decb9d887894073a1b6b3d985729ac8)) y el [!DNL x-campaign-email] campo como entrada para la expresión regular. Una vez identificados los nuevos visitantes que cumplen la condición, se capturan todas las entradas de registro de dichos visitantes.

![](assets/cfg_Transformation_NewVisitorCondition.png)

