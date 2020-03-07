---
description: La transformación de la Unión toma un conjunto de entradas y crea un vector de cadenas como salida.
solution: Analytics
title: Unión
topic: Data workbench
uuid: 2f8bd332-727e-4a4e-a3e7-a52ea2b0a33a
translation-type: tm+mt
source-git-commit: 27600561841db3705f4eee6ff0aeb8890444bbc9

---


# Unión{#union}

La transformación de la Unión toma un conjunto de entradas y crea un vector de cadenas como salida.

Si una de las entradas es en sí misma un vector, cada elemento del vector de entrada se asocia con un elemento del vector de salida (es decir, la transformación no crea un vector de vectores).

| Parámetro | Descripción | Valor predeterminado |
|---|---|---|
| Nombre | Nombre descriptivo de la transformación. Aquí puede introducir cualquier nombre. |  |
| Comentarios | Opcional. Notas sobre la transformación. |  |
| Condición | Condiciones en las que se aplica esta transformación. |  |
| Valor predeterminado | El valor predeterminado que se usará si se cumple la condición y el valor de entrada no está disponible. |  |
| Entradas | Uno o más valores de entrada. |  |
| Salida | Nombre del campo de salida. |  |

Este ejemplo utiliza campos de datos del tráfico del sitio web para crear una lista de los códigos postales asociados con los visitantes del sitio web (es decir, dentro de cada entrada de registro). Los datos proporcionan dos fuentes posibles para esta información: uno en cs-uri-query y el otro en un [!DNL zipcode] campo de la cookie. Si ninguno de estos campos contiene un código postal, se utiliza el valor predeterminado 00000.

![](assets/cfg_TransformationType_Union.png)

Aunque es posible que ambos valores estén disponibles en una única entrada de registro, puede seleccionar qué valor utilizar al crear una dimensión en función del resultado de la transformación. En un caso de uso habitual, se crearía una dimensión simple que tomaría el primero o el último de los valores encontrados. Para obtener información sobre la creación de dimensiones simples, consulte Dimensiones [extendidas](../../../../../home/c-dataset-const-proc/c-ex-dim/c-abt-ex-dim.md).
