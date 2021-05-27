---
description: Un servidor de Data Workbench es consciente de una fuente de datos, como un sensor, cuando recibe datos de esa fuente.
title: Explicación del tiempo “Con fecha”
uuid: a1853573-e77c-41f7-8b99-2843e38cc82d
exl-id: 58ea5c6f-de6b-48d2-b573-f265857026da
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '275'
ht-degree: 2%

---

# Explicación del tiempo “Con fecha”{#understanding-as-of-time}

Un servidor de Data Workbench es consciente de una fuente de datos, como un sensor, cuando recibe datos de esa fuente.

Con el tiempo es una garantía de que el [!DNL data workbench server] tiene datos para todas las fuentes de datos de las que tiene conocimiento.

Digamos que tenemos un conjunto de tres [!DNL Sensors] que envían datos a un [!DNL data workbench server]: WEB1, WEB2 y WEB3. A medida que [!DNL data workbench server] recibe y procesa los datos de estos [!DNL Sensors], automáticamente esperan datos de cada una de estas fuentes. El valor Con fecha indica la última vez que el [!DNL data workbench server] recibió datos de las tres fuentes anteriores.

En términos prácticos, el [!DNL data workbench server] solo se preocupa por el valor Con el tiempo y no por lo que podría llamarse &quot;tiempo de pared&quot;, o la hora desde un reloj en la pared. El [!DNL data workbench server] solo conoce la hora como el valor Con fecha. Esto es especialmente importante a efectos de los informes, ya que garantiza que los informes siempre se ejecuten en función del valor Con fecha, lo que garantiza que los informes que solo tengan datos parciales no se puedan enviar nunca a los usuarios finales del sistema.

El [!DNL data workbench server] utiliza los datos que se envían desde el transmisor para proporcionar el valor Con fecha, ya sean datos reales recopilados del sitio web o latidos periódicos enviados por su [!DNL Sensors]. Estos latidos tienen dos propósitos:

1. Para mantener abierta una conexión persistente HTTP/1.1 entre [!DNL Sensor] y [!DNL data workbench server].

1. Para mantener actualizado el valor Con respecto al tiempo en el caso de que el tráfico del sitio web no se esté recopilando y enviando al [!DNL data workbench server].
