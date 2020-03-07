---
description: Este documento describe los perfiles con sus campos, dimensiones y métricas empleados por el perfil de supervisión del área de trabajo de datos.
solution: Analytics
title: Métricas y dimensiones de perfil del área de trabajo de datos
topic: Data workbench
uuid: 42ef154f-fd8b-4609-8685-96d9dbf32a3d
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Métricas y dimensiones de perfil del área de trabajo de datos{#data-workbench-profile-dimensions-and-metrics}

Este documento describe los perfiles con sus campos, dimensiones y métricas empleados por el perfil de supervisión del área de trabajo de datos.

Para supervisar los servidores del área de trabajo de datos, los datos se recopilan mediante una secuencia de comandos que analiza el estado detallado y, al mismo tiempo, captura información específica del servidor. A continuación, la información del servidor del área de trabajo de datos se pasa a una llamada de etiqueta de página para que el sensor del área de trabajo de datos recopile y guarde en un archivo VSL.

## Perfiles empleados por el perfil de supervisión del área de trabajo de datos {#section-b5b1234f55c3407dae8e68b031b7cd7f}

Estos perfiles proporcionan dimensiones y métricas que le permiten ver datos de rendimiento y estado del servidor:

* [Dimensiones en el perfil de estado del perfil de Insight](../../../home/monitoring-installation/monitoring-appendix/monitoring-profile-status.md#concept-d4cd7da41c8a42bab4aea25418264e64)
* [Dimensiones en el perfil de estado de Insight Server](../../../home/monitoring-installation/monitoring-appendix/monitoring-servers-profile.md#concept-8cbeb91e99bc42e2b52b22d551423f8a)
* [Dimensiones en el perfil histórico de Insight](../../../home/monitoring-installation/monitoring-appendix/monitoring-historical.md#concept-a42837c9c9274f83ad5bc5a6720f02b0)
* [Métricas en el perfil de supervisión histórica de Insight](../../../home/monitoring-installation/monitoring-appendix/monitoring-hist-metrics.md#concept-8fece88b1f014637bbc7c8372ee93203)

Los perfiles de estado permiten ver el rendimiento actual del área de trabajo de datos desde una perspectiva operativa. El perfil Estado **del** perfil y el perfil Estado **del** servidor recopilan datos de los servidores Estado detallado y Área de trabajo de datos. Todos los datos recopilados se colocan en el `cs-uri-query` campo para su uso.

Los perfiles **** históricos le permiten evaluar el impacto de los cambios de configuración y hardware utilizando datos históricos. El perfil histórico puede ser el más útil porque le permite evaluar el impacto de los cambios de configuración y hardware con el paso del tiempo.
