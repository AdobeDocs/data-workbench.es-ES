---
description: Con el nuevo perfil de atribución basado en reglas en el área de trabajo de datos, puede analizar rápidamente los eventos de atribución y asignar responsabilidades que conducen a una conversión correcta definida por usted. El perfil de atribución incluye toda la información necesaria para que el arquitecto de datos configure y amplíe sus funciones, e incluye espacios de trabajo pregenerados para que el analista pueda entrar y empezar a analizar.
solution: Analytics
title: Perfil de atribución
topic: Data workbench
uuid: 500e9e86-cffc-4f0d-a397-6521b493bf9a
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Attribution Profile{#attribution-profile}

Con el nuevo perfil de atribución basado en reglas en el área de trabajo de datos, puede analizar rápidamente los eventos de atribución y asignar responsabilidades que conducen a una conversión correcta definida por usted. El perfil de atribución incluye toda la información necesaria para que el arquitecto de datos configure y amplíe sus funciones, e incluye espacios de trabajo pregenerados para que el analista pueda entrar y empezar a analizar.

El perfil de atribución le permite obtener una nueva perspectiva sobre las relaciones entre sus esfuerzos de mercadotecnia y una generación exitosa de posibles clientes o conversión de ventas. El perfil de atribución ayuda a calificar las interacciones que deben recibir la asignación de crédito por los ingresos realizados o la participación en la fase posterior del viaje del cliente. Ayuda a identificar el impacto de los esfuerzos y los costos de mercadotecnia permitiéndole analizar rápidamente los eventos de atribución y, a continuación, asignar responsabilidad por los primeros o últimos toques u otros eventos que conducen a una venta exitosa.

<!-- <a id="section_648A288E4CA84D579884BC161085C4D5"></a> -->

>[!IMPORTANT]
>
>El perfil de atribución está configurado para su uso inmediato por los usuarios que han implementado el perfil de Adobe SC que utiliza la fuente de datos de Analytics (SC/Insight). De forma predeterminada, los eventos de marketing y conversión se emplean como los tipos predeterminados de interacciones evaluadas en los modelos basados en reglas proporcionados.

Consulte [Implementación de modelos](../../../../home/c-get-started/c-attribution-profiles/c-rules-attrib/c-attrib-profile-deploy.md#concept-fbcb5800cd6a40cc901e61f3882988c0) de atribución y [atribución](../../../../home/c-get-started/c-attribution-profiles/c-rules-attrib/c-attrib-models.md#concept-e209c7e86a5c4008ad6d78fdf4ea032d) para obtener información adicional.

## Espacios de trabajo de arquitectura y analistas {#section-27c6aff70ba147cca6e11451e127afb4}

Dentro del perfil de atribución, tiene espacios de trabajo de Arquitecto y Analista definidos en fichas independientes del área de trabajo.

![](assets/attribution_profile_tabs.png)

**Espacios de trabajo de arquitectura**

En la ficha **Atribución** , haga clic en la **[!UICONTROL Architect Workspace]** ficha para abrir espacios de trabajo diseñados específicamente para configurar los archivos de configuración para el modelado de atribución básico.

![](assets/attribution_profile_arch.png)

La ficha Arquitectura incluye espacios de trabajo para recorrer cada uno de los archivos de configuración de la carpeta de conjuntos de datos de perfil. Por ejemplo, **[!UICONTROL Attribution Configuration - Step 1]** permite identificar los valores de atribución dentro de la sección Transformación del [!DNL profile.cfg] archivo.

![](assets/attribution_profile_arch_step1.png)

**Espacios de trabajo** de analistas Haga clic en la **[!UICONTROL Analyst]** ficha **[!UICONTROL Workspaces]** para abrir el análisis pregenerado de espacios de trabajo utilizando las dimensiones y métricas proporcionadas con el perfil de atribución.

Estos espacios de trabajo están organizados en cuatro categorías:

1. **Los informes** básicos exponen un solo modelo dentro de un espacio de trabajo.
1. **Los informes** comparativos ampliaron los análisis presentando varios modelos en una sola vista.
1. **Informes** de investigación expande las plantillas de informes para presentar los modelos de atribución en diferentes formatos. En esta sección también se introducen y exponen las tasas de ponderación basadas en posiciones.
1. **Los informes** de rutas proporcionan visibilidad sobre el viaje de mercadotecnia del cliente con varias visualizaciones de rutas para explorar y expresar completamente los flujos de procesos y las rutas de interacción

![](assets/attribution_profile_analyst.png)

La ficha Analista incluye espacios de trabajo preconfigurados con informes. Por ejemplo, **[!UICONTROL First Attribution]** le permite seleccionar en la **[!UICONTROL Campaign]** tabla para ver la **[!UICONTROL Revenue]** atribución basada en **[!UICONTROL Time]**.

![](assets/attribution_profile_analyst_step1.png)

