---
description: Muestra cómo configurar Título, Perfil, Dimensión, Métrica, Filtro, Mostrar arriba, Ordenar por y Período de tiempo.
solution: Analytics
title: Configuración de visualizaciones
topic: Data workbench
uuid: aca77188-8f28-4554-8913-412b252f688c
translation-type: tm+mt
source-git-commit: 25366087936dfa5e31c5921aac400535ec259f2e

---


# Configuración de visualizaciones{#configuring-visualizations}

Muestra cómo configurar Título, Perfil, Dimensión, Métrica, Filtro, Mostrar arriba, Ordenar por y Período de tiempo.

Cada visualización del lienzo del tablero tiene su propia configuración. Cuando se agrega una visualización por primera vez al lienzo del tablero, su ventana de configuración aparecerá automáticamente. Una vez configurada, la visualización se puede modificar en cualquier momento haciendo clic en el icono de engranaje en la parte superior derecha de la ventana de visualización.

>[!NOTE]
>
>Las opciones de configuración varían ligeramente según el tipo de visualización que se esté mostrando.

## Título de visualización {#section-0414844283d745ae912e85f8ea14a51d}

Este campo permite personalizar el título que se muestra en la parte superior de la visualización. De forma predeterminada, el título se establece en **[!UICONTROL Automatic Title]**, lo que generará automáticamente un título para la ventana de visualización. Al borrar el **[!UICONTROL Automatic Title]** botón, puede colocar cualquier título en este campo. (Este campo se aplica a todas las visualizaciones).

![](assets/title.png)

## Perfil {#section-16eb0def0a2d4eb289f5bb9200d14754}

Este campo permite seleccionar el perfil desde el que desea visualizar los datos. Al hacer clic en el menú desplegable, se le proporcionará una lista de perfiles para los que tiene acceso. (Este campo no se aplica a las visualizaciones de texto enriquecido).

Los perfiles son conjuntos de datos definidos en el área de trabajo de datos que contienen datos sobre un determinado dominio, junto con las dimensiones, métricas y filtros que acompañan a los datos. Un perfil se suele diseñar para cumplir un propósito específico (como el tráfico de mercadotecnia o de sitio web).

>[!NOTE]
>
>Solo puede ver los perfiles para los que se le ha concedido acceso. Para obtener más información, consulte Controles de acceso.

![](assets/profile.png)

## Dimensión {#section-4ebb8c4308a146c3a35c7ac7ab6b579f}

Permite seleccionar la dimensión que desea visualizar. La lista se rellena a partir de la lista de dimensiones disponibles del perfil seleccionado en el campo Perfil. Haga clic en la dimensión deseada y, a continuación, haga clic en el botón Seleccionar. (Este campo no se aplica a las visualizaciones Leyendas de métricas y Texto enriquecido).

Las dimensiones son categorías de tipos de datos similares. Por ejemplo, la dimensión Días de la semana se compone de los siguientes elementos de datos: Domingo, lunes, martes, miércoles, jueves, viernes y sábado. Las dimensiones muestran lo que se está midiendo.

![](assets/dimension.png)

## Metric(s) {#section-7d46f2f1b9fe4e539b5eb0a0dc6e5ad3}

Permite seleccionar las métricas que se van a visualizar. Las métricas son objetos cuantitativos y están definidas por alguna expresión cuantificable. Por ejemplo: Vistas de página por sesión se deriva de la expresión del recuento de Vistas de página dividido por el recuento de Sesiones. Las métricas responden a la pregunta de &quot;¿cuántos?&quot;

Las visualizaciones de una sola métrica tienen una ventana de selección de una sola métrica:

![](assets/metrics2.png)

Las visualizaciones multimétricas tienen una ventana de selección multimétrica:

![](assets/metrics.png)

La lista se rellena a partir de la lista de métricas disponibles en el perfil seleccionado en el campo Perfil.

Haga clic en las métricas deseadas y, a continuación, haga clic en **[!UICONTROL Select]**. (Este campo no se aplica a las visualizaciones de texto enriquecido).

## Filtros {#section-f8619ae2f8e54735a2c1b0fbb8bb1281}

Seleccione los filtros que desee aplicar a la visualización. La ventana de selección de filtros permite seleccionar varios filtros en la lista de filtros. La lista se rellena a partir de la lista de filtros disponibles en el perfil seleccionado en el campo Perfil. Haga clic en el filtro deseado y luego haga clic en **[!UICONTROL Select]**.

>[!NOTE]
>
>Los filtros aplicados aquí solo se aplican a su visualización correspondiente, no a todo el tablero. Esto resulta útil para comparar los resultados de dos visualizaciones diferentes con diferentes filtros aplicados.

![](assets/filter.png)

## Mostrar entradas {#section-7ce71cb0fa6446998b710b427e68b133}

Las visualizaciones del tablero no están diseñadas para mostrar la totalidad de los datos. En su lugar, permiten especificar el número de registros de dimensión que desea mostrar en la visualización. Esto muestra el número superior de dimensiones en función del valor de ordenación que se indica a continuación. (Este campo no se aplica a las visualizaciones Tablas, Leyendas de métricas y Texto enriquecido).

![](assets/display_top.png)

## Sort By {#section-f686249e20444359bff87c00cc2ba29f}

Esto le permite especificar cómo se deben ordenar los datos cuando se muestran en la visualización. (Este campo no se aplica a las visualizaciones Tablas, Leyendas de métricas y Texto enriquecido). Existen varias opciones de clasificación:

* **[!UICONTROL Default]** - Devuelve los datos sin ordenar según el orden de clasificación almacenado en el área de trabajo de datos. Esta es la opción que se utiliza para datos basados en el tiempo, como hora, día, semana o mes.
* **[!UICONTROL Dimension]** -Ordene los datos según el valor de dimensión alfanumérica.
* **[!UICONTROL Metric]** - Clasifique los datos en función del valor de la métrica y resulta útil para visualizar rápidamente las dimensiones principales.
* **[!UICONTROL Descending]** - Ordenar los datos en orden descendente.
* **[!UICONTROL Ascending]** - Ordenar los datos en orden ascendente.

![](assets/sort_by.png)

## Período de tiempo {#section-6220368e9e524b46ac735add6ab9edb0}

Esta visualización permite especificar la fecha de inicio y/o finalización que se desea que muestren los datos en la visualización.

Al seleccionar **[!UICONTROL All Dates]**se muestra el intervalo de fechas completo disponible en el perfil.

La selección **[!UICONTROL Range]** muestra únicamente los datos que se encuentran dentro de un rango especificado. Para introducir el intervalo de fechas, puede escribir la fecha de inicio y/o finalización, o bien utilizar una entrada de calendario seleccionando el icono de calendario.

(Este campo no se aplica a las visualizaciones de texto enriquecido).

>[!NOTE]
>
>Los intervalos de fechas aplicados aquí solo se aplican a su visualización correspondiente, no a todo el tablero. Esto resulta útil para comparar los resultados de dos visualizaciones diferentes con intervalos de fechas aplicados diferentes.

![](assets/time_period.png)

