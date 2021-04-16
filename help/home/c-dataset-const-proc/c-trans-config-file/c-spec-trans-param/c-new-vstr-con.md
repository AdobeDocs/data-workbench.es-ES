---
description: La condición de nuevo visitante es una operación de condición que se utiliza con los datos del sitio web para determinar qué visitantes se consideran para su inclusión en el conjunto de datos.
title: Condición de nuevo visitante
uuid: e9733109-5bf3-47ce-974c-d68264291f19
exl-id: a0520edd-bde3-4f55-858c-8974d4224435
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '175'
ht-degree: 3%

---

# Condición de nuevo visitante{#new-visitor-condition}

La condición de nuevo visitante es una operación de condición que se utiliza con los datos del sitio web para determinar qué visitantes se consideran para su inclusión en el conjunto de datos.

El [!DNL New Visitor Condition] define la primera entrada de registro (ordenada por el tiempo) para un visitante que se va a usar en el conjunto de datos, y todas las entradas de registro subsiguientes para este visitante se incluyen en el conjunto de datos independientemente de si cumplen esta condición. Dado que [!DNL New Visitor Condition] requiere que los datos se ordenen por visitante y tiempo, solo se aplican durante la fase de transformación de la construcción del conjunto de datos.

El [!DNL New Visitor Condition] mostrado en este ejemplo crea un conjunto de datos que incluye solo las entradas de registro de los visitantes que responden a las campañas de correo electrónico. Para ello, utilice la prueba [!DNL NotEmptyCondition] (consulte [No está vacío](../../../../home/c-dataset-const-proc/c-conditions/c-test-ops/c-test-op-con.md#section-1decb9d887894073a1b6b3d985729ac8)) y el campo [!DNL x-campaign-email] como entrada para la expresión regular. Una vez identificados los nuevos visitantes que cumplen la condición, se capturan todas las entradas de registro de esos visitantes.

![](assets/cfg_Transformation_NewVisitorCondition.png)
