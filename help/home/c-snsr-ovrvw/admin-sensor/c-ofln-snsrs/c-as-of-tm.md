---
description: Un servidor del área de trabajo de datos tiene conocimiento de una fuente de datos, como un sensor, cuando recibe datos de esa fuente.
solution: Analytics
title: Explicación del tiempo “Con fecha”
uuid: a1853573-e77c-41f7-8b99-2843e38cc82d
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '275'
ht-degree: 2%

---


# Explicación del tiempo “Con fecha”{#understanding-as-of-time}

Un servidor del área de trabajo de datos tiene conocimiento de una fuente de datos, como un sensor, cuando recibe datos de esa fuente.

El valor Con el tiempo es una garantía de que el usuario [!DNL data workbench server] tiene datos para todas las fuentes de datos de las que tiene conocimiento.

Supongamos que tenemos un conjunto de tres [!DNL Sensors] que envían datos a un [!DNL data workbench server]: WEB1, WEB2 y WEB3. A medida que [!DNL data workbench server] recibe y procesa los datos de estos [!DNL Sensors], automáticamente se esperan datos de cada una de estas fuentes. El valor Con respecto al tiempo indica la última vez que los datos [!DNL data workbench server] recibidos de estas tres fuentes.

En términos prácticos, a la [!DNL data workbench server] única le importa el Tiempo y no lo que podría llamarse &quot;tiempo de pared&quot;, o la hora de un reloj en la pared. El [!DNL data workbench server] conoce el tiempo sólo como el A del tiempo. Esto es especialmente importante a efectos de sistema de informes, ya que garantiza que los informes siempre se ejecuten en función del valor Con el tiempo, lo que garantiza que los informes con datos parciales no se puedan enviar nunca a los usuarios finales del sistema.

El [!DNL data workbench server] utiliza los datos que se envían desde el transmisor para proporcionar el valor Con el tiempo, ya sean datos reales recopilados desde el sitio web o latidos periódicos enviados por su [!DNL Sensors]. Estos latidos tienen dos propósitos:

1. Para mantener abierta una conexión persistente HTTP/1.1 entre el [!DNL Sensor] y el [!DNL data workbench server].

1. Para mantener el valor Con el tiempo actualizado en el evento de que el tráfico del sitio web no se está recopilando y enviando al [!DNL data workbench server].

