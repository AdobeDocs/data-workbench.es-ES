---
description: Utilice el perfil histórico de Data Workbench para ver cómo la configuración, el hardware y otros cambios afectan al rendimiento, la estabilidad y la capacidad del servidor a lo largo del tiempo.
title: Espacio de trabajo histórico de Data Workbench
uuid: 61c45cae-f255-4d20-bb6b-f318c8dd8214
exl-id: e6d7e924-641e-468c-a828-16ebe1c8724f
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '400'
ht-degree: 2%

---

# Espacio de trabajo histórico de Data Workbench{#data-workbench-historic-workspace}

Utilice el perfil histórico de Data Workbench para ver cómo la configuración, el hardware y otros cambios afectan al rendimiento, la estabilidad y la capacidad del servidor a lo largo del tiempo.

El perfil histórico incluye un conjunto de datos basado en perfiles [Profile Performance](../../../home/monitoring-installation/monitoring-profiles/monitoring-historical-using.md#section-184a86f9de054970bf68515bb9dea85d) y el conjunto de datos basado en servidor [Server Performance](../../../home/monitoring-installation/monitoring-profiles/monitoring-historical-using.md#section-5dad5870384b40e094d50173fcd90a09) en la pestaña **[!UICONTROL Performance]**. Estos son los conjuntos de datos más utilizados y vistos desde una perspectiva anterior del rendimiento del servidor de Data Workbench. Además, puede ver los [Componentes](../../../home/monitoring-installation/monitoring-profiles/monitoring-historical-using.md#section-5be7223abb384784bafe7b37c764ea66) y [Modo de procesamiento](../../../home/monitoring-installation/monitoring-profiles/monitoring-historical-using.md#section-5be7223abb384784bafe7b37c764ea66) seleccionando la pestaña **[!UICONTROL Up Time]**.

![](assets/Historic_Performance.png)

Además, puede ver los [Componentes](../../../home/monitoring-installation/monitoring-profiles/monitoring-historical-using.md#section-5be7223abb384784bafe7b37c764ea66) y [Modo de procesamiento](../../../home/monitoring-installation/monitoring-profiles/monitoring-historical-using.md#section-5be7223abb384784bafe7b37c764ea66) seleccionando la pestaña **[!UICONTROL Up Time]**.

Para obtener información de referencia adicional sobre las dimensiones utilizadas en el perfil histórico de Data Workbench, consulte [Dimension en el perfil histórico de Insight.](../../../home/monitoring-installation/monitoring-appendix/monitoring-historical.md#concept-a42837c9c9274f83ad5bc5a6720f02b0)

## Espacio de trabajo del rendimiento del perfil {#section-184a86f9de054970bf68515bb9dea85d}

Este conjunto de datos incluye las siguientes métricas relevantes para la supervisión de Data Workbench.

* MegaBytes de entrada rápida por minuto: métricas que muestran una gran cantidad de datos introducidos durante el procesamiento inicial del registro.
* Fusión rápida MegaBytes por minuto: métricas que muestran la transformación.

![](assets/Historic_Profile_Performance.png)

>[!NOTE]
>
>Para realizar una evaluación del rendimiento real de su perfil, observe la velocidad en lugar de la hora del calendario transcurrido. La tasa se mide como los valores modificados entre las encuestas cada diez minutos.

## Espacio de trabajo del rendimiento del servidor {#section-5dad5870384b40e094d50173fcd90a09}

Este conjunto de datos supervisa las métricas del servidor más allá del alcance de los perfiles incluidos e incluye las siguientes métricas relevantes del servidor para la supervisión de Data Workbench.

* Minutos barridos estimados — Tiempo de resolución de consulta estimado.
* Milisegundos de latencia de encuesta: indicador de lo ocupado que está el software al medir cuánto tiempo se tarda en pasar por un ciclo completo de servicio de cada componente.

![](assets/Historic_Server_Performance.png)

## Espacio de trabajo de componentes {#section-5be7223abb384784bafe7b37c764ea66}

Este conjunto de datos se encuentra en la ficha Tiempo de activación .

![](assets/Up_Time.png)

El conjunto de datos de componentes incluye dos aspectos para el estado de los componentes:

* Métrica de comunicaciones: ¿respondió el proceso del servidor de Data Workbench?
* Métrica Todos los componentes: en la parte superior de la página Estado detallado hay una lista de los componentes que el host está administrando en los procesos del servidor de Data Workbench. Si algún componente está en estado de error, se muestra en la tabla Componentes en error .

![](assets/Up_Time_components.png)

## Espacio de trabajo del modo de procesamiento {#section-3e1dedb9474e4b4ba513240943e76817}

Este espacio de trabajo se encuentra en la ficha Tiempo de actividad. Este espacio de trabajo permite observar cuánto tiempo se tarda en introducir datos rápidamente, combinar rápidamente y en tiempo real.

![](assets/Up_Time_Processing_mode.png)

Este conjunto de datos proporciona características importantes de carga del servidor, como la identificación de la carga de datos para

* Día de la semana (por ejemplo, una Tasa de entrada rápida los martes y los miércoles),
* Hora del día (¿qué porcentaje del día está en el modo de Entrada rápida?)
