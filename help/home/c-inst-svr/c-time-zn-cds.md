---
description: Dar formato a instrucciones sobre parámetros basados en tiempo en Insight Server.
solution: Insight
title: Códigos de huso horario
uuid: dcc8aa15-5846-4f24-8b82-e25ff89871ba
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Códigos de huso horario{#time-zone-codes}

Dar formato a instrucciones sobre parámetros basados en tiempo en Insight Server.

La mayoría de los parámetros basados en el tiempo en [!DNL Insight Server] se especifican con el siguiente formato:

*Mes DD, AAAA HH:MM:SS Huso horario*

Ejemplo: 13 de agosto de 2013, 22:30:00 EST

Los husos horarios se expresan en un formato de zona horaria independiente del sistema (hora universal coordinada) con el siguiente formato:

UTC +hhmm *dificultades*

El signo (+) puede ser un signo más (+) o un signo menos (-), y *hhmm* es el desplazamiento desde UTC en horas y minutos. Las *instrucciones* de variable opcionales especifican un conjunto de reglas para implementar el horario de verano o una política de cambio de reloj similar.

Si especifica *las estructuras*, un archivo delimitado por tabuladores denominado *&lt;[!DNL dstrules]>* [!DNL .dst] debe estar presente en el directorio Dataset\TimeZone del perfil Base (para los archivos de configuración que no están asociados a un conjunto de datos determinado) o del perfil del conjunto de datos (para los archivos de configuración que son específicos del conjunto de datos). El archivo especifica un conjunto de reglas independiente de zona horaria para el horario de verano. Puede tener diferentes conjuntos de reglas para diferentes años. El [!DNL DST.dst] archivo proporcionado por Adobe en el perfil base especifica las reglas estándar de EE.UU. establecidas por la Ley de Política Energética de 2005 (en vigor a partir de 2007) y las reglas de EE.UU. para años anteriores.

A continuación se muestran las entradas de zona horaria de muestra:

* Hora del verano del este de EE.UU.: Zona horaria = cadena: UTC -0500 DST
* Hora UTC sin desplazamiento y sin *instrucciones* (correspondiente a GMT): Zona horaria = cadena: UTC -0000

Cuando se utiliza este formato, la zona horaria del sistema de [!DNL Insight Server], [!DNL Insight]y [!DNL Report] los equipos no debe ser la misma que la zona horaria especificada. Además, todos los perfiles de conjuntos de datos activos de un [!DNL Insight Server] equipo no necesitan tener la misma configuración de huso horario.

La siguiente tabla contiene la lista de códigos que puede utilizar para especificar zonas horarias en parámetros basados en tiempo.

## Tabla de códigos de zona horaria {#section-3cab225b864f4e54ac4f5bd83ab4ed36}

>[!NOTE]
>
>Si va a implementar el horario de verano o una política de cambio de reloj similar, debe guardar el [!DNL .dst] archivo que contiene las reglas correspondientes en el equipo *de nombres* de perfil \Dataset\Timezone directory on the [!DNL Insight Server] .

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
