---
description: En esta sección se explica cómo crear marcas de hora para un conjunto de datos del área de trabajo de datos.
title: Configuración del tiempo de evento
uuid: 0230154d-05a2-44cf-9456-0a27e55f58ef
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Configuración del tiempo de evento{#setting-up-event-time}

En esta sección se explica cómo crear marcas de hora para un conjunto de datos del área de trabajo de datos.

## Información sobre la hora del evento {#section-e10ef2b5b6244dc5b215836e3c77d663}

Hora del evento es la fecha y la hora en que se produce la solicitud (o evento).

Normalmente, para los datos en línea, *x_hit_time_gmt* se utiliza como campo de marca de hora. La hora de la llamada se puede utilizar como marca de hora para los datos sin conexión (como los datos del centro de llamadas). Se trata de un campo obligatorio y todas las fuentes de datos deben tener un campo en él que pueda utilizarse como marca de hora. Esta información debe ser proporcionada por su organización.

En DWB, las siguientes variables predefinidas capturan la marca de tiempo:

<table id="table_C24BD56CEB4E42F68D645EBB65585D16"> 
 <tbody> 
  <tr> 
   <td colname="col1"><i>x-timestamp</i> </td> 
   <td colname="col2"> <p> La fecha y hora (GMT) a las que el servidor recibió la solicitud. El tiempo se expresa como el número de 100 nanosegundos desde el 1 de enero de 1600. </p> <p>Ejemplo: 127710989320000000 sería el valor de <i>x-timestamp</i> para 11:28:52.0000000 el martes 13 de septiembre de 2005. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><i>x-timestring</i> </td> 
   <td colname="col2"> <i>x-timestamp</i> con el formato AAAA-MM-DD HH:MM:SS.mmm. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><i>x-unixtime</i> </td> 
   <td colname="col2"> <i>x-unixtime</i> es la hora de epoc que representa el número de segundos desde el 1 de enero de 1970, a las 00:00:01. </td> 
  </tr> 
 </tbody> 
</table>

En función del formato del campo de fecha, se utiliza x-timestamp o x-unixtime o x-timestring. Por ejemplo, si los datos entrantes tienen el formato AAAA-MM-DD, se utilizará la cadena de hora x.

La marca de tiempo se define en uno de los formatos y DWB genera internamente los otros dos formatos. Además, se trata de campos DWB predefinidos y no se debe utilizar el mismo nombre para ningún otro campo.

## Husos horarios definidos en DWB {#section-3cdd12254342442b917376661e1d9c9f}

Si el campo de fecha contiene cualquiera de los husos horarios mencionados a continuación, DWB considerará toda la fila de ese huso horario en particular. Por ejemplo, un archivo tiene la fecha definida como 2015-01-01 00:00:00 gmty otro archivo tiene el valor 2015-01-01 00:00:00 cst, la fecha del primer archivo se considerará en GMT CSHPE, mientras que la fecha del segundo archivo estará en Zona horaria T.

| Código | Zona horaria |
|---|---|
| gmt | Medio de Greenwich |
| est | Estándar oriental |
| edt | Luz de verano oriental |
| cst | Central Standard |
| cdt | Luz diurna central |
| mst | Mountain Standard |
| mdt | Luz diurna de montaña |
| pst | Norma del Pacífico |
| pdt | Luz de día del Pacífico |

>[!NOTE]
>
>DWB sólo procesa las zonas horarias mencionadas anteriormente.

## Configuración de zonas horarias personalizadas {#section-7c351921f22b439b81c73f40d5b47536}

DWB no procesa el desplazamiento en el huso horario. Para tener en cuenta el desplazamiento en el huso horario, se debe dar formato a los datos en ese huso horario de desplazamiento.

Ejemplo: para tener en cuenta el formato de fecha en la zona horaria del CCT, los datos deben estar en formato AAAA-MM-DD HH:MM:SS UTC +/-HHMM desde el cliente.

2015-10-18 05:00:00 UTC -0200

## Cómo configurar la hora y la marca de hora del evento {#section-81507080f0b44ae6b83d3650ba019812}

En función del formato de campo de fecha, se utiliza la variable *x-timestamp, x-unixtime* o *x-timestring* . En el ejemplo siguiente, como *x-hit_time_gmt* viene en formato unix epoc, se utiliza *x-unixtime* .

En el archivo DWB [!DNL foundation.cfg] (o en cualquier otro archivo de configuración de la carpeta de procesamiento del registro de Dataset), utilice la transformación Copiar para establecer el tiempo de evento como se muestra:

En función del formato de campo de fecha, se utiliza x-timestamp, x-unixtime o x-timestring. En el ejemplo siguiente, dado que x-hit_time_gmt tiene un formato de epoc unix, se utiliza x-unixtime.

En insight foundation.cfg (o cualquier otra configuración de la carpeta de procesamiento del registro Datasetà), utilice la transformación Copiar para establecer el tiempo de evento como se muestra a continuación: ![](assets/dwb_impl_timestamp1.png)

Si la fecha en es el formato AAAA-MM-DD HH:MM:SS.mmm, se utiliza la cadena de hora x. ![](assets/dwb_impl_timestamp2.png)Ejemplo: Si el campo de fecha está en un formato distinto al definido en DWB, por ejemplo AAAA/MM/DD, primero formatéelo en uno de los formatos de marca de hora aceptados por el DWB y luego asígnelo a la variable correspondiente. En la siguiente captura de pantalla, la fecha se convierte primero al formato AAAA-MM-DD y, a continuación, se asigna a *x-timestring *variable. ![](assets/dwb_impl_timestamp3.png)

