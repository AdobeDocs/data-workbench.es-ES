---
description: En esta sección se explica cómo crear marcas de hora para un conjunto de datos de Data Workbench.
title: Configuración del tiempo del evento
uuid: 0230154d-05a2-44cf-9456-0a27e55f58ef
exl-id: 9632e713-5cf9-4acf-aafa-bfdf79a51ad9
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '592'
ht-degree: 2%

---

# Configuración del tiempo del evento{#setting-up-event-time}

{{eol}}

En esta sección se explica cómo crear marcas de hora para un conjunto de datos de Data Workbench.

## Información sobre la hora del evento {#section-e10ef2b5b6244dc5b215836e3c77d663}

Hora del evento es la fecha y la hora a las que se produce la solicitud (o evento).

Normalmente, para los datos en línea, *x_hit_time_gmt* se utiliza como campo de marca de tiempo. La hora de la llamada se puede usar como marca de tiempo para los datos sin conexión (como los datos del centro de llamadas). Se trata de un campo obligatorio y todas las fuentes de datos deben tener un campo que pueda utilizarse como marca de tiempo. Su organización debe proporcionar esta información.

En DWB, las siguientes variables predefinidas capturan la marca de tiempo:

<table id="table_C24BD56CEB4E42F68D645EBB65585D16"> 
 <tbody> 
  <tr> 
   <td colname="col1"><i>x-timestamp</i> </td> 
   <td colname="col2"> <p> La fecha y hora (GMT) a las que el servidor recibió la solicitud. El tiempo se expresa como el número de 100 nanosegundos desde el 1 de enero de 1600. </p> <p>Ejemplo: 127710989320000000 sería el <i>x-timestamp</i> valor para 11:28:52.000000 el martes 13 de septiembre de 2005. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><i>x-timestring</i> </td> 
   <td colname="col2"> <i>x-timestamp</i> con el formato AAAA-MM-DD HH:MM:SS.mmm. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><i>x-unixtime</i> </td> 
   <td colname="col2"> <i>x-unixtime</i> es la hora de epoc que representa el número de segundos desde el 1 de enero de 1970 a las 00 horas:00:01. </td> 
  </tr> 
 </tbody> 
</table>

En función del formato de campo de fecha, se utiliza x-timestamp o x-unixtime o x-timestring. Por ejemplo, si los datos entrantes tienen el formato AAAA-MM-DD, se utilizará la cadena de tiempo x.

La marca de tiempo se define en uno de los formatos y DWB genera internamente los otros dos formatos. Además, son campos DWB predefinidos y no se debe utilizar el mismo nombre para ningún otro campo.

## Husos horarios definidos en DWB {#section-3cdd12254342442b917376661e1d9c9f}

Si el campo de fecha contiene cualquiera de los husos horarios mencionados a continuación, DWB considera la fila completa de ese huso horario en particular. Por ejemplo, un archivo tiene la fecha definida como 2015-01-01 00:00:00 gmtand otro archivo tiene el valor 2015-01-01 00:00:00 cst, entonces la fecha del primer archivo se considerará en la zona horaria GMT, mientras que la fecha del segundo archivo estará en la zona horaria CST.

| Código | Zona horaria |
|---|---|
| gmt | Greenwich Media |
| est | Estándar oriental |
| edt | Luz de verano oriental |
| cst | Estándar central |
| cdt | Luz de día central |
| mst | Mountain Standard |
| mdt | Horario de montaña |
| pst | Pacific Standard |
| pdt | Luz de día del Pacífico |

>[!NOTE]
>
>DWB solo procesa las zonas horarias mencionadas anteriormente.

## Configuración de zonas horarias personalizadas {#section-7c351921f22b439b81c73f40d5b47536}

DWB no procesa el desplazamiento en la zona horaria. Para tener en cuenta el desplazamiento en la zona horaria, se debe dar formato a los datos en esa zona horaria de desplazamiento.

Ejemplo: para tener en cuenta el formato de fecha en la zona horaria del CCT, los datos deben estar en AAAA-MM-DD HH:MM:Seleccione el formato UTC +/-HHMM del cliente.

2015-10-18 05:00:00 UTC -0200

## Cómo establecer la hora/marca de tiempo del evento {#section-81507080f0b44ae6b83d3650ba019812}

En función del formato de campo de fecha, *x-timestamp, x-unixtime* o *x-timestring* se utiliza. En el ejemplo siguiente, ya que la variable *x-hit_time_gmt* viene en formato unix epoc, *x-unixtime* se utiliza.

En el DWB [!DNL foundation.cfg] (o cualquier otro archivo de configuración de la carpeta de procesamiento del registro del conjunto de datos), utilice la transformación Copiar para establecer el Tiempo de evento como se muestra:

En función del formato de campo de fecha, se utiliza x-timestamp, x-unixtime o x-timestring . En el siguiente ejemplo, dado que x-hit_time_gmt viene en formato unix epoc, se utiliza x-unixtime.

En insight foundation.cfg (o en cualquier otra configuración de la carpeta de procesamiento de registros del conjunto de datos), utilice la transformación Copiar para establecer el Tiempo de evento como se muestra a continuación: ![](assets/dwb_impl_timestamp1.png)

Si la fecha en es AAAA-MM-DD HH:MM:en formato SS.mmm, se utiliza x-timestring. ![](assets/dwb_impl_timestamp2.png)Ejemplo: Si el campo de fecha tiene un formato distinto al definido en DWB, por ejemplo AAAA/MM/DD, formatéelo primero en uno de los formatos de marca de tiempo aceptados por el DWB y, a continuación, asígnelo a la variable correspondiente. En la captura de pantalla siguiente, la fecha primero se convierte al formato AAAA-MM-DD y luego se asigna a la variable *x-timestring *. ![](assets/dwb_impl_timestamp3.png)
