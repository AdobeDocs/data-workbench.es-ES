---
description: El perfil Estado de perfil del área de trabajo de datos proporciona información actual sobre el estado del servidor del área de trabajo de datos en función del perfil en lugar de las métricas del servidor o los datos históricos.
solution: Analytics
title: Espacio de trabajo Estado del perfil del área de trabajo de datos
topic: Data workbench
uuid: b54713c8-863d-4376-8ebf-4a2985e28c76
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Espacio de trabajo Estado del perfil del área de trabajo de datos{#data-workbench-profile-status-workspace}

El perfil Estado de perfil del área de trabajo de datos proporciona información actual sobre el estado del servidor del área de trabajo de datos en función del perfil en lugar de las métricas del servidor o los datos históricos.

## Estado del perfil de Área de trabajo de datos {#section-65d1fa393cfd450cbacef3cba823fcc1}

Este perfil de estado proporciona la información del servidor del área de trabajo de datos que está actualizada, pero no en tiempo real, ya que el agente se sondea cada diez minutos y el informe siempre incluye esta latencia de diez minutos. Más precisamente, los conjuntos de datos generados por este perfil proporcionan la última observación del servidor desde el agente, que generalmente tiene un período de sondeo predeterminado de diez minutos.

Para obtener información de referencia adicional sobre las dimensiones utilizadas en el perfil Estado del perfil del área de trabajo de datos, consulte Perfil de estado del perfil de [Insight](../../../home/monitoring-installation/monitoring-profiles/monitoring-profile-using.md#concept-d4cd7da41c8a42bab4aea25418264e64).

![](assets/Status_General_Status.png)

Este informe es más para monitorear operaciones que para controlar componentes o fluctuaciones de tráfico específicas.

![](assets/Status_General_page.png)

Esto nos da una idea de quién está en qué modo: Si vemos una alta velocidad de entrada rápida para un determinado perfil, ese perfil se encuentra en modo de entrada rápida.

Si la métrica Detenido es 1, el servidor se detiene. Si el valor es 0, el servidor no se detiene.

**Lectura de registros para cargas por lotes grandes**

![](assets/Status_General_stalled_log.png)

