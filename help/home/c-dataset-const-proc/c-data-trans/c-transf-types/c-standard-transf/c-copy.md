---
description: La transformación Copiar simplemente copia el valor del campo de entrada en el campo de salida dado. Si el campo de entrada puede ser un vector de cadenas, el campo de salida debe comenzar por "x-".
title: Copiar
uuid: 073f53bf-befb-4fba-a8f8-260ffcdd007c
exl-id: 04e97006-1e8e-4123-bbbc-b90a5231170f
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '176'
ht-degree: 6%

---

# Copiar{#copy}

La transformación Copiar simplemente copia el valor del campo de entrada en el campo de salida dado. Si el campo de entrada puede ser un vector de cadenas, el campo de salida debe comenzar por &quot;x-&quot;.

| Parámetro | Descripción | Predeterminado |
|---|---|---|
| Nombre | Nombre descriptivo de la transformación. Puede introducir cualquier nombre aquí. |  |
| Comentarios | Opcional. Notas sobre la transformación. |  |
| Condición | Condiciones en las que se aplica esta transformación. |  |
| Predeterminado | Se utiliza si la prueba de la condición es verdadera y el valor de entrada no está disponible en la entrada de registro determinada. |  |
| Entrada | Nombre del campo desde el que se va a copiar. |  |
| Salida | Nombre del campo de salida. |  |

En este ejemplo, que utiliza campos de datos recopilados del tráfico del sitio web, el campo de salida, x-purchase-success, recibe el valor literal de &quot;1&quot; cada vez que cs-uri-stem coincide con [!DNL /checkout/confirmed.php]. Si [!DNL Condition] no está satisfecho (es decir, cs-uri-stem no coincide con [!DNL /checkout/confirmed.php]), x-purchase-success no cambia.

![](assets/cfg_TransformationType_Copy.png)
