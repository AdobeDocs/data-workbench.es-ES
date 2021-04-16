---
description: El perfil Tráfico contiene las siguientes dimensiones para ayudar a identificar las acciones de los visitantes.
title: Dimensiones del perfil de tráfico
uuid: 9c0dabfc-67c9-4772-99ac-4c503c06ea78
exl-id: 1e7d2904-aa5d-4848-a398-5d4669953be9
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '987'
ht-degree: 8%

---

# Dimensiones del perfil de tráfico{#traffic-profile-dimensions}

El perfil Tráfico contiene las siguientes dimensiones para ayudar a identificar las acciones de los visitantes.

Las dimensiones de la siguiente tabla se definen en el conjunto de datos de transformación e incluyen archivos en Traffic\Dataset\Transformation directory.

| Nombre | Tipo | Nivel | Descripción |
|---|---|---|---|
| Día | Sencilla | Sesión | El día de la primera entrada de registro de la sesión. |
| Día de la semana | Sencilla | Sesión | El día de la semana de la primera entrada de registro de una sesión. |
| Duración exacta de la página (oculta) | Numéricos | Vista de la página | La duración en milisegundos de la vista de página medida restando el tiempo de la siguiente vista de página desde el momento de la vista de página. La duración exacta de la última vista de página de una sesión es siempre 0. |
| Hora | Sencilla | Sesión | Hora de la primera entrada de registro de una sesión. |
| Hora del día | Sencilla | Sesión | Hora del día de la primera entrada de registro de una sesión. |
| Mes | Sencilla | Sesión | Mes de la primera entrada de registro de una sesión. |
| Vista de la página | Contable | Sesión | Una entrada de registro o &quot;Registro de datos de evento&quot; que cumpla la condición de vista de página. |
| Referente | Sencilla | Sesión | Dominio de segundo nivel del referente de la primera entrada de registro de la sesión (o Ninguno si es un dominio de referente interno). |
| Sesión | Contable | Visitante | Un período de actividad contigua relacionada por un visitante. Se delimita por un periodo de inactividad de 30 minutos y un dominio de referente externo o una duración máxima de sesión de 48 horas. Tanto esos tiempos de espera como el conjunto de dominios que se consideran internos se pueden configurar en el archivo [!DNL Transformation.cfg] . |
| URI | Sencilla | Vista de la página | El nombre URI de una vista de página. La dimensión URI se puede redefinir con las transformaciones ReplaceURI, PrependURI y AppendURI . |
| Visitante | Contable | N/A | Un valor único de x-trackingid. Normalmente corresponde a un explorador único si se utilizan cookies persistentes. De lo contrario, x-trackingid puede basarse en el número IP o en algún otro identificador único, como el nombre común x.509. |
| Semana | Sencilla | Sesión | La semana de la primera entrada de registro de una sesión. |

Las dimensiones de la siguiente tabla se definen en el directorio Dimension del perfil Tráfico:

