---
description: Un servidor del área de trabajo de datos tiene conocimiento de una fuente de datos, como un sensor, cuando recibe datos de esa fuente.
solution: Insight
title: Explicación del tiempo "Con fecha"
uuid: a1853573-e77c-41f7-8b99-2843e38cc82d
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Explicación del tiempo &quot;Con fecha&quot;{#understanding-as-of-time}

Un servidor del área de trabajo de datos tiene conocimiento de una fuente de datos, como un sensor, cuando recibe datos de esa fuente.

El valor Con el tiempo es una garantía de que el usuario [!DNL data workbench server] tiene datos para todas las fuentes de datos de las que tiene conocimiento.

Supongamos que tenemos un conjunto de tres [!DNL Sensors] que envían datos a un [!DNL data workbench server]: WEB1, WEB2 y WEB3. A medida que [!DNL data workbench server] recibe y procesa los datos de estos [!DNL Sensors], automáticamente se esperan datos de cada una de estas fuentes. El valor Con respecto al tiempo indica la última vez que los datos [!DNL data workbench server] recibidos de estas tres fuentes.

En términos prácticos, a la [!DNL data workbench server] única le importa el Tiempo y no lo que podría llamarse &quot;tiempo de pared&quot;, o la hora de un reloj en la pared. El [!DNL data workbench server] conoce el tiempo sólo como el A del tiempo. Esto es especialmente importante para los informes, ya que garantiza que los informes siempre se ejecuten en función del valor Con el tiempo, lo que garantiza que los informes con datos parciales no se puedan enviar nunca a los usuarios finales del sistema.

El [!DNL data workbench server] utiliza los datos que se envían desde el transmisor para proporcionar el valor Con el tiempo, ya sean datos reales recopilados desde el sitio web o latidos periódicos enviados por su [!DNL Sensors]. Estos latidos tienen dos propósitos:

1. Para mantener abierta una conexión persistente HTTP/1.1 entre el [!DNL Sensor] y el [!DNL data workbench server].

1. Mantener actualizado el valor Con respecto al tiempo en caso de que el tráfico del sitio web no se recopile y se envíe al [!DNL data workbench server].

