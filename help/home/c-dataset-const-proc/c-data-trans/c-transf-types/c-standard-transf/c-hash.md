---
description: La transformación Hash crea una cadena casi única que representa un número de 64 bits a partir de los valores de entrada.
solution: Analytics
title: Hash
topic: Data workbench
uuid: 13bc14e6-75e2-4711-8f98-50fd18802be5
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Hash{#hash}

La transformación Hash crea una cadena casi única que representa un número de 64 bits a partir de los valores de entrada.

Esta transformación proporciona el mismo valor hash cuando se le dan las mismas entradas.

>[!NOTE]
>
>El valor resultante es casi único porque la transformación utiliza un número de 64 bits como espacio de posibles valores hash. Para un millón de entradas únicas a la [!DNL hash] transformación, hay una probabilidad de 1 en 38.000.000 de obtener un valor hash duplicado.

| Parámetro | Descripción | Valor predeterminado |
|---|---|---|
| Nombre | Nombre descriptivo de la transformación. Aquí puede introducir cualquier nombre. |  |
| Comentarios | Opcional. Notas sobre la transformación. |  |
| Condición | Condiciones en las que se aplica esta transformación. |  |
| Valor predeterminado | El valor predeterminado que se utilizará si el valor de entrada no está disponible. |  |
| Entradas | Conjunto de entradas que se va a utilizar para crear el valor hash. |  |
| Salida | Nombre del campo que se va a mostrar. |  |

En este ejemplo, los valores de los campos c-ip y cs(user-agent) se utilizan para crear un ID de seguimiento, que se almacena en el campo x-trackingid.

![](assets/cfg_TransformationType_Hash.png)

>[!NOTE]
>
>Este ejemplo no representa una solución ideal para crear ID de seguimiento únicos. Sin embargo, en situaciones en las que se utiliza la información de registro de archivos, puede ser el mejor método.

