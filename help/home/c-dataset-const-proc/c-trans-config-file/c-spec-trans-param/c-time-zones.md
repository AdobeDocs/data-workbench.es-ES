---
description: El parámetro Zona horaria del archivo Transformation.cfg controla las dimensiones horarias, las conversiones horarias (por ejemplo, la definición del campo x-local-timestring ) y el formato de todas las horas locales en el perfil del conjunto de datos.
title: Zonas horarias
uuid: 7b253c5a-f2b1-410c-9433-f13ed1d7a8b3
exl-id: c8dc49d5-3245-428a-bfb9-42970df73d3e
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '396'
ht-degree: 1%

---

# Zonas horarias{#time-zones}

{{eol}}

El parámetro Zona horaria del archivo Transformation.cfg controla las dimensiones horarias, las conversiones horarias (por ejemplo, la definición del campo x-local-timestring ) y el formato de todas las horas locales en el perfil del conjunto de datos.

>[!NOTE]
>
>El parámetro Zona horaria no afecta a la funcionalidad de nivel del sistema, como las marcas de tiempo en los registros de estado y eventos, que se expresan en la hora local del sistema.

El parámetro Zona horaria admite un formato de zona horaria independiente del sistema (&quot;Hora universal coordinada&quot;) con el siguiente formato:

Zona horaria = cadena: Instrucciones UTC +hmm

El signo (+) puede ser un signo más (+) o un signo menos (-), y *hmm* es el desplazamiento con respecto a UTC en horas y minutos. La variable opcional *Dstrules* especifica un conjunto de reglas para implementar el cambio de horario de verano o una política de cambio de reloj similar.

Si especifica *Dstrules*, un archivo delimitado por tabuladores denominado [!DNL dstrules .dst] debe estar presente en el subdirectorio Dataset\TimeZone del perfil del conjunto de datos. El archivo especifica un conjunto de reglas independientes de zona horaria para el horario de verano. Puede tener diferentes conjuntos de reglas para diferentes años. La variable [!DNL DST.dst] El archivo proporcionado por el Adobe en el perfil de base especifica las normas estándar de los Estados Unidos establecidas por la Ley de Política Energética de 2005 (en vigor a partir de 2007) y las normas de los Estados Unidos para años anteriores.

A continuación se enumeran las entradas de zona horaria de muestra:

* Hora de verano de EE. UU.: Zona horaria = cadena: UTC -0500 DST
* Tiempo UTC sin desplazamiento y sin dificultades : Zona horaria = cadena: UTC -0000

Cuando se utiliza este formato, la zona horaria del sistema del servidor de Data Workbench, Data Workbench y [!DNL Report] Los equipos no deben ser los mismos que el huso horario especificado. Además, todos los perfiles de conjuntos de datos activos en un equipo de servidor de Data Workbench no necesitan tener la misma configuración de zona horaria.

Adobe no recomienda ejecutar más de un perfil de conjunto de datos en un único equipo de servidor de Data Workbench o clúster de servidores de Data Workbench.

Los usuarios de Data Workbench verán datos en la zona horaria del perfil del conjunto de datos en lugar de la zona horaria del sistema. Adobe recomienda que la zona horaria del sistema para un equipo de servidor de Data Workbench sea la misma que la utilizada en sus conjuntos de datos.

>[!NOTE]
>
>Puede especificar un parámetro de zona horaria en la variable [!DNL Log Processing.cfg] , donde se utiliza para conversiones de tiempo durante el procesamiento del registro. Para obtener información sobre el parámetro de zona horaria en la variable [!DNL Log Processing.cfg] archivo, consulte [Archivo de configuración de procesamiento de registros](../../../../home/c-dataset-const-proc/c-log-proc-config-file/c-abt-log-proc-config-file.md).
