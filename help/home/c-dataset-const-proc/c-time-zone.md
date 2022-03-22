---
description: Información sobre los códigos y formatos de zona horaria.
title: Códigos y formatos de zona horaria
uuid: 5698882a-9682-41d8-88d3-8471578a22cc
exl-id: 2829c4ca-af6f-4ddb-acce-b33c3b552ba7
source-git-commit: 235b8816c7397ac1ab71df650a1d4c2d681b3b2d
workflow-type: tm+mt
source-wordcount: '378'
ht-degree: 4%

---

# Códigos de huso horario{#time-zone-codes}

Información sobre los códigos y formatos de zona horaria.

La mayoría de los parámetros basados en tiempo del servidor de Data Workbench se especifican con el siguiente formato:

* Mes DD , AAAA HH :MM :SS TZone
* Ejemplo: 13 de agosto de 2013 22:30:00 EST

Las zonas horarias se expresan en un formato de zona horaria independiente del sistema (hora universal coordinada) con el siguiente formato:

* Instrucciones UTC +hmm

El signo (+) puede ser un signo más (+) o un signo menos (-), y hmm es el desplazamiento desde UTC en horas y minutos. La variable opcional estructura especifica un conjunto de reglas para implementar el cambio de horario de verano o una política de cambio de reloj similar.

Si especifica celdas, un archivo delimitado por tabuladores denominado [!DNL dstrules.dst] debe estar presente en el directorio Dataset\TimeZone de [!DNL Base] perfil (para archivos de configuración que no están asociados a un conjunto de datos determinado) o el perfil del conjunto de datos (para archivos de configuración que son específicos del conjunto de datos). El archivo especifica un conjunto de reglas independientes de zona horaria para el horario de verano. Puede tener diferentes conjuntos de reglas para diferentes años. La variable [!DNL DST.dst] archivo proporcionado por el Adobe en la variable [!DNL Base] especifica las normas estándar de los Estados Unidos establecidas por la Ley de Política Energética de 2005 (en vigor a partir de 2007) y las normas de los Estados Unidos para años anteriores.

A continuación se enumeran las entradas de zona horaria de ejemplo:

* Hora de verano de EE. UU.: Zona horaria = cadena: UTC -0500 DST
* Hora UTC sin desplazamiento y sin dificultades (correspondiente a GMT): Zona horaria = cadena: UTC -0000

Cuando se utiliza este formato, la zona horaria del sistema del servidor de Data Workbench, Data Workbench y los equipos de informes no tiene que ser la misma que la zona horaria especificada. Además, todos los perfiles de conjuntos de datos activos en un equipo de servidor de Data Workbench no necesitan tener la misma configuración de zona horaria.

La siguiente tabla contiene la lista de códigos que puede utilizar para especificar zonas horarias en parámetros basados en tiempo.

## Tabla de código de zona horaria {#section-b4f965b872c543e2ac52a3c94410d076}

Si va a implementar Horario de verano o una política de cambio de reloj similar, debe guardar la variable [!DNL .dst] archivo que contiene las reglas adecuadas en el nombre del perfil [!DNL \Dataset\Timezone] en el equipo de servidor de Data Workbench.

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
