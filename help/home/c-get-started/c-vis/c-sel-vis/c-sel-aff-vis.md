---
description: Dentro de un espacio de trabajo, una visualización representa un conjunto de resultados de consulta.
title: Explicación de cómo una selección afecta a otras visualizaciones
uuid: d46f4e8d-df6f-4a7f-a796-eb9f11536ae5
exl-id: 7756646b-9309-41aa-a098-8988f6c065c8
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '427'
ht-degree: 3%

---

# Explicación de cómo una selección afecta a otras visualizaciones{#understanding-how-a-selection-affects-other-visualizations}

Dentro de un espacio de trabajo, una visualización representa un conjunto de resultados de consulta.

Al realizar una selección, la Data Workbench filtra los resultados de las consultas que utiliza para producir las visualizaciones en el espacio de trabajo. El filtro específico varía según la visualización.

Los siguientes ejemplos ilustran cómo la Data Workbench aplica una selección a tres tipos diferentes de visualizaciones. La revisión de estos ejemplos le ayuda a comprender el efecto de filtrado que tienen las selecciones en las visualizaciones. También le ayudan a comprender cómo interpretar los resultados que ve en una visualización filtrada.

* [Filtrado de una visualización con una métrica de sesiones](../../../../home/c-get-started/c-vis/c-sel-vis/c-sel-aff-vis.md#section-7cc06493ecb34cd4a696dbf0f0a7aaef)
* [Filtrado de una visualización con una métrica de visitantes](../../../../home/c-get-started/c-vis/c-sel-vis/c-sel-aff-vis.md#section-97d38c7f03e8457189a9c72d69514ed2)
* [Filtrado de una visualización con una métrica Visitantes por sesión](../../../../home/c-get-started/c-vis/c-sel-vis/c-sel-aff-vis.md#section-f746182311d648dcb98716b0fe846e25)

## Filtrado de una visualización con una métrica de sesiones {#section-7cc06493ecb34cd4a696dbf0f0a7aaef}

En este ejemplo, el URI [!DNL /direct.asp/?ldPage=hme] de la visualización de la izquierda está filtrando la métrica para Sesiones mostradas en la visualización de la derecha.

![](assets/client-vis1.png)

* **Efecto de la selección en la consulta:**  la Data Workbench filtra las sesiones para el URI seleccionado. En este ejemplo, la consulta que genera el valor para el elemento [!DNL /pops/disclosure_pop.asp] se filtra de la siguiente manera:

   ```
   Sessions[ URI="/pops/disclosure_pop.asp" AND URI="/direct.asp
   /?ldPage=hme"] by Page View by Session
   ```

* **Interpretación de la visualización:** la visualización filtrada representa el número de sesiones que incluyen los URI enumerados en la visualización y  [!DNL /direct.asp/?ldPage=hme]. Este ejemplo muestra que hubo 113 sesiones durante las cuales los visitantes vieron la página [!DNL /pops/disclosure_pop.asp] y [!DNL /direct.asp/?ldPage=hme] en la misma sesión.

## Filtrado de una visualización con una métrica de visitantes {#section-97d38c7f03e8457189a9c72d69514ed2}

En este ejemplo, el URI [!DNL /direct.asp/?ldPage=home] de la visualización de la izquierda está filtrando la métrica para Visitantes en la visualización de la derecha.

![](assets/client-vis2.png)

* **Efecto de la selección en la consulta:** la Data Workbench filtra los visitantes para el URI seleccionado. En este ejemplo, la consulta que genera el valor para el URI [!DNL /pops/disclosure_pop.asp] se filtra de la siguiente manera:

   ```
   Visitors[ URI="/pops/disclosure_pop.asp" by Page View by Visitor 
     AND URI="/direct.asp/?ldPage=hme" by Page View by Visitor ]
   ```

* **Interpretación de la visualización:** la visualización filtrada representa los visitantes que han visto los URI enumerados en la visualización y  [!DNL /direct.asp/?ldPage=hme] (aunque no necesariamente durante la misma sesión). El ejemplo anterior muestra que 2041 visitantes han visto [!DNL /pops/disclosure_pop.asp] y [!DNL /direct.asp/?ldPage=hme].

## Filtrado de una visualización con una métrica Visitantes por sesión {#section-f746182311d648dcb98716b0fe846e25}

En este ejemplo, el URI [!DNL /direct.asp/?ldPage=hme] de la visualización de la izquierda está filtrando la métrica visitante por sesión en la visualización de la derecha.

![](assets/client-vis3.png)

* **Efecto de la selección en la consulta:** la Data Workbench filtra los visitantes por sesión para el URI seleccionado. Por ejemplo, la consulta que genera el valor para el URI [!DNL /pops/disclosure_pop.asp] se filtra de la siguiente manera:

   ```
   Visitors[ ( URI="/pops/disclosure_pop.asp" by Page View 
     AND URI="/direct.asp/?ldPage=hme" by Page View ) by Session ]
   ```

* **Interpretación de la visualización:** la visualización filtrada representa los visitantes que han visto ambas URI enumeradas en la visualización y  [!DNL /direct.asp/?ldPage=hme] durante la misma sesión. Este ejemplo muestra que 1069 visitantes vieron [!DNL /pops/disclosure_pop.asp] y [!DNL /direct.asp/?ldPage=hme] durante una sola sesión.
