---
description: Este documento describe los perfiles con sus campos, dimensiones y métricas empleados por el perfil de supervisión de Data Workbench.
title: Métricas y dimensiones del perfil de Data Workbench
uuid: 42ef154f-fd8b-4609-8685-96d9dbf32a3d
exl-id: cfad9897-2ea3-47e4-aa36-416e0fde9358
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '233'
ht-degree: 5%

---

# Métricas y dimensiones del perfil de Data Workbench{#data-workbench-profile-dimensions-and-metrics}

{{eol}}

Este documento describe los perfiles con sus campos, dimensiones y métricas empleados por el perfil de supervisión de Data Workbench.

Para monitorizar los servidores de Data Workbench, los datos se recopilan con una secuencia de comandos que analiza el estado detallado y captura a la vez información específica del servidor. A continuación, la información del servidor de Data Workbench se pasa a una llamada de etiqueta de página para que el sensor de Data Workbench recopile y guarde en un archivo VSL.

## Perfiles empleados por el perfil de monitorización de Data Workbench {#section-b5b1234f55c3407dae8e68b031b7cd7f}

Estos perfiles proporcionan dimensiones y métricas que le permiten ver datos de rendimiento y estado del servidor:

* [Dimension en el perfil de estado del perfil de Insight](../../../home/monitoring-installation/monitoring-appendix/monitoring-profile-status.md#concept-d4cd7da41c8a42bab4aea25418264e64)
* [Dimension en el perfil de estado de Insight Server](../../../home/monitoring-installation/monitoring-appendix/monitoring-servers-profile.md#concept-8cbeb91e99bc42e2b52b22d551423f8a)
* [Dimension en el perfil de Insight Historic](../../../home/monitoring-installation/monitoring-appendix/monitoring-historical.md#concept-a42837c9c9274f83ad5bc5a6720f02b0)
* [Métricas en el perfil de monitorización histórica de Insight](../../../home/monitoring-installation/monitoring-appendix/monitoring-hist-metrics.md#concept-8fece88b1f014637bbc7c8372ee93203)

Los perfiles de estado le permiten ver el rendimiento actual de Data Workbench desde una perspectiva operativa. La variable **Estado del perfil** y **Estado del servidor** recopilar datos de perfiles de los servidores Estado detallado y Data Workbench. Todos los datos recopilados se colocan en la variable `cs-uri-query` para usar.

La variable **Perfiles históricos** permite evaluar el impacto de los cambios de configuración y hardware utilizando datos históricos. El perfil histórico puede ser el más útil porque le permite evaluar el impacto de los cambios de configuración y hardware a lo largo del tiempo.
