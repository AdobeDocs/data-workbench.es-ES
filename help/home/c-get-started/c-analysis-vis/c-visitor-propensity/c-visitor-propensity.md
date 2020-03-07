---
description: La puntuación de tendencia permite definir a los clientes en función de su posibilidad de realizar una conversión exitosa o completar un evento específico. Permite maximizar el impacto potencial de los esfuerzos antes de ejecutar un proceso o dirigir una campaña.
solution: Analytics
title: Puntuación de tendencia
topic: Data workbench
uuid: 4f7163f5-6fe4-4f87-9e27-71ec8b4717af
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Puntuación de tendencia{#propensity-scoring}

La puntuación de tendencia permite definir a los clientes en función de su posibilidad de realizar una conversión exitosa o completar un evento específico. Permite maximizar el impacto potencial de los esfuerzos antes de ejecutar un proceso o dirigir una campaña.

## El valor de la puntuación de tendencia {#section-c51ece66effc42de9b754f0f46027c1b}

La puntuación de tendencia permite realizar la detección de datos para identificar comportamientos o patrones ocultos que existen en los datos. En concreto, la puntuación de tendencia le ayuda a identificar grupos de clientes similares que utilizan medios más específicos y objetivos en lugar de una segmentación o filtrado sencillos. Además, la puntuación de tendencia le permite crear funciones de predicción para identificar el comportamiento de clientes de gran valor para su empresa.

Una vez identificado el público de gran valor, puede motivarlo a participar para conseguir el máximo efecto. Por ejemplo: si usted es una empresa de empresa a empresa, es posible que tenga leads de llamada de ventas que le permitan puntuar los posibles clientes e identificar su probabilidad de convertirse sin conexión. Dado que todos los posibles clientes generan un aumento de costes, crear un incentivo para identificar a los clientes potenciales que muestran la mayor probabilidad de convertir una venta es la forma más eficaz y económica de concentrar sus recursos.

La puntuación de tendencia permite identificar los factores más importantes a la hora de predecir una puntuación concreta o aumentar la probabilidad de que se produzca un evento, pero también se puede aplicar para responder a preguntas específicas: ¿El cliente va a realizar una conversión? ¿El cliente va a responder a un correo electrónico? ¿El cliente va a volver a comprar? La puntuación de tendencia le permite responder a estas preguntas e identificar a aquellos visitantes que muestren una inclinación a realizar una acción que posteriormente se podrá elaborar y puntuar.

Además, puede utilizar filtros para definir un subconjunto de visitantes que se van a puntuar mediante la función opcional **[!UICONTROL Training Filter]** . Si no se aplica ningún filtro, todos los visitantes serán el objetivo de la puntuación.

## Características de la visualización de Puntuación de tendencia {#section-28413bc7d33b42c59cecb427c1c5a3fa}

Para abrir la Visualización de puntuación de tendencia, haga clic en **[!UICONTROL Add]** > **[!UICONTROL Visualization]** > **[!UICONTROL Predictive Analytics]** > **[!UICONTROL Scoring]** > **[!UICONTROL Propensity Score]**.

![](assets/propensity_visualization_GO.png)

La visualización de puntuación de tendencia incluye estas funciones accesibles desde su barra de herramientas:

| Función de barra de herramientas | Descripción |
|---|---|
| Ir | Haga clic para ejecutar el proceso de puntuación después de configurar los parámetros. |
| Reset | Borre todos los ajustes de la visualización. |
| Load | Carga un ScoreDim creado anteriormente que le permite cambiar o reconstruir el modelo de puntuación. |
| Guardar | Guarde la visualización de puntuación de tendencia como un archivo Dim para acceder a él y abrirlo según sea necesario. |
| Enviar | Enviar tarea de puntuación para el procesamiento en el servidor. |
| Opciones | Configure el Filtro de formación para limitar el subconjunto de visitantes. El filtro predeterminado es **[!UICONTROL Train on Everyone]** pero puede cambiarlo haciendo selecciones en el espacio de trabajo o creando un filtro con el **[!UICONTROL Filter Editor]**. |
| Definir objetivo | Establezca la variable dependiente. |
| Métrica | Agregar métricas como variables independientes. |
| Elementos | Arrastre los elementos de dimensión utilizando las teclas `<Ctrl>` + `<Alt>` de las tablas de dimensión. |

**Consulte también**:

* Gráficos [Ganancia y Alza](../../../../home/c-get-started/c-analysis-vis/c-visitor-propensity/c-propensity-gain-lift-chart.md#concept-0d049f6baf534f7fb97f271843ba6c4a). Estas vistas se pueden abrir desde un modelo de puntuación completo o desde [!DNL Add Visualization> Predictive Analytics > Scoring.]
* Visor [de modelos](../../../../home/c-get-started/c-analysis-vis/c-visitor-propensity/c-propensity-model-viewer.md#concept-d4fdf4b335c04b0ea07e70ab9a7ce9dd). Estas vistas se pueden abrir desde un modelo de puntuación completo o desde [!DNL Add Visualization> Predictive Analytics > Scoring.]
* La función Descripción [del filtro](../../../../home/c-get-started/c-analysis-vis/c-visitor-propensity/c-propensity-complex-filter.md#concept-f9c55e54837f4b5995a00bc950ce5dff) complejo.

## Uso de la visualización de puntuación de tendencia {#section-63ced03fa2eb44f2b8a98d61a6c88122}

* **Defina uno o varios filtros para definir la población de visitantes para la puntuación**. Esta opción **[!UICONTROL Training Filter]** le permite dirigirse a los visitantes en función de los criterios seleccionados. Si no se aplica ningún filtro de formación, todos los visitantes serán el objetivo de la puntuación. Si se establece el filtro de formación, el resultado de la puntuación es significativo para la población de visitantes definida, aunque a cada visitante se le asignará una puntuación.
* **Identifique a los visitantes** positivos. Definir la variable dependiente para especificar un filtro de objetivo que identifique a los visitantes positivos que coincidan con el resultado deseado. Esto puede ser tan sencillo como Ingresos > 10 $ o un filtro mucho más complejo.
* **El filtro de Target no puede ser el mismo que el filtro** de formación. Lógicamente, el filtro de destino debe ser una adición al filtro de formación, lo que resulta en un subconjunto positivo de la población de visitantes que se va a puntuar.
* **Seleccione variables de interés (variables independientes) como entradas para el algoritmo** de Puntuación de tendencia. Pueden ser Métricas o elementos individuales de una dimensión. La Puntuación de tendencia empezará a preprocesarse como en el agrupamiento de [visitantes](../../../../home/c-get-started/c-analysis-vis/c-visitor-cluster/c-visitor-cluster.md#concept-1c2406ef7b284a56a02daa38eaa2e73d). El sistema comienza a capturar una cierta cantidad de muestras que coinciden con la definición del filtro de formación establecido anteriormente (si existe). Actualmente, el tamaño de la muestra se establece en el 10 % de la población de puntuación (definida por el filtro de formación), con un mínimo de 20.000 y un máximo de 100.000, y se limita al tamaño de la población de puntuación.

* Una dimensión de puntuación tiene elementos que van del 0 % al 100 % y que determinan la probabilidad de que los visitantes coincidan con la variable de Target.

