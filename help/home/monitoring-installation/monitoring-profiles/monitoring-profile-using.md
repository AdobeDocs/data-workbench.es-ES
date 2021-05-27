---
description: El perfil de estado del perfil de Data Workbench proporciona información actual sobre el estado del servidor de Data Workbench en función del perfil, no de las métricas del servidor o los datos históricos.
title: Espacio de trabajo del estado del perfil de Data Workbench
uuid: b54713c8-863d-4376-8ebf-4a2985e28c76
exl-id: 40b9b0bf-4fd9-48d8-875b-514921c520cd
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '217'
ht-degree: 4%

---

# Espacio de trabajo del estado del perfil de Data Workbench{#data-workbench-profile-status-workspace}

El perfil de estado del perfil de Data Workbench proporciona información actual sobre el estado del servidor de Data Workbench en función del perfil, no de las métricas del servidor o los datos históricos.

## Estado del perfil de Data Workbench {#section-65d1fa393cfd450cbacef3cba823fcc1}

Este perfil de estado proporciona la información del servidor de Data Workbench que está actualizada, pero no en tiempo real, ya que se sondea el agente cada diez minutos y el sistema de informes siempre incluye esta latencia de diez minutos. Más precisamente, los conjuntos de datos generados por este perfil proporcionan la observación más reciente del servidor desde el agente, que generalmente tiene un periodo de sondeo predeterminado de diez minutos.

Para obtener información de referencia adicional sobre las dimensiones utilizadas en el perfil de estado del perfil de Data Workbench, consulte [Perfil de estado del perfil de Insight](../../../home/monitoring-installation/monitoring-profiles/monitoring-profile-using.md#concept-d4cd7da41c8a42bab4aea25418264e64).

![](assets/Status_General_Status.png)

Este informe es más para las operaciones de monitoreo que para los componentes o las fluctuaciones específicas del tráfico.

![](assets/Status_General_page.png)

Esto nos da una idea de quién está en qué modo: Si vemos una alta velocidad de entrada rápida para un perfil determinado, ese perfil está en modo de entrada rápida.

Si la métrica Parada es 1, el servidor se paraliza. Si el valor es 0, el servidor no se detiene.

**Lectura de registros para cargas por lotes grandes**

![](assets/Status_General_stalled_log.png)
