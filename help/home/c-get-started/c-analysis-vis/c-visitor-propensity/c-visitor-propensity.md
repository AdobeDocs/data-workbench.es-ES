---
description: La puntuación de tendencia permite definir a los clientes en función de su posibilidad de realizar una conversión correcta o completar un evento específico. Permite maximizar el impacto potencial de los esfuerzos antes de ejecutar un proceso o dirigir una campaña.
title: Puntuación de tendencia
uuid: 4f7163f5-6fe4-4f87-9e27-71ec8b4717af
exl-id: 832a1e6c-8eeb-4dcc-97e8-9570e1a6eb4f
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '747'
ht-degree: 24%

---

# Puntuación de tendencia{#propensity-scoring}

{{eol}}

La puntuación de tendencia permite definir a los clientes en función de su posibilidad de realizar una conversión correcta o completar un evento específico. Permite maximizar el impacto potencial de los esfuerzos antes de ejecutar un proceso o dirigir una campaña.

## El valor de la puntuación de tendencia  {#section-c51ece66effc42de9b754f0f46027c1b}

La puntuación de tendencia permite realizar descubrimientos de datos para identificar comportamientos o patrones ocultos en los datos. En concreto, la puntuación de tendencia le ayuda a identificar grupos de clientes similares que utilizan medios más específicos y objetivos en lugar de una segmentación o filtrado sencillos. Además, la puntuación de tendencia le permite configurar capacidades predictivas para identificar el comportamiento de los clientes de alto valor de su compañía.

Una vez identificada una audiencia de gran valor, puede motivarla a participar para conseguir el máximo efecto. Por ejemplo, si su empresa es Business to Business, es posible que tenga posibles clientes a los que realizar llamadas comerciales que le permitan puntuar los posibles clientes e identificar la probabilidad de convertir sin conexión. Debido a que cada posible cliente aumenta los costes, crear un incentivo para identificar a los clientes potenciales con la mayor probabilidad de convertir una venta es la manera más efectiva y menos costosa de enfocar sus recursos.

La puntuación de tendencia permite identificar los factores más predictivos de una puntuación determinada o aumentar la probabilidad de que se produzca un evento, pero también se puede aplicar para responder preguntas específicas: ¿El cliente generará una conversión? ¿Responderá el cliente a un correo electrónico? ¿El cliente volverá a comprar? La puntuación de tendencia le permite responder a estas preguntas e identificar visitantes con una inclinación a la acción que luego se puede configurar y puntuar.

Además, puede usar filtros para definir un subconjunto de visitantes que se clasificarán con la variable opcional **[!UICONTROL Training Filter]** función. Si no se aplica ningún filtro, todos los visitantes serán seleccionados para la puntuación.

## Características de la visualización de puntuación de tendencia {#section-28413bc7d33b42c59cecb427c1c5a3fa}

Para abrir la visualización de puntuación de tendencia, haga clic en **[!UICONTROL Add]** > **[!UICONTROL Visualization]** > **[!UICONTROL Predictive Analytics]** > **[!UICONTROL Scoring]** > **[!UICONTROL Propensity Score]**.

![](assets/propensity_visualization_GO.png)

La visualización de puntuación de tendencia incluye las siguientes funciones accesibles desde su barra de herramientas:

| Función de la barra de herramientas | Descripción |
|---|---|
| Ir | Haga clic en para ejecutar el proceso de puntuación después de configurar los parámetros. |
| Restablecer | Borre todos los ajustes de la visualización. |
| Load | Carga un ScoreDim creado anteriormente que le permite cambiar o reconstruir el modelo de puntuación. |
| Guardar | Guarde la visualización Puntuación de tendencia como un archivo atenuado para acceder a él y abrirlo según sea necesario. |
| Submit | Envíe una tarea de puntuación para el procesamiento en el servidor. |
| Opciones | Establezca el Filtro de formación para limitar el subconjunto de visitantes. El filtro predeterminado es **[!UICONTROL Train on Everyone]**, pero puede cambiarlo realizando selecciones de espacio de trabajo o creando un filtro usando la variable **[!UICONTROL Filter Editor]**. |
| Definir Target | Establezca la variable dependiente. |
| Métrica | Agregar métricas como variables independientes. |
| Elementos | Arrastre los elementos del Dimension utilizando la variable `<Ctrl>` + `<Alt>` teclas de las tablas del Dimension. |

**Consulte también**:

* La variable [Gráficos de alza y ganancia](../../../../home/c-get-started/c-analysis-vis/c-visitor-propensity/c-propensity-gain-lift-chart.md#concept-0d049f6baf534f7fb97f271843ba6c4a). Estas vistas se pueden abrir desde un modelo de puntuación completo o desde [!DNL Add Visualization> Predictive Analytics > Scoring.]
* La variable [Visualizador de modelo](../../../../home/c-get-started/c-analysis-vis/c-visitor-propensity/c-propensity-model-viewer.md#concept-d4fdf4b335c04b0ea07e70ab9a7ce9dd). Estas vistas se pueden abrir desde un modelo de puntuación completo o desde [!DNL Add Visualization> Predictive Analytics > Scoring.]
* La variable [Descripción del filtro complejo](../../../../home/c-get-started/c-analysis-vis/c-visitor-propensity/c-propensity-complex-filter.md#concept-f9c55e54837f4b5995a00bc950ce5dff) función.

## Uso de la visualización de puntuación de tendencia {#section-63ced03fa2eb44f2b8a98d61a6c88122}

* **Defina uno o más filtros para definir la población de visitantes con el fin de obtener una puntuación.**. Esta opción es opcional **[!UICONTROL Training Filter]** permite dirigirse a visitantes basándose en criterios seleccionados. Si no se aplica ningún filtro de formación, todos los visitantes serán seleccionados para la puntuación. Si se establece el filtro de formación, el resultado de la puntuación será significativo para la población de visitantes definida, aunque a cada visitante se le dará una puntuación.
* **Identificar a los visitantes positivos**. Definir la variable dependiente para especificar un filtro de destino que identifique a los visitantes positivos que coincidan con el resultado deseado. Puede ser tan sencillo como Ingresos > 10 $ o un filtro mucho más complejo.
* **No se permite que el filtro de Target sea el mismo que el filtro de formación**. Lógicamente, el filtro de destino debe ser una adición al filtro de formación, lo que da como resultado un subconjunto positivo de la población de visitantes que se va a puntuar.
* **Seleccione variables de interés (variables independientes) como entradas para el algoritmo de Puntuación de tendencia**. Pueden ser Métricas o elementos individuales de un Dimension. La puntuación de tendencia empezará a preprocesarse del mismo modo que en [Clúster de visitantes](../../../../home/c-get-started/c-analysis-vis/c-visitor-cluster/c-visitor-cluster.md#concept-1c2406ef7b284a56a02daa38eaa2e73d). El sistema comienza a capturar una cierta cantidad de muestras que coinciden con la definición del filtro de formación establecido anteriormente (si las hay). Actualmente, el tamaño de la muestra se establece en el 10 % de la población de puntuación (definido por el filtro de formación), con un mínimo de 20 000 y un máximo de 100 000, y está enlazado al tamaño de la población de puntuación.

* Un Dimension de puntuación tiene elementos que van del 0 % al 100 % y que determinan la probabilidad de que los visitantes coincidan con la variable de Target.
