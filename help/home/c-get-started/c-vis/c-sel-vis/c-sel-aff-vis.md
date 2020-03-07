---
description: Dentro de un espacio de trabajo, una visualización representa un conjunto de resultados de consulta.
solution: Analytics
title: Explicación de cómo una selección afecta a otras visualizaciones
topic: Data workbench
uuid: d46f4e8d-df6f-4a7f-a796-eb9f11536ae5
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Explicación de cómo una selección afecta a otras visualizaciones{#understanding-how-a-selection-affects-other-visualizations}

Dentro de un espacio de trabajo, una visualización representa un conjunto de resultados de consulta.

Al realizar una selección, Área de trabajo de datos filtra los resultados de las consultas que utiliza para producir las visualizaciones en el espacio de trabajo. El filtro específico varía según la visualización.

Los siguientes ejemplos ilustran cómo Área de trabajo de datos aplica una selección a tres tipos diferentes de visualizaciones. La revisión de estos ejemplos ayuda a comprender el efecto de filtrado que las selecciones tienen en las visualizaciones. También ayudan a entender cómo interpretar los resultados que se ven en una visualización filtrada.

* [Filtrado de una visualización con una métrica de sesiones](../../../../home/c-get-started/c-vis/c-sel-vis/c-sel-aff-vis.md#section-7cc06493ecb34cd4a696dbf0f0a7aaef)
* [Filtrado de una visualización con una métrica de visitantes](../../../../home/c-get-started/c-vis/c-sel-vis/c-sel-aff-vis.md#section-97d38c7f03e8457189a9c72d69514ed2)
* [Filtrado de una visualización con una métrica de visitantes por sesión](../../../../home/c-get-started/c-vis/c-sel-vis/c-sel-aff-vis.md#section-f746182311d648dcb98716b0fe846e25)

## Filtrado de una visualización con una métrica de sesiones {#section-7cc06493ecb34cd4a696dbf0f0a7aaef}

En este ejemplo, el [!DNL /direct.asp/?ldPage=hme] URI de la visualización de la izquierda está filtrando la métrica de Sesiones que se muestra en la visualización de la derecha.

![](assets/client-vis1.png)

* **Efecto de la selección en la consulta:** Área de trabajo de datos filtra las sesiones para el URI seleccionado. En este ejemplo, la consulta que genera el valor para el [!DNL /pops/disclosure_pop.asp] elemento se filtra de la siguiente manera:

   ```
   Sessions[ URI="/pops/disclosure_pop.asp" AND URI="/direct.asp
   /?ldPage=hme"] by Page View by Session
   ```

* **Interpretación de la visualización:** La visualización filtrada representa el número de sesiones que incluyen los URI enumerados en la visualización y [!DNL /direct.asp/?ldPage=hme]. Este ejemplo muestra que hubo 1.113 sesiones durante las cuales los visitantes vieron tanto [!DNL /pops/disclosure_pop.asp] la página como [!DNL /direct.asp/?ldPage=hme] en la misma sesión.

## Filtrado de una visualización con una métrica de visitantes {#section-97d38c7f03e8457189a9c72d69514ed2}

En este ejemplo, el [!DNL /direct.asp/?ldPage=home] URI de la visualización de la izquierda está filtrando la métrica de Visitantes en la visualización de la derecha.

![](assets/client-vis2.png)

* **Efecto de la selección en la consulta:** Área de trabajo de datos filtra los visitantes para el URI seleccionado. En este ejemplo, la consulta que genera el valor del [!DNL /pops/disclosure_pop.asp] URI se filtra de la siguiente manera:

   ```
   Visitors[ URI="/pops/disclosure_pop.asp" by Page View by Visitor 
     AND URI="/direct.asp/?ldPage=hme" by Page View by Visitor ]
   ```

* **Interpretación de la visualización:** La visualización filtrada ilustra los visitantes que han visto los URI enumerados en la visualización y [!DNL /direct.asp/?ldPage=hme] (aunque no necesariamente durante la misma sesión). El ejemplo anterior muestra que 2.041 visitantes han visto [!DNL /pops/disclosure_pop.asp] y [!DNL /direct.asp/?ldPage=hme].

## Filtrado de una visualización con una métrica de visitantes por sesión {#section-f746182311d648dcb98716b0fe846e25}

En este ejemplo, el [!DNL /direct.asp/?ldPage=hme] URI de la visualización de la izquierda está filtrando la métrica visitante por sesión en la visualización de la derecha.

![](assets/client-vis3.png)

* **Efecto de la selección en la consulta:** Área de trabajo de datos filtra los visitantes por sesión para el URI seleccionado. Por ejemplo, la consulta que genera el valor para el [!DNL /pops/disclosure_pop.asp] URI se filtra de la siguiente manera:

   ```
   Visitors[ ( URI="/pops/disclosure_pop.asp" by Page View 
     AND URI="/direct.asp/?ldPage=hme" by Page View ) by Session ]
   ```

* **Interpretación de la visualización:** La visualización filtrada ilustra los visitantes que han visualizado ambos URI enumerados en la visualización y [!DNL /direct.asp/?ldPage=hme] durante la misma sesión. Este ejemplo muestra que 1069 visitantes vieron [!DNL /pops/disclosure_pop.asp] y [!DNL /direct.asp/?ldPage=hme] durante una sola sesión.

