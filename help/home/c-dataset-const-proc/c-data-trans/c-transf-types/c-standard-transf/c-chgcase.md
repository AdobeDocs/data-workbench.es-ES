---
description: La transformación ChangeCase cambia las mayúsculas y minúsculas de la cadena en el parámetro Input tal como se especifica en el parámetro Action .
title: ChangeCase
uuid: 676e79e6-324e-43d1-8982-b44596d0eeac
exl-id: 2002fe22-d31c-4286-9f73-59ef205f1384
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '145'
ht-degree: 8%

---

# ChangeCase{#changecase}

{{eol}}

La transformación ChangeCase cambia las mayúsculas y minúsculas de la cadena en el parámetro Input tal como se especifica en el parámetro Action .

| Parámetro | Descripción | Predeterminado |
|---|---|---|
| Nombre | Nombre descriptivo de la transformación. Puede introducir cualquier nombre aquí. |  |
| Acción | Superior o inferior. Especifica si se va a cambiar el caso a superior o inferior. | lower |
| Comentarios | Opcional. Notas sobre la transformación. |  |
| Condición | Condiciones en las que se aplica esta transformación. |  |
| Entrada | Nombre del campo de la entrada de registro que se utilizará como entrada. |  |
| Output | Nombre del campo de salida. |  |

En este ejemplo, que utiliza campos de datos recopilados del tráfico del sitio web, se cambia el caso de la cadena dentro del campo s-dns a minúsculas y el nuevo valor se genera en el nuevo campo, x-lowercase-dns.

![](assets/cfg_TransformationType_ChangeCase.png)