<table id="table_02AC8DAD1B62443A96FABCB75C37F23A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Dimensión </th> 
   <th colname="col2" class="entry"> Tipo </th> 
   <th colname="col03" class="entry"> Nivel </th> 
   <th colname="col3" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Explorador </td> 
   <td colname="col2"> Sencilla </td> 
   <td colname="col03"> Visitante </td> 
   <td colname="col3"> El tipo de agente de usuario que utiliza el visitante, incluido el número de versión (por ejemplo, MSIE 6.0). </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Tipo de explorador </td> 
   <td colname="col2"> Sencilla </td> 
   <td colname="col03"> Visitante </td> 
   <td colname="col3"> Tipo de agente de usuario que utiliza el visitante (por ejemplo, MSIE). </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Motor de búsqueda </td> 
   <td colname="col2"> Sencilla </td> 
   <td colname="col03">Sesión <p>PRIMERA FILA </p></td> 
   <td colname="col3"> El primer motor de búsqueda en la sesión de un visitante cuando un visitante ha buscado desde un motor de búsqueda con nombre. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> URI siguiente </td> 
   <td colname="col2"> Derivado (ShiftDim basado en la dimensión URI) </td> 
   <td colname="col03"> Vista de la página </td> 
   <td colname="col3"> El URI del siguiente URI después del URI seleccionado actualmente. Esta dimensión derivada se utiliza para realizar análisis sobre qué hacen los visitantes después de cualquier URI determinado. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Onetime frente a Repeat </td> 
   <td colname="col2"> Derivado (SegmentDim en función de las métricas Visitantes repetidos y Visitantes únicos) </td> 
   <td colname="col03"> Visitante </td> 
   <td colname="col3"> Tipo de visitante: una vez o repita. Los visitantes únicos solo han tenido una sesión en el sitio, mientras que los visitantes repetidos han tenido más de una sesión. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Página </td> 
   <td colname="col2"> Derivado (Cambiar nombre de Dim en función de la dimensión URI) </td> 
   <td colname="col03"> Vista de la página </td> 
   <td colname="col3"> Nombre de cada página visitada durante una sesión. Inicialmente, el nombre de cada página es el mismo que el URI, pero se puede cambiar para facilitar la interpretación. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Referente </td> 
   <td colname="col2"> Heredado de la dimensión Referente integrada </td> 
   <td colname="col03"> Sesión </td> 
   <td colname="col3"> El nombre de dominio de segundo nivel del sitio web que remitió por primera vez una sesión al sitio (proporcionado por el explorador del visitante). </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Frase de búsqueda </td> 
   <td colname="col2"> Sencilla </td> 
   <td colname="col03">Sesión <p>PRIMERA FILA </p></td> 
   <td colname="col3"> Primera frase de búsqueda de la sesión de un visitante según la transfiere un motor de búsqueda cuando un visitante ha buscado desde un motor de búsqueda con nombre. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Término de búsqueda </td> 
   <td colname="col2"> Varios a varios </td> 
   <td colname="col03"> Sesión </td> 
   <td colname="col3"> Cada término de búsqueda según se transfiere mediante un motor de búsqueda cuando un visitante tiene una pulsación del referente de búsqueda desde un motor de búsqueda con nombre. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Duración de la sesión </td> 
   <td colname="col2"> Derivada (métrica Dim en función de la métrica Duración exacta de la página) </td> 
   <td colname="col03"> Sesión </td> 
   <td colname="col3"> Duración de una sesión en incrementos de 30 segundos. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Número de sesión </td> 
   <td colname="col2"> Sencilla </td> 
   <td colname="col03"> Sesión </td> 
   <td colname="col3"> Número de veces que un visitante ha visitado el sitio. Por ejemplo, los visitantes nuevos tienen un Número de sesión de "1", los visitantes nuevos tienen un Número de sesión de "2", etc. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Vistas de páginas de la sesión </td> 
   <td colname="col2"> Derivada (métrica Dim basada en la métrica Vistas de página) </td> 
   <td colname="col03"> Sesión </td> 
   <td colname="col3"> Número de vistas de página de una sesión. Por ejemplo, si selecciona "3" en la dimensión Vistas de página de sesión, se seleccionarían todas las sesiones con exactamente 3 vistas de página. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Motor de búsqueda </td> 
   <td colname="col2"> Sencilla </td> 
   <td colname="col03"> Sesión </td> 
   <td colname="col3"> El nombre de dominio de segundo nivel del primer sitio web que es un motor de búsqueda con nombre que hizo referencia a un visitante en el sitio durante una sesión (proporcionado por el explorador del visitante). </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Dimensiones temporales </td> 
   <td colname="col2"> Sencilla </td> 
   <td colname="col03"> Sesión </td> 
   <td colname="col3"> Hora, día, hora del día, semana, día de la semana, mes, trimestre o año en que comenzó una sesión. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Dimension de informes de tiempo </td> 
   <td colname="col2"> Derivadas (dimensiones LastN y Cambiar nombre basadas en dimensiones temporales integradas) </td> 
   <td colname="col03"> Sesión </td> 
   <td colname="col3"> Dimension, incluidos Días anteriores, Días del último mes, Días de la última semana, Días de este mes, Días de esta semana, Horas de hoy, Horas de ayer, últimos 12 meses, últimos 2 meses, últimas 2 semanas, últimas 24 horas, últimos 3 meses, últimas 4 semanas, últimos 6 meses, últimos 7 días, últimos 7 días y hoy, últimas 8 semanas, últimos 9 meses, Mes, Última semana, Meses atrás, Este mes, Esta semana, Este y Los Últimos 14 Días, Este y Los Últimos 6 Meses, Esta y Las Últimas 8 Semanas, Hoy, Informes Hoy, Hoy y Últimos 30 Días, Hace Semanas y Ayer proporcionan una forma cómoda de crear un espacio de trabajo o informe que siempre muestra una parte de los datos en el conjunto de datos. Cada uno se basa en el momento en que se inició una sesión. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> URI </td> 
   <td colname="col2"> Heredado del URI del Dimension integrado </td> 
   <td colname="col03"> Vista de la página </td> 
   <td colname="col3"> El URI de cada página vista. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Vistas de páginas del visitante </td> 
   <td colname="col2"> Derivada (métrica Dim basada en la métrica Vistas de página) </td> 
   <td colname="col03"> Visitante </td> 
   <td colname="col3"> Número de vistas de página realizadas hasta la fecha por un visitante. Por ejemplo, si selecciona "3" en la dimensión Vistas de página del visitante, se seleccionarían todos los visitantes con exactamente 3 vistas de página en todas las sesiones. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Referente de visitante </td> 
   <td colname="col2"> Heredado del referente de dimensión integrado </td> 
   <td colname="col03"> Visitante </td> 
   <td colname="col3"> El nombre de dominio de segundo nivel del sitio web que dirigió por primera vez a un visitante al sitio durante su primera sesión (proporcionado por el explorador del visitante). </td> 
  </tr> 
 </tbody> 
</table>
