---
description: La transformación Unión toma un conjunto de entradas y crea un vector de cadenas como salida.
title: Union
uuid: 2f8bd332-727e-4a4e-a3e7-a52ea2b0a33a
exl-id: 841b5133-d587-409c-b39e-47169beb2ddf
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '262'
ht-degree: 4%

---

# Unión{#union}

{{eol}}

La transformación Unión toma un conjunto de entradas y crea un vector de cadenas como salida.

Si una de las entradas es en sí misma un vector, cada elemento del vector de entrada se asocia con un elemento del vector de salida (es decir, la transformación no crea un vector de vectores).

| Parámetro | Descripción | Predeterminado |
|---|---|---|
| Nombre | Nombre descriptivo de la transformación. Puede introducir cualquier nombre aquí. |  |
| Comentarios | Opcional. Notas sobre la transformación. |  |
| Condición | Condiciones en las que se aplica esta transformación. |  |
| Predeterminado | El valor predeterminado que se debe utilizar si se cumple la condición y el valor de entrada no está disponible. |  |
| Entradas | Uno o más valores de entrada. |  |
| Output | Nombre del campo de salida. |  |

Este ejemplo utiliza campos de datos del tráfico del sitio web para crear una lista de los códigos postales asociados con los visitantes del sitio web (es decir, dentro de cada entrada de registro). Los datos proporcionan dos fuentes posibles para esta información: uno en cs-uri-query y el otro en un [!DNL zipcode] del campo de la cookie. Si ninguno de estos campos contiene código postal, se utiliza el valor predeterminado 00000.

![](assets/cfg_TransformationType_Union.png)

Aunque es posible que ambos valores estén disponibles en una sola entrada de registro, se puede seleccionar qué valor utilizar al crear una dimensión en función de la salida de la transformación. En un caso de uso típico, se crearía una dimensión simple que tomaría la primera o la última de los valores encontrados. Para obtener información sobre la creación de dimensiones simples, consulte [Dimension extendidos](../../../../../home/c-dataset-const-proc/c-ex-dim/c-abt-ex-dim.md).
