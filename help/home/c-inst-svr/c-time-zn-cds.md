---
description: Dar formato a instrucciones sobre parámetros basados en tiempo en Insight Server.
title: Códigos de huso horario (Insight Server)
uuid: dcc8aa15-5846-4f24-8b82-e25ff89871ba
exl-id: d8923b01-24fe-4a70-9800-f2eedf567c6a
source-git-commit: 235b8816c7397ac1ab71df650a1d4c2d681b3b2d
workflow-type: tm+mt
source-wordcount: '365'
ht-degree: 4%

---

# Códigos de huso horario{#time-zone-codes}

Dar formato a instrucciones sobre parámetros basados en tiempo en Insight Server.

La mayoría de los parámetros basados en tiempo de [!DNL Insight Server] se especifican en el siguiente formato:

*Mes DD, AAAA HH:MM:Zona horaria SS*

Ejemplo: 13 de agosto de 2013 22:30:00 EST

Las zonas horarias se expresan en un formato de zona horaria independiente del sistema (hora universal coordinada) con el siguiente formato:

UTC +hmm *Dstrules*

El signo (+) puede ser un signo más (+) o un signo menos (-), y *hmm* es el desplazamiento con respecto a UTC en horas y minutos. La variable opcional *Dstrules* especifica un conjunto de reglas para implementar el cambio de horario de verano o una política de cambio de reloj similar.

Si especifica *Dstrules*, un archivo delimitado por tabuladores denominado *&lt; [!DNL dstrules]>* [!DNL .dst] debe estar presente en el directorio Dataset\TimeZone del perfil Base (para archivos de configuración que no están asociados a un conjunto de datos concreto) o el perfil del conjunto de datos (para archivos de configuración que son específicos del conjunto de datos). El archivo especifica un conjunto de reglas independientes de zona horaria para el horario de verano. Puede tener diferentes conjuntos de reglas para diferentes años. La variable [!DNL DST.dst] El archivo proporcionado por el Adobe en el perfil de base especifica las normas estándar de los Estados Unidos establecidas por la Ley de Política Energética de 2005 (en vigor a partir de 2007) y las normas de los Estados Unidos para años anteriores.

A continuación se enumeran las entradas de zona horaria de ejemplo:

* Hora de verano de EE. UU.: Zona horaria = cadena: UTC -0500 DST
* Tiempo UTC sin desplazamiento y sin *Dstrules* (correspondiente a GMT): Zona horaria = cadena: UTC -0000

Cuando se utiliza este formato, la zona horaria del sistema de [!DNL Insight Server], [!DNL Insight]y [!DNL Report] Los equipos no deben ser los mismos que el huso horario especificado. Además, todos los perfiles de conjuntos de datos activos en un [!DNL Insight Server] La máquina no necesita tener la misma configuración de zona horaria.

La siguiente tabla contiene la lista de códigos que puede utilizar para especificar zonas horarias en parámetros basados en tiempo.

## Tabla de código de zona horaria {#section-3cab225b864f4e54ac4f5bd83ab4ed36}

>[!NOTE]
>
>Si va a implementar Horario de verano o una política de cambio de reloj similar, debe guardar la variable [!DNL .dst] archivo que contiene las reglas adecuadas en la *nombre de perfil*\Dataset\Timezone en el directorio [!DNL Insight Server] máquina.

| Código | Zona horaria | Desplazamiento desde GMT |
|---|---|---|
| gmt | Greenwich Media | 0 |
| est | Estándar oriental | 5 |
| edt | Luz de verano oriental | 5 |
| cst | Estándar central | 6 |
| cdt | Luz de día central | 6 |
| mst | Mountain Standard | 7 |
| mdt | Horario de montaña | 7 |
| pst | Pacific Standard | 8 |
| pdt | Luz de día del Pacífico | 8 |
