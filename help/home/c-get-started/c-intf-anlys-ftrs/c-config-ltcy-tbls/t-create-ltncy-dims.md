---
description: Las dimensiones de latencia se crean a partir de una dimensión contable principal, como Sesiones, y una dimensión de tiempo, como Día.
title: Creación de una dimensión de latencia
uuid: 531d8bf6-a66f-4b02-9d81-05664fb9c988
exl-id: 38b470ef-9409-455b-b2b8-b0391f80b800
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '542'
ht-degree: 2%

---

# Creación de una dimensión de latencia{#create-a-latency-dimension}

Las dimensiones de latencia se crean a partir de una dimensión contable principal, como Sesiones, y una dimensión de tiempo, como Día.

Cuando crea una tabla de latencia en Data Workbench, agrega automáticamente una dimensión de latencia al archivo de visualización (.vw). Puede editar la dimensión de latencia de una tabla siguiendo los pasos a continuación.

**Para editar una dimensión de latencia**

1. Abra la tabla de latencia que creó en un editor de texto como el Bloc de notas. Se encuentra en la carpeta Usuario > `working profile name` > Trabajo dentro del directorio de instalación de la Data Workbench.

   La dimensión de latencia definida incluye los parámetros que se muestran en el siguiente ejemplo. (La definición de la dimensión de latencia puede incluir parámetros adicionales). El [!DNL line entity = LatencyDim:] indica el inicio de la definición de la dimensión de latencia.

   ```
   entity = LatencyDim:
   Name = string: dimension name
   Level = ref: wdata/model/dim/level
   Clip = ref: wdata/model/dim/clip
   Time = ref: wdata/model/dim/time dimension
   Format = printf_format: 
   format = string: %+0.0f time string
   offset = double: offset
   Time Before = int: time before
   Time After = int: time after
   ```

1. Edite los valores de los parámetros Nombre, Nivel, Clip, Tiempo, Formato, Tiempo antes o Tiempo después utilizando la siguiente tabla como guía:

   <table id="table_13DF30B8B7314F118D0ED5DF9EA70B9B"> 
   <thead> 
   <tr> 
      <th colname="col1" class="entry"> Para este parámetro... </th> 
      <th colname="col2" class="entry"> Proporcione esta información... </th> 
   </tr> 
   </thead>
   <tbody> 
   <tr> 
      <td colname="col1"> <p>Nombre </p> </td> 
      <td colname="col2"> <p>Opcional. Nombre de la dimensión de latencia que aparece en el menú contextual cuando se hace clic con el botón derecho en la etiqueta de dimensión o los elementos. </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> <p>Nivel </p> </td> 
      <td colname="col2"> <p>Dimensión contable que es la principal de la dimensión de latencia. Algunos ejemplos son Sesión, Visitante y Vista de página. </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> <p>Clip </p> </td> 
      <td colname="col2"> <p>Dimensión contable que tiene una relación "uno a varios" con el nivel de la dimensión de latencia. La latencia no se calcula entre los límites de esta dimensión. Por ejemplo, si especifica un nivel de vista de página y un clip de sesión, las latencias se calculan para las vistas de página que se produjeron durante la misma sesión que el evento. </p> <p>Para obtener información sobre las dimensiones "uno a varios" (simples), consulte la <i>Guía de configuración del conjunto de datos</i>. </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> <p>Fecha </p> </td> 
      <td colname="col2"> <p>Dimensión utilizada para medir el tiempo transcurrido para la dimensión de latencia. Esta dimensión puede ser una dimensión de tiempo, como Día o Hora, o una dimensión contable, como Visitante, Sesión o Vista de página. </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Formato </td> 
      <td colname="col2"> <p>Opcional. Especifica el aspecto de la visualización de latencia en la Data Workbench. En el parámetro Format , puede editar los siguientes valores: 
      <ul id="ul_ABF4C17BDE2E4F6C9CBDD933674DE861"> 
         <li id="li_5ED6A7267C81444983AF8507ADC6A5AB">Cadena de hora. Unidad de tiempo mostrada en la visualización de latencia, como día o semana. Asegúrese de cambiar la cadena de hora cuando cambie la dimensión de tiempo. </li> 
         <li id="li_E3B517ECE1494221AAE90455CC0AAB42">Desplazamiento. Un número entero igual al negativo del valor para Tiempo antes. Por ejemplo, si Tiempo antes es 7, el desplazamiento debe ser -7. </li> 
      </ul> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> <p>Tiempo antes </p> </td> 
      <td colname="col2"> <p>Cantidad máxima de tiempo (expresada en las unidades de la dimensión Tiempo) antes del evento para el que se calcula la latencia. Si este valor se establece en 0 o no se establece en absoluto, la latencia se calcula solo para la dirección de avance. </p> <p>Si cambia este valor, asegúrese de cambiar el valor de desplazamiento en el parámetro Format : El desplazamiento es el negativo del valor de Tiempo antes. </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> <p>Tiempo después </p> </td> 
      <td colname="col2"> <p>Cantidad máxima de tiempo (expresada en las unidades de la dimensión Tiempo) después del evento para el que se calcula la latencia. </p> </td> 
   </tr> 
   </tbody> 
   </table>

1. Guarde el archivo [!DNL .vw] en la carpeta User\*working profile name*\Work .

   A continuación se muestran los ajustes de la dimensión de latencia predeterminada:

   ```
   entity = LatencyDim:
   Name = string: 
   Level = ref: wdata/model/dim/Session
   Clip = ref: wdata/model/dim/Visitor
   Time = ref: wdata/model/dim/Day
   Time Before = int: 7
   Time After = int: 7
   ```

   En la siguiente dimensión de latencia, la latencia de cada evento de sesión se calcula en horas y Tiempo antes se establece en cero. Por lo tanto, la latencia se calcula solo para aquellas sesiones que se produjeron dentro de las 24 horas posteriores al evento definido.

   ```
   entity = LatencyDim:
   Name = string:
   Level = ref: wdata/model/dim/Session
   Clip = ref: wdata/model/dim/Visitor
   Time = ref: wdata/model/dim/Hour
   Time Before = int: 0
   Time After = int: 24
   ```
