---
description: Los parámetros vectoriales contienen varios valores para una sola variable.
title: Parámetros vectoriales
uuid: 2ca83502-acc4-4b94-b0e4-a48a596e7623
exl-id: c6140bdf-dcd9-4fa9-a6e0-34cbc45414d0
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '89'
ht-degree: 4%

---

# Parámetros vectoriales{#vector-parameters}

Los parámetros vectoriales contienen varios valores para una sola variable.

Solo se puede hacer referencia a los parámetros vectoriales como el único elemento de un vector. Este ejemplo muestra un archivo [!DNL Transformation Dataset Include] que define un parámetro vectorial. El parámetro vectorial &quot;Dominios internos&quot; consta de tres valores.

![](assets/cfg_WebParameters_InternalDomains.png)

Tenga en cuenta que el parámetro vectorial es el único elemento enumerado para el vector [!DNL Matches] en la condición [!DNL String Match].

![](assets/cfg_Parameters_InternalDomains_Ref.png)

Para obtener más información sobre los dominios internos, consulte [Configuración de datos web](../../../../home/c-dataset-const-proc/c-config-web-data/c-config-web-data.md#concept-9a306b65483a484bb3f6f3c1d7e77519). Para obtener información sobre la condición [!DNL String Match], consulte [Condiciones](../../../../home/c-dataset-const-proc/c-conditions/c-abt-cond.md).
