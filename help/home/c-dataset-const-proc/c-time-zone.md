---
description: Información sobre los códigos y formatos del huso horario.
solution: Analytics
title: Códigos de huso horario
topic: Data workbench
uuid: 5698882a-9682-41d8-88d3-8471578a22cc
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Códigos de huso horario{#time-zone-codes}

Información sobre los códigos y formatos del huso horario.

La mayoría de los parámetros basados en el tiempo del servidor del área de trabajo de datos se especifican con el siguiente formato:

* Mes DD, AAAA HH :MM :SS TZone
* Ejemplo: 13 de agosto de 2013, 22:30:00 EST

Los husos horarios se expresan en un formato de zona horaria independiente del sistema (hora universal coordinada) con el siguiente formato:

* Rótulos UTC +hhmm

El signo (+) puede ser un signo más (+) o un signo menos (-), y hhmm es el desplazamiento de UTC en horas y minutos. Las instrucciones de variable opcionales especifican un conjunto de reglas para implementar el horario de verano o una política de cambio de reloj similar.

Si especifica las estructuras, un archivo delimitado por tabuladores denominado [!DNL dstrules.dst] debe estar presente en el directorio Dataset\TimeZone del [!DNL Base] perfil (para los archivos de configuración que no están asociados a un conjunto de datos concreto) o del perfil del conjunto de datos (para los archivos de configuración que son específicos de un conjunto de datos). El archivo especifica un conjunto de reglas independiente de zona horaria para el horario de verano. Puede tener diferentes conjuntos de reglas para diferentes años. El [!DNL DST.dst] archivo proporcionado por Adobe en el [!DNL Base] perfil especifica las reglas estándar de EE.UU. establecidas por la Ley de Política Energética de 2005 (en vigor a partir de 2007) y las normas de EE.UU. para años anteriores.

A continuación se muestran las entradas de zona horaria de muestra:

* Hora del verano del este de EE.UU.: Zona horaria = cadena: UTC -0500 DST
* Hora UTC sin desplazamiento y sin ejes (correspondiente a GMT): Zona horaria = cadena: UTC -0000

Cuando se utiliza este formato, la zona horaria del sistema del servidor del área de trabajo de datos, del área de trabajo de datos y de los equipos de informes no debe ser la misma que la zona horaria especificada. Además, todos los perfiles de conjuntos de datos activos de un equipo de servidor del área de trabajo de datos no necesitan tener la misma configuración de zona horaria.

La siguiente tabla contiene la lista de códigos que puede utilizar para especificar zonas horarias en parámetros basados en tiempo.

## Tabla de códigos de zona horaria {#section-b4f965b872c543e2ac52a3c94410d076}

Si va a implementar el horario de verano o una política de cambio de reloj similar, debe guardar el [!DNL .dst] archivo que contiene las reglas correspondientes en el directorio del nombre del perfil [!DNL \Dataset\Timezone] del equipo del servidor del área de trabajo de datos.

| Código | Zona horaria | Desplazamiento desde GMT |
|---|---|---|
| gmt | Medio de Greenwich | 0 |
| est | Estándar oriental | 5 |
| edt | Luz de verano oriental | 5 |
| cst | Central Standard | 6 |
| cdt | Luz diurna central | 6 |
| mst | Mountain Standard | 7 |
| mdt | Luz diurna de montaña | 7 |
| pst | Norma del Pacífico | 8 |
| pdt | Luz de día del Pacífico | 8 |

