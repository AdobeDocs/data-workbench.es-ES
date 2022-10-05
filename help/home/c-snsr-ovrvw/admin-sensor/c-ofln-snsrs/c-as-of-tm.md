---
description: Un servidor de Data Workbench es consciente de una fuente de datos, como un sensor, cuando recibe datos de esa fuente.
title: Explicación del tiempo “Con fecha”
uuid: a1853573-e77c-41f7-8b99-2843e38cc82d
exl-id: 58ea5c6f-de6b-48d2-b573-f265857026da
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '275'
ht-degree: 2%

---

# Explicación del tiempo “Con fecha”{#understanding-as-of-time}

{{eol}}

Un servidor de Data Workbench es consciente de una fuente de datos, como un sensor, cuando recibe datos de esa fuente.

El valor Con el tiempo es una garantía de que la variable [!DNL data workbench server] tiene datos para todas las fuentes de datos de las que tiene conocimiento.

Digamos que tenemos un conjunto de tres [!DNL Sensors] que envían datos a un [!DNL data workbench server]: WEB1, WEB2 y WEB3. Como [!DNL data workbench server] recibe y procesa los datos de estos [!DNL Sensors], se espera automáticamente datos de cada una de estas fuentes. El valor Con respecto al tiempo indica la última vez que el valor [!DNL data workbench server] recibió datos de las tres fuentes.

En términos prácticos, la variable [!DNL data workbench server] solo se preocupa por el valor de Con tiempo y no por lo que podría llamarse &quot;tiempo de pared&quot;, o la hora de un reloj en la pared. La variable [!DNL data workbench server] solo conoce la hora como el valor Con tiempo. Esto es especialmente importante a efectos de los informes, ya que garantiza que los informes siempre se ejecuten en función del valor Con fecha, lo que garantiza que los informes que solo tengan datos parciales no se puedan enviar nunca a los usuarios finales del sistema.

La variable [!DNL data workbench server] utiliza los datos que se envían desde el transmisor para proporcionar el valor Con fecha, ya sean datos reales recopilados del sitio web o latidos periódicos enviados por su [!DNL Sensors]. Estos latidos tienen dos propósitos:

1. Para mantener una conexión persistente HTTP/1.1 abierta entre las variables [!DNL Sensor] y [!DNL data workbench server].

1. Para mantener actualizado el valor Con respecto al tiempo en caso de que el tráfico del sitio web no se recopile y se envíe al [!DNL data workbench server].
