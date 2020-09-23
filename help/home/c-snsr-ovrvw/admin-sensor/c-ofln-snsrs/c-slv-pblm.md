---
description: Cuando un servidor web se desconecta debido a un error, la solución es sencilla y requiere un usuario de Data Workbench con los privilegios adecuados para abrir el archivo Log Processing Mode.cfg y agregar el ID del sensor (en nuestro ejemplo, WEB2) a la sección "Offline Sources".
solution: Analytics
title: Solución del problema
uuid: 19d47b06-be12-4adf-9eac-b16cf7131834
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '317'
ht-degree: 1%

---


# Solución del problema{#solving-the-problem}

Cuando un servidor web se desconecta debido a un error, la solución es sencilla y requiere un usuario de Data Workbench con los privilegios adecuados para abrir el archivo Log Processing Mode.cfg y agregar el ID del sensor (en nuestro ejemplo, WEB2) a la sección &quot;Offline Sources&quot;.

Esta sección del archivo indica [!DNL data workbench server] que ya no debe esperar ningún dato de esta fuente porque, de hecho, está sin conexión.

>[!NOTE]
>
>Este cambio no necesita ser realizado por un consultor de Adobe. Cualquier persona que tenga los privilegios adecuados para abrir el [!DNL Log Processing Mode.cfg] archivo puede realizar este cambio.

Si WEB2 comienza a enviar datos de nuevo, [!DNL data workbench server] vuelve a poner la fuente en línea y ajusta el valor Con el tiempo para reflejar la última vez que recibió datos de todas las fuentes de las que tiene conocimiento. En otras palabras, los nuevos datos que entran en el sistema tienen prioridad sobre los que se escriben en el [!DNL Log Processing Mode.cfg file].

Si WEB2 vuelve a estar sin conexión, el valor Con tiempo se detendrá de nuevo y tendrá que volver a editar el [!DNL Log Processing Mode.cfg] archivo aunque ya tenga WEB2 como origen sin conexión. Este es un artefacto del diseño del producto de acuerdo con la definición del valor Con el tiempo: la última vez que el sistema tiene datos para todas las fuentes conocidas.

Cuando agrega más servidores Web (WEB4, WEB5, WEB6) y comienzan a enviar datos al [!DNL data workbench server], no es necesario que haga nada para que el [!DNL data workbench server] reconocimiento de las nuevas fuentes. El sistema simplemente se da cuenta de que debe esperar datos de estas nuevas fuentes, como se ha descrito anteriormente.
