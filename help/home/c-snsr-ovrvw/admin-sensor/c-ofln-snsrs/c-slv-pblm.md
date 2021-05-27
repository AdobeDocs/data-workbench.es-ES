---
description: Cuando un servidor web se desconecta debido a un error, la solución es sencilla y requiere un usuario de Data Workbench con los privilegios adecuados para abrir el archivo Log Processing Mode.cfg y añadir el ID del sensor (en nuestro ejemplo, WEB2) a la sección "Fuentes sin conexión".
title: Solución del problema
uuid: 19d47b06-be12-4adf-9eac-b16cf7131834
exl-id: 4a05dc06-360b-4c15-a881-81d350e95372
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '317'
ht-degree: 1%

---

# Solución del problema{#solving-the-problem}

Cuando un servidor web se desconecta debido a un error, la solución es sencilla y requiere un usuario de Data Workbench con los privilegios adecuados para abrir el archivo Log Processing Mode.cfg y añadir el ID del sensor (en nuestro ejemplo, WEB2) a la sección &quot;Fuentes sin conexión&quot;.

Esta sección del archivo indica a [!DNL data workbench server] que ya no debería esperar ningún dato de este origen porque, de hecho, está sin conexión.

>[!NOTE]
>
>Este cambio no necesita ser realizado por un consultor de Adobe. Cualquier persona que tenga los privilegios adecuados para abrir el archivo [!DNL Log Processing Mode.cfg] puede realizar este cambio.

Si WEB2 comienza a enviar datos de nuevo, el [!DNL data workbench server] vuelve a poner la fuente en línea y ajusta el valor Con fecha para reflejar la última vez que recibió datos de todas las fuentes de las que tiene conocimiento. En otras palabras, los nuevos datos que llegan al sistema tienen prioridad sobre lo que se escribe en [!DNL Log Processing Mode.cfg file].

Si WEB2 vuelve a estar sin conexión, el valor Con fecha se detendrá de nuevo y tendrá que volver a editar el archivo [!DNL Log Processing Mode.cfg] aunque ya esté incluido WEB2 como origen sin conexión. Este es un artefacto del diseño del producto de acuerdo con la definición del Con del tiempo: la última vez que el sistema tiene datos para todas las fuentes conocidas.

Cuando agrega más servidores web (WEB4, WEB5, WEB6) y comienzan a enviar datos a [!DNL data workbench server], no es necesario que haga nada para que [!DNL data workbench server] reconozca los nuevos orígenes. El sistema simplemente es consciente de que debería esperar datos de estas nuevas fuentes, como se ha descrito anteriormente.
