---
description: Cuando un servidor web se desconecta debido a un error, la solución es sencilla y requiere un usuario de Data Workbench con los privilegios adecuados para abrir el archivo Log Processing Mode.cfg y añadir el ID del sensor (en nuestro ejemplo, WEB2) a la sección "Fuentes sin conexión".
title: Solución del problema
uuid: 19d47b06-be12-4adf-9eac-b16cf7131834
exl-id: 4a05dc06-360b-4c15-a881-81d350e95372
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '317'
ht-degree: 1%

---

# Solución del problema{#solving-the-problem}

{{eol}}

Cuando un servidor web se desconecta debido a un error, la solución es sencilla y requiere un usuario de Data Workbench con los privilegios adecuados para abrir el archivo Log Processing Mode.cfg y añadir el ID del sensor (en nuestro ejemplo, WEB2) a la sección &quot;Fuentes sin conexión&quot;.

Esta sección del archivo indica a la variable [!DNL data workbench server] que ya no debería esperar ningún dato de esta fuente porque, de hecho, está sin conexión.

>[!NOTE]
>
>Este cambio no necesita ser realizado por un consultor de Adobe. Cualquier persona que tenga los privilegios adecuados para abrir el [!DNL Log Processing Mode.cfg] puede realizar este cambio.

Si WEB2 comienza a enviar datos de nuevo, la variable [!DNL data workbench server] vuelve a poner la fuente en línea y ajusta el valor Con fecha para reflejar la última vez que recibió datos de todas las fuentes de las que tiene conocimiento. En otras palabras, los nuevos datos que llegan al sistema tienen prioridad sobre los que se escriben en la variable [!DNL Log Processing Mode.cfg file].

Si WEB2 vuelve a estar sin conexión, el valor Con fecha se detendrá de nuevo y tendrá que editar la variable [!DNL Log Processing Mode.cfg] a pesar de que ya podría tener WEB2 como fuente sin conexión. Este es un artefacto del diseño del producto de acuerdo con la definición del Con del tiempo: la última vez que el sistema tiene datos para todas las fuentes conocidas.

Cuando agrega más servidores web (WEB4, WEB5, WEB6), y empiezan a enviar datos al [!DNL data workbench server], no es necesario que haga nada para que el [!DNL data workbench server] reconozca las nuevas fuentes. El sistema simplemente es consciente de que debería esperar datos de estas nuevas fuentes, como se ha descrito anteriormente.
