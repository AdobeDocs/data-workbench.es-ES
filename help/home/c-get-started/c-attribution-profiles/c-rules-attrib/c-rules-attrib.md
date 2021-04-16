---
description: Con el nuevo perfil de atribución basado en reglas en Data Workbench, puede analizar rápidamente los eventos de atribución y asignar responsabilidad que conduzcan a una conversión correcta definida por usted. El perfil de atribución viene completo con la información necesaria para que su arquitecto de datos configure y amplíe sus funciones, e incluye espacios de trabajo creados previamente para que su analista pueda entrar y comenzar a analizar.
title: Perfil de atribución
uuid: 500e9e86-cffc-4f0d-a397-6521b493bf9a
exl-id: 29946f22-1d39-44ca-9474-13dbe228751c
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '465'
ht-degree: 0%

---

# Perfil de atribución{#attribution-profile}

Con el nuevo perfil de atribución basado en reglas en Data Workbench, puede analizar rápidamente los eventos de atribución y asignar responsabilidad que conduzcan a una conversión correcta definida por usted. El perfil de atribución viene completo con la información necesaria para que su arquitecto de datos configure y amplíe sus funciones, e incluye espacios de trabajo creados previamente para que su analista pueda entrar y comenzar a analizar.

El perfil de atribución permite obtener una nueva perspectiva sobre las relaciones entre los esfuerzos de marketing y una generación de posibles clientes o conversión de ventas exitosa. El perfil de atribución ayuda a calificar las interacciones que deben recibir la asignación de crédito para obtener ingresos reales o participación descendente en el recorrido del cliente. Ayuda a identificar el impacto de sus esfuerzos y costes de marketing, ya que le permite analizar rápidamente los eventos de atribución y, a continuación, asignar responsabilidad por los primeros o últimos toques u otros eventos que conduzcan a una venta correcta.

<!-- <a id="section_648A288E4CA84D579884BC161085C4D5"></a> -->

>[!IMPORTANT]
>
>El perfil de atribución está configurado para su uso inmediato por parte de los usuarios que hayan implementado el perfil SC de Adobe que utiliza la fuente de datos de Analytics (SC/Insight). De forma predeterminada, los eventos de marketing y conversión se emplean como tipos predeterminados de interacciones evaluadas en los modelos basados en reglas proporcionados.

Consulte [Implementación del perfil de atribución](../../../../home/c-get-started/c-attribution-profiles/c-rules-attrib/c-attrib-profile-deploy.md#concept-fbcb5800cd6a40cc901e61f3882988c0) y [Modelos de atribución](../../../../home/c-get-started/c-attribution-profiles/c-rules-attrib/c-attrib-models.md#concept-e209c7e86a5c4008ad6d78fdf4ea032d) para obtener más información.

## Espacios de trabajo de arquitectura y analistas {#section-27c6aff70ba147cca6e11451e127afb4}

Dentro del perfil de atribución, tiene espacios de trabajo de Arquitecto y Analista definidos en pestañas independientes en el área de trabajo.

![](assets/attribution_profile_tabs.png)

**Espacios de trabajo de arquitectura**

En la pestaña **Attribution**, haga clic en la pestaña **[!UICONTROL Architect Workspace]** para abrir espacios de trabajo específicamente diseñados para configurar los archivos de configuración para el modelado de atribución básico.

![](assets/attribution_profile_arch.png)

La pestaña Arquitectura incluye espacios de trabajo para recorrer cada uno de los archivos de configuración de la carpeta del conjunto de datos de perfil. Por ejemplo, **[!UICONTROL Attribution Configuration - Step 1]** permite identificar los valores de atribución dentro de la sección Transformation del archivo [!DNL profile.cfg].

![](assets/attribution_profile_arch_step1.png)

**Espacios de** trabajo de analistaHaga clic en la  **[!UICONTROL Analyst]** **[!UICONTROL Workspaces]** pestaña para abrir el análisis creado previamente de espacios de trabajo utilizando las dimensiones y métricas proporcionadas con el perfil de atribución.

Estos espacios de trabajo están organizados en cuatro categorías:

1. **Los** informes básicos representan un modelo único dentro de un espacio de trabajo.
1. **Los** informes comparativos ampliaron los análisis presentando varios modelos dentro de una sola vista.
1. **Informes de investigación** crea plantillas de informes para presentar los modelos de atribución en diferentes formatos. En esta sección también se presentan y exponen los coeficientes de ponderación basados en posiciones.
1. **Los** informes de rutas proporcionan visibilidad del recorrido de marketing del cliente con varias visualizaciones de rutas para explorar y expresar completamente los flujos de procesos y las rutas de interacción

![](assets/attribution_profile_analyst.png)

La pestaña Analista incluye espacios de trabajo preconfigurados con informes. Por ejemplo, **[!UICONTROL First Attribution]** permite seleccionar entre la tabla **[!UICONTROL Campaign]** para ver la atribución **[!UICONTROL Revenue]** basada en **[!UICONTROL Time]**.

![](assets/attribution_profile_analyst_step1.png)
