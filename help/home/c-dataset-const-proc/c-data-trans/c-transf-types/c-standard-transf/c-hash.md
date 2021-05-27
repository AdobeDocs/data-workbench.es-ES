---
description: La transformación Hash crea una cadena casi única que representa un número de 64 bits a partir de los valores de entrada.
title: Hash
uuid: 13bc14e6-75e2-4711-8f98-50fd18802be5
exl-id: 6912a1d2-9ae8-42ba-94bd-a7a28cbdfae6
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '203'
ht-degree: 4%

---

# Hash{#hash}

La transformación Hash crea una cadena casi única que representa un número de 64 bits a partir de los valores de entrada.

Esta transformación proporciona el mismo valor hash cuando se proporcionan las mismas entradas.

>[!NOTE]
>
>El valor resultante es casi único porque la transformación utiliza un número de 64 bits como el espacio de posibles valores hash. Para un millón de entradas únicas para la transformación [!DNL hash], hay una probabilidad de 1 en 38.000.000 de obtener un valor hash duplicado.

| Parámetro | Descripción | Predeterminado |
|---|---|---|
| Nombre | Nombre descriptivo de la transformación. Puede introducir cualquier nombre aquí. |  |
| Comentarios | Opcional. Notas sobre la transformación. |  |
| Condición | Condiciones en las que se aplica esta transformación. |  |
| Predeterminado | El valor predeterminado que se debe utilizar si el valor de entrada no está disponible. |  |
| Entradas | Conjunto de entradas para crear el valor hash. |  |
| Salida | Nombre del campo de salida. |  |

En este ejemplo, los valores de los campos c-ip y cs(user-agent) se utilizan para crear un ID de seguimiento, que se almacena en el campo x-trackingid .

![](assets/cfg_TransformationType_Hash.png)

>[!NOTE]
>
>Este ejemplo no representa una solución ideal para crear ID de seguimiento únicos. Sin embargo, en situaciones en las que se utiliza la información de registro de archivo, puede ser el mejor método.
