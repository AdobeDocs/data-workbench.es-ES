---
description: La condición de nuevo visitante es una operación de condición que se utiliza con los datos del sitio web para determinar qué visitantes se consideran para su inclusión en el conjunto de datos.
title: Condición de nuevo visitante
uuid: e9733109-5bf3-47ce-974c-d68264291f19
exl-id: a0520edd-bde3-4f55-858c-8974d4224435
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '175'
ht-degree: 3%

---

# Condición de nuevo visitante{#new-visitor-condition}

{{eol}}

La condición de nuevo visitante es una operación de condición que se utiliza con los datos del sitio web para determinar qué visitantes se consideran para su inclusión en el conjunto de datos.

La variable [!DNL New Visitor Condition] define la primera entrada de registro (ordenada por el tiempo) para un visitante que se va a usar en el conjunto de datos, y todas las entradas de registro subsiguientes para este visitante se incluyen en el conjunto de datos independientemente de si cumplen esta condición. Porque la variable [!DNL New Visitor Condition] requiere que los datos se ordenen por visitante y tiempo; se aplican solo durante la fase de transformación de la construcción del conjunto de datos.

La variable [!DNL New Visitor Condition] en este ejemplo se crea un conjunto de datos que incluye solo las entradas de registro de los visitantes que responden a las campañas de correo electrónico. Para ello, utilice la variable [!DNL NotEmptyCondition] prueba (consulte [No vacío](../../../../home/c-dataset-const-proc/c-conditions/c-test-ops/c-test-op-con.md#section-1decb9d887894073a1b6b3d985729ac8)) y [!DNL x-campaign-email] como entrada a la expresión regular. Una vez identificados los nuevos visitantes que cumplen la condición, se capturan todas las entradas de registro de esos visitantes.

![](assets/cfg_Transformation_NewVisitorCondition.png)
