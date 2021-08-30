---
description: El gráfico de barras en la Data Workbench ahora incluye una comparación de regresión para varias métricas en varios gráficos.
title: Gráfico de análisis de regresión
uuid: 8512890e-f42b-4dce-826a-2b4bf2a215f4
exl-id: bfc76c4a-edd5-41fe-b875-c199ea3beab5
source-git-commit: 232117a8cacaecf8e5d7fcaccc5290d6297947e5
workflow-type: tm+mt
source-wordcount: '272'
ht-degree: 2%

---

# Gráfico de análisis de regresión{#regression-analysis-graph}

El gráfico de barras en la Data Workbench ahora incluye una comparación de regresión para varias métricas en varios gráficos.

[Las ](https://experienceleague.adobe.com/docs/data-workbench/using/client/analysis-visualizations/graphs/c-graphs.html) gráficas de barras en la Data Workbench permiten retroceder las métricas de un gráfico a las métricas de otro gráfico. Si tiene varios gráficos, puede comparar una métrica (como variable independiente) con un gráfico que evalúe otras métricas (como variables dependientes). Esto permite determinar la solidez de la relación entre una variable dependiente (la métrica establecida primero) y una serie de otras métricas cambiantes (regresiones con la métrica dependiente establecida).

El análisis de regresión en una visualización de gráfico permite a los analistas realizar escenarios de &quot;qué pasaría si&quot;. Por ejemplo, si las visitas aumentan a este nivel, ¿qué impacto tendrá este aumento en los ingresos?

**Configuración del análisis de regresión**

1. Seleccione el gráfico como métrica dependiente para una comparación de regresión.

   Haga clic con el botón derecho en el gráfico y seleccione **Establecer como métrica base para la regresión**.

   ![](assets/c_graph_regression_1.png)

1. Defina otros gráficos de métricas como variables independientes.

   Haga clic con el botón derecho en la métrica y seleccione **[!UICONTROL Regress with `<base metric name>`]** para otras métricas.

   ![](assets/c_graph_regression.png)

1. Ver la regresión haciendo clic con el botón derecho en el gráfico para subir y bajar la barra.

   Si hace clic con el botón derecho en el gráfico de un valor específico, puede ver las tasas de regresión de cada métrica en función de los valores hacia arriba o hacia abajo.

   ![](assets/c_graph_regression_2.png)

   Por ejemplo, si mis vistas de página disminuyen a 86 041, las demás métricas tendrán estos valores: Visitas a 12.183 y Visitantes por visita a 12.028.

   ![](assets/c_graph_regression_3.png)

   Si los valores de Visitantes por Visitas aumentan a 26.141, las demás métricas serán Visitas a 26.560 y Vistas de página a 189.091.
