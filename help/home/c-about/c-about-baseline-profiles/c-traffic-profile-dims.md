---
description: El perfil Tráfico contiene las siguientes dimensiones para ayudar a identificar las acciones de los visitantes.
solution: Analytics
title: Dimensiones de perfil de tráfico
topic: Data workbench
uuid: 9c0dabfc-67c9-4772-99ac-4c503c06ea78
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Dimensiones de perfil de tráfico{#traffic-profile-dimensions}

El perfil Tráfico contiene las siguientes dimensiones para ayudar a identificar las acciones de los visitantes.

Las dimensiones de la siguiente tabla se definen en el conjunto de datos de transformación que incluye archivos en el directorio Traffic\Dataset\Transformation directory.

| Nombre | Tipo | Nivel | Descripción |
|---|---|---|---|
| Día | Simple | Sesión | El día de la primera entrada de registro de la sesión. |
| Día de la semana | Simple | Sesión | El día de la semana de la primera entrada de registro de una sesión. |
| Duración exacta de la página (oculta) | Numéricos | Vista de la página | Duración en milisegundos de la vista de página medida restando el tiempo de la siguiente vista de página desde el momento de esa vista de página. La duración exacta de la última vista de página de una sesión es siempre 0. |
| Hora | Simple | Sesión | Hora de la primera entrada de registro de una sesión. |
| Hora del día | Simple | Sesión | La hora del día de la primera entrada de registro de una sesión. |
| Mes | Simple | Sesión | Mes de la primera entrada de registro de una sesión. |
| Vista de la página | Contable | Sesión | Entrada de registro o &quot;Registro de datos del evento&quot; que cumple la condición de vista de página. |
| Referente | Simple | Sesión | Dominio de segundo nivel del referente de la primera entrada de registro de la sesión (o Ninguno si es un dominio de referente interno). |
| Sesión | Contable | API | Período de actividad contigua relacionada por parte de un visitante. Está delimitado por un período de inactividad de 30 minutos y un dominio de referente externo o por una duración de sesión máxima de 48 horas. Tanto estos tiempos de espera como el conjunto de dominios que se consideran internos se pueden configurar en el [!DNL Transformation.cfg] archivo. |
| URI | Simple | Vista de la página | La derivación URI de una vista de página. La dimensión URI se puede redefinir con las transformaciones ReplaceURI, PrependURI y AppendURI. |
| API | Contable | N/A | Un valor único de x-trackingid. Normalmente corresponde a un navegador único si se utilizan cookies persistentes. De lo contrario, x-trackingid puede basarse en el número IP o en algún otro identificador único, como el nombre común x.509. |
| Semana | Simple | Sesión | La semana de la primera entrada de registro de una sesión. |

Las dimensiones de la tabla siguiente se definen en el directorio Dimension del perfil de tráfico:

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
   <td colname="col2"> Simple </td> 
   <td colname="col03"> API </td> 
   <td colname="col3"> El tipo de agente de usuario utilizado por el visitante, incluido el número de versión (por ejemplo, MSIE 6.0). </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Tipo de navegador </td> 
   <td colname="col2"> Simple </td> 
   <td colname="col03"> API </td> 
   <td colname="col3"> El tipo de agente de usuario utilizado por el visitante (por ejemplo, MSIE). </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Motor de búsqueda </td> 
   <td colname="col2"> Simple </td> 
   <td colname="col03">Sesión <p>PRIMERA FILA </p></td> 
   <td colname="col3"> El primer motor de búsqueda de una sesión de visitante cuando un visitante ha buscado desde un motor de búsqueda con nombre. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> URI siguiente </td> 
   <td colname="col2"> Derivado (ShiftDim basado en la dimensión URI) </td> 
   <td colname="col03"> Vista de la página </td> 
   <td colname="col3"> URI del siguiente URI después del URI seleccionado actualmente. Esta dimensión derivada se utiliza para realizar un análisis sobre lo que los visitantes hacen después de cualquier URI determinado. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Onetime vs Repetir </td> 
   <td colname="col2"> Derivado (SegmentDim según las métricas Visitantes repetidos y Visitantes únicos) </td> 
   <td colname="col03"> API </td> 
   <td colname="col3"> Tipo de visitante: una vez o una repetición. Los visitantes únicos solo han tenido una sesión en el sitio, mientras que los visitantes repetidos han tenido más de una sesión. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Página </td> 
   <td colname="col2"> Derivado (RenameDim según la dimensión URI) </td> 
   <td colname="col03"> Vista de la página </td> 
   <td colname="col3"> Nombre de cada página visitada durante una sesión. Inicialmente, el nombre de cada página es el mismo que el URI, pero se puede cambiar para facilitar la interpretación. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Referente </td> 
   <td colname="col2"> Se hereda de la dimensión Referente integrada </td> 
   <td colname="col03"> Sesión </td> 
   <td colname="col3"> El nombre de dominio de segundo nivel del sitio web que dirigió por primera vez una sesión al sitio (tal como lo proporciona el explorador del visitante). </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Frase de búsqueda </td> 
   <td colname="col2"> Simple </td> 
   <td colname="col03">Sesión <p>PRIMERA FILA </p></td> 
   <td colname="col3"> Primera frase de búsqueda en la sesión de un visitante, según la transferencia de un motor de búsqueda cuando un visitante ha buscado desde un motor de búsqueda con nombre. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Término de búsqueda </td> 
   <td colname="col2"> De varios a muchos </td> 
   <td colname="col03"> Sesión </td> 
   <td colname="col3"> Cada término de búsqueda se pasa por un motor de búsqueda cuando un visitante tiene una pulsación del referente de búsqueda desde un motor de búsqueda con nombre. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Duración de la sesión </td> 
   <td colname="col2"> Derivado (métrica Dim según la métrica Duración exacta de la página) </td> 
   <td colname="col03"> Sesión </td> 
   <td colname="col3"> Duración de una sesión en incrementos de 30 segundos. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Número de sesión </td> 
   <td colname="col2"> Simple </td> 
   <td colname="col03"> Sesión </td> 
   <td colname="col3"> Número de veces que un visitante ha visitado el sitio. Por ejemplo: los visitantes que ingresan al sitio por primera vez tienen un número de sesión de "1", los que lo hacen por segunda vez tienen un número de sesión de "2", etc. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Vistas de página de sesión </td> 
   <td colname="col2"> Derivado (métrica Dim según la métrica Vistas de página) </td> 
   <td colname="col03"> Sesión </td> 
   <td colname="col3"> Número de vistas de página en una sesión. Por ejemplo: si selecciona "3" en la dimensión Vistas de página de sesión, se seleccionarían todas las sesiones con exactamente 3 vistas de página. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Motor de búsqueda </td> 
   <td colname="col2"> Simple </td> 
   <td colname="col03"> Sesión </td> 
   <td colname="col3"> El nombre de dominio de segundo nivel del primer sitio Web que es un motor de búsqueda con nombre que dirigió a un visitante al sitio durante una sesión (según lo proporcionado por el explorador del visitante). </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Dimensiones temporales </td> 
   <td colname="col2"> Simple </td> 
   <td colname="col03"> Sesión </td> 
   <td colname="col3"> Hora, día, hora del día, semana, día de la semana, mes, trimestre o año en los que se inició una sesión. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Dimensiones de informes de tiempo </td> 
   <td colname="col2"> Derivadas (dimensiones LastN y Rename basadas en dimensiones de tiempo integradas) </td> 
   <td colname="col03"> Sesión </td> 
   <td colname="col3"> Dimensiones, incluyendo Días anteriores, Días del último mes, Días de la última semana, Días de este mes, Días de esta semana, Horas del día, Horas del día de ayer, Últimos 12 meses, Últimos 2 meses, Últimas 2 semanas, Últimas 24 horas, Últimos 3 meses, Últimas 4 semanas, Últimos 6 meses, Últimos 7 días y Hoy, Últimas 8 semanas, Últimos 9 meses, Mes, Última semana, Meses atrás, Este Mes, Esta Semana, Este y Últimos 14 Días, Este y Últimos 6 Meses, Esta y Últimas 8 Semanas, Hoy, Informes Hoy, Hoy y Últimos 30 Días, Semanas Antes y Ayer proporcionan una manera conveniente de construir un espacio de trabajo o informe que siempre muestra una porción de datos en el Conjunto de datos. Cada una de ellas se basa en el momento en que se inicia una sesión. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> URI </td> 
   <td colname="col2"> Se hereda del URI de dimensión integrado </td> 
   <td colname="col03"> Vista de la página </td> 
   <td colname="col3"> URI de cada página vista. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Vistas de página del visitante </td> 
   <td colname="col2"> Derivado (métrica Dim según la métrica Vistas de página) </td> 
   <td colname="col03"> API </td> 
   <td colname="col3"> Número de vistas de página realizadas hasta la fecha por un visitante. Por ejemplo: si selecciona "3" en la dimensión Vistas de página del visitante, se seleccionarán todos los visitantes con exactamente 3 vistas de página en todas sus sesiones. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Referente del visitante </td> 
   <td colname="col2"> Se hereda del referente de dimensión integrado </td> 
   <td colname="col03"> API </td> 
   <td colname="col3"> El nombre de dominio de segundo nivel del sitio web que dirigió por primera vez a un visitante al sitio durante su primera sesión (tal como lo proporciona el explorador del visitante). </td> 
  </tr> 
 </tbody> 
</table>

