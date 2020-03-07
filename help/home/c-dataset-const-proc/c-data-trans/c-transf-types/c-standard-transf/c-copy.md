---
description: La transformación Copiar simplemente copia el valor del campo de entrada en el campo de salida dado. Si el campo de entrada puede ser un vector de cadenas, el campo de salida debe comenzar con "x-".
solution: Analytics
title: Copiar
topic: Data workbench
uuid: 073f53bf-befb-4fba-a8f8-260ffcdd007c
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Copiar{#copy}

La transformación Copiar simplemente copia el valor del campo de entrada en el campo de salida dado. Si el campo de entrada puede ser un vector de cadenas, el campo de salida debe comenzar con &quot;x-&quot;.

| Parámetro | Descripción | Valor predeterminado |
|---|---|---|
| Nombre | Nombre descriptivo de la transformación. Aquí puede introducir cualquier nombre. |  |
| Comentarios | Opcional. Notas sobre la transformación. |  |
| Condición | Condiciones en las que se aplica esta transformación. |  |
| Valor predeterminado | Se utiliza si la prueba de condición es verdadera y el valor de entrada no está disponible en la entrada de registro dada. |  |
| Entrada | Nombre del campo desde el que se va a copiar. |  |
| Salida | Nombre del campo de salida. |  |

En este ejemplo, que utiliza campos de datos recopilados del tráfico del sitio web, al campo de salida, x-purchase-success, se le asigna el valor literal de &quot;1&quot; cada vez que cs-uri-stem coincide [!DNL /checkout/confirmed.php]. Si no [!DNL Condition] está satisfecho (es decir, cs-uri-stem no coincide [!DNL /checkout/confirmed.php]), el éxito de x-purchase no se modifica.

![](assets/cfg_TransformationType_Copy.png)

