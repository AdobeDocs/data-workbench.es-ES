---
description: La transformación ChangeCase cambia las mayúsculas y minúsculas de la cadena en el parámetro Input, tal como se especifica en el parámetro Action.
solution: Analytics
title: ChangeCase
topic: Data workbench
uuid: 676e79e6-324e-43d1-8982-b44596d0eeac
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# ChangeCase{#changecase}

La transformación ChangeCase cambia las mayúsculas y minúsculas de la cadena en el parámetro Input, tal como se especifica en el parámetro Action.

| Parámetro | Descripción | Valor predeterminado |
|---|---|---|
| Nombre | Nombre descriptivo de la transformación. Aquí puede introducir cualquier nombre. |  |
| Acción | Superior o inferior. Especifica si el caso se va a cambiar a superior o inferior. | lower |
| Comentarios | Opcional. Notas sobre la transformación. |  |
| Condición | Condiciones en las que se aplica esta transformación. |  |
| Entrada | Nombre del campo de la entrada de registro que se va a utilizar como entrada. |  |
| Salida | Nombre del campo de salida. |  |

En este ejemplo, que utiliza campos de datos recopilados del tráfico del sitio web, el caso de la cadena dentro del campo s-dns se cambia a letra minúscula y el nuevo valor se muestra en el nuevo campo, x-lowercase-dns.

![](assets/cfg_TransformationType_ChangeCase.png)

