---
description: El parámetro Huso horario del archivo Transformation.cfg controla las dimensiones horarias, las conversiones horarias (por ejemplo, la definición del campo x-local-timestring) y el formato de todas las horas locales en el perfil del conjunto de datos.
solution: Analytics
title: Zonas horarias
topic: Data workbench
uuid: 7b253c5a-f2b1-410c-9433-f13ed1d7a8b3
translation-type: tm+mt
source-git-commit: 27600561841db3705f4eee6ff0aeb8890444bbc9

---


# Zonas horarias{#time-zones}

El parámetro Huso horario del archivo Transformation.cfg controla las dimensiones horarias, las conversiones horarias (por ejemplo, la definición del campo x-local-timestring) y el formato de todas las horas locales en el perfil del conjunto de datos.

>[!NOTE]
>
>El parámetro Huso horario no afecta a la funcionalidad de nivel de sistema, como las marcas de hora en los registros de estado y eventos, que se expresan en la hora local del sistema.

El parámetro Huso horario admite un formato de zona horaria independiente del sistema (&quot;Hora universal coordinada&quot;) con el siguiente formato:

Zona horaria = cadena: Rótulos UTC +hhmm

El signo (+) puede ser un signo más (+) o un signo menos (-), y *hhmm* es el desplazamiento desde UTC en horas y minutos. Las *instrucciones* de variable opcionales especifican un conjunto de reglas para implementar el horario de verano o una política de cambio de reloj similar.

Si se especifican *disoluciones*, un archivo delimitado por tabuladores denominado [!DNL dstrules .dst] debe estar presente en el subdirectorio Dataset\TimeZone del perfil del conjunto de datos. El archivo especifica un conjunto de reglas independiente de zona horaria para el horario de verano. Puede tener diferentes conjuntos de reglas para diferentes años. El [!DNL DST.dst] archivo proporcionado por Adobe en el perfil base especifica las reglas estándar de EE.UU. establecidas por la Ley de Política Energética de 2005 (en vigor a partir de 2007) y las reglas de EE.UU. para años anteriores.

A continuación se muestran las entradas de huso horario de muestra:

* Hora del verano del este de EE.UU.: Zona horaria = cadena: UTC -0500 DST
* Tiempo UTC sin desplazamiento ni desempates: Zona horaria = cadena: UTC -0000

Cuando se utiliza este formato, el huso horario del sistema del servidor del área de trabajo de datos, el área de trabajo de datos y [!DNL Report] los equipos no debe ser el mismo que el huso horario especificado. Además, todos los perfiles de conjuntos de datos activos de un equipo de servidor del área de trabajo de datos no necesitan tener la misma configuración de zona horaria.

Adobe no recomienda ejecutar más de un perfil de conjunto de datos en un único equipo de servidor del área de trabajo de datos o clúster de servidores del área de trabajo de datos.

Los usuarios del área de trabajo de datos verán los datos en el huso horario del perfil del conjunto de datos en lugar del huso horario del sistema. Adobe recomienda que la zona horaria del sistema para un equipo de servidor del área de trabajo de datos sea la misma que la zona horaria utilizada en sus conjuntos de datos.

>[!NOTE]
>
>Puede especificar un parámetro de zona horaria en el [!DNL Log Processing.cfg] archivo, donde se utiliza para las conversiones de tiempo durante el procesamiento del registro. Para obtener información sobre el parámetro Huso horario del [!DNL Log Processing.cfg] archivo, consulte Archivo [de configuración de procesamiento](../../../../home/c-dataset-const-proc/c-log-proc-config-file/c-abt-log-proc-config-file.md)de registro.

