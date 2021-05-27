---
description: Dar formato a instrucciones sobre parámetros basados en tiempo en Insight Server.
title: Códigos de huso horario
uuid: dcc8aa15-5846-4f24-8b82-e25ff89871ba
exl-id: d8923b01-24fe-4a70-9800-f2eedf567c6a
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '364'
ht-degree: 5%

---

# Códigos de huso horario{#time-zone-codes}

Dar formato a instrucciones sobre parámetros basados en tiempo en Insight Server.

La mayoría de los parámetros basados en tiempo en [!DNL Insight Server] se especifican en el siguiente formato:

*Mes DD, AAAA HH:MM:SS Zona horaria*

Ejemplo: 13 de agosto de 2013 22:30:00 EST

Las zonas horarias se expresan en un formato de zona horaria independiente del sistema (hora universal coordinada) con el siguiente formato:

UTC +hmm *discos*

El signo (+) puede ser un signo más (+) o un signo menos (-), y *hmm* es el desplazamiento con respecto a UTC en horas y minutos. La variable opcional *dstrules* especifica un conjunto de reglas para implementar el cambio de horario de verano o una política similar de cambio de reloj.

Si especifica *dstrules*, un archivo delimitado por tabuladores denominado *&lt; [!DNL dstrules]>* [!DNL .dst] debe estar presente en el directorio Dataset\TimeZone del perfil Base (para archivos de configuración que no están asociados a un conjunto de datos determinado) o el perfil del conjunto de datos (para archivos de configuración que son específicos del conjunto de datos). El archivo especifica un conjunto de reglas independientes de zona horaria para el horario de verano. Puede tener diferentes conjuntos de reglas para diferentes años. El archivo [!DNL DST.dst] proporcionado por el Adobe en el perfil Base especifica las reglas estándar de Estados Unidos establecidas por la Ley de Política Energética de 2005 (en vigor a partir de 2007) y las reglas de Estados Unidos para años anteriores.

A continuación se enumeran las entradas de zona horaria de ejemplo:

* Hora de verano de EE. UU.: Zona horaria = cadena: UTC -0500 DST
* Hora UTC sin desplazamiento y sin *discos* (correspondiente a GMT): Zona horaria = cadena: UTC -0000

Cuando se utiliza este formato, la zona horaria del sistema de las máquinas [!DNL Insight Server], [!DNL Insight] y [!DNL Report] no tiene que ser la misma que la zona horaria especificada. Además, todos los perfiles de conjuntos de datos activos en un equipo [!DNL Insight Server] no necesitan tener la misma configuración de zona horaria.

La siguiente tabla contiene la lista de códigos que puede utilizar para especificar zonas horarias en parámetros basados en tiempo.

## Tabla de código de zona horaria {#section-3cab225b864f4e54ac4f5bd83ab4ed36}

>[!NOTE]
>
>Si va a implementar Daylight Saving Time o una política similar de cambio de reloj, debe guardar el archivo [!DNL .dst] que contiene las reglas adecuadas en el equipo *nombre de perfil*\Dataset\Timezone directory on the [!DNL Insight Server].

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
