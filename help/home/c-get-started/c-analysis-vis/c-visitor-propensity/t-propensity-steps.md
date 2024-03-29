---
description: Siga estos pasos para utilizar la visualización Puntuación de tendencia .
title: Configuración de la puntuación de tendencia
uuid: afc9aada-3bf9-4ce6-8c43-a955771065b4
exl-id: e16a7062-636e-44a9-a07d-343d48bf1b4c
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '536'
ht-degree: 2%

---

# Configuración de la puntuación de tendencia{#setting-up-propensity-scoring}

{{eol}}

Siga estos pasos para utilizar la visualización Puntuación de tendencia .

1. Abra un nuevo espacio de trabajo y haga clic en **[!UICONTROL Add]** > **[!UICONTROL Visualization]** > **[!UICONTROL Predictive Analytics]** > **[!UICONTROL Scoring]** > **[!UICONTROL Propensity Score]**.

   ![](assets/propensity_visualization.png)

1. Configure las variables **[!UICONTROL Target]** (la variable dependiente).

   Configure la variable dependiente seleccionando:

* **elementos del Dimension**: Haga clic con el botón derecho en el espacio de trabajo y seleccione **[!UICONTROL Table]**. A continuación, seleccione un Dimension de elementos como variable dependiente.

   OR

* **[!UICONTROL Filter Editor]**. Haga clic en **[!UICONTROL Add]** > **[!UICONTROL Visualization]** > **[!UICONTROL Filter Editor]** para abrir la visualización Editor de filtros.

   ![](assets/propensity_visualization_filter_editor.png)

   Después de seleccionar un elemento Dimension o Filtrar como variable dependiente, haga clic en **[!UICONTROL Set Target]**, introduzca un nombre para describir la variable dependiente. A continuación, haga clic en **[!UICONTROL OK]** (y asegúrese de que el cuadro de filtro está resaltado) para establecer el objetivo.

   ![](assets/propensity_visualization_setTarget.png)

   El nombre que asigne al destino es la variable dependiente que aparecerá en el panel izquierdo.
1. Agregue variables independientes.

   Agregue las variables independientes mediante Métricas o Elementos de Dimension.

   ![](assets/propensity_visualization_metrics.png)

* **Métricas**. En la barra de herramientas Puntuación de tendencia, seleccione una métrica de la **[!UICONTROL Metrics]** para abrir el Navegador.

* **elementos del Dimension**: Haga clic con el botón derecho en el espacio de trabajo y seleccione **[!UICONTROL Table]**. Seleccione uno o varios elementos de Dimension y arrastre a la columna izquierda debajo de **[!UICONTROL Independent Variables]** o a la **[!UICONTROL Element]** usando la variable `<Ctrl>` + `<Alt>` teclas.

1. Establezca **[!UICONTROL Training Filter]**. Puede definir el conjunto de visitantes que desea puntuar haciendo clic en **[!UICONTROL Options]** > **[!UICONTROL Set Training Filter]** en la barra de herramientas Puntuación de tendencia. Proporcionará un subconjunto de datos creados utilizando únicamente los visitantes que desea puntuar. Por ejemplo, quién visitó en el último mes, los visitantes que residen en Australia o los visitantes que vieron productos específicos.

   El filtro predeterminado es **[!UICONTROL Train on Everyone]**, pero puede cambiarlo activando **[!UICONTROL Dimension Elements]** en una tabla o crear un filtro utilizando la variable **[!UICONTROL Filter Editor]**.

   Después de seleccionar un elemento Dimension o crear un filtro y, mientras está activado, haga clic en **Opciones** > **Definir filtro de formación**, introduzca un nombre para describir el filtro y, a continuación, haga clic en **[!UICONTROL OK]**.
1. Una vez que haya identificado todas sus entradas, presione **[!UICONTROL Go]**.

   ![](assets/propensity_visualization_GO.png)

   El proceso de puntuación empezará pasando los datos varias veces. A continuación, se muestran los resultados como gráficos de barras sobre una línea de porcentaje.
1. Guarde la puntuación de tendencia.

   A partir de la versión 6.1, ahora tiene la opción de usar Guardar puntuación de tendencia:

* Dimensión
* Dimension y métrica

   Puede terminar con dos archivos guardados, una dimensión y una métrica definida.

   >[!NOTE]
   >
   >Si envía la puntuación de tendencia para su procesamiento, solo obtendrá una dimensión.

   La métrica derivada es la métrica de puntuación promedio asociada.
1. Compruebe la precisión.

   Se mostrará el sistema **[!UICONTROL Model Complete]** y generar un modelo de puntuación cuando se complete el proceso.

   Clic con el botón derecho en **[!UICONTROL Model Complete]** identificará la precisión del modelo de puntuación definido por el sistema. Los valores que oscilan entre el 0 y el 100 % identificarán la probabilidad de que los visitantes coincidan con la variable **[!UICONTROL Target]** variable.

   La matriz de confusión ofrece cuatro recuentos por la combinación de Positivo Real (AP), Negativo Real (AN), Predicted Positive (PP) y Predicted Negative (PN). Estos números se obtienen aplicando el modelo de puntuación resultante a los datos de prueba retenidos del 20 % de los cuales conocemos la respuesta verdadera. Si la puntuación es buena al 50 %, se predice como un caso positivo (que coincida con el evento definido).

   ![](assets/propensity_lift_gain_1.png)

<table id="table_154BDD6D294C4ED1B8C15EC33B74B199"> 
 <tbody> 
  <tr> 
   <td colname="col1"><b> Precisión</b> </td> 
   <td colname="col2"> Indica la precisión del modelo identificando las predicciones correctas sobre todas las predicciones. <p>(TP + TN)/(TP + FP + TN + FN) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b> Recordar</b> </td> 
   <td colname="col2"> Identifica la capacidad para volver a identificar el modelo de puntuación. <p><b>TP / (TP + FN)</b> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b> Precisión</b> </td> 
   <td colname="col2">Identifica el nivel de discrepancia. <p>TP / (TP + FP) </p> </td> 
  </tr> 
 </tbody> 
</table>

1. Abra un [Gráfico de alza o ganancia](../../../../home/c-get-started/c-analysis-vis/c-visitor-propensity/c-propensity-gain-lift-chart.md#concept-0d049f6baf534f7fb97f271843ba6c4a)o [Visualizador de modelo](../../../../home/c-get-started/c-analysis-vis/c-visitor-propensity/c-propensity-model-viewer.md#concept-9f2593a8218140b7bd132a4c74e159f9).

   Haga clic con el botón derecho en el **Modelo completado** visualización y seleccionar **[!UICONTROL Lift Chart]**, **[!UICONTROL Gain Chart]** o **[!UICONTROL Model Viewer.]**
