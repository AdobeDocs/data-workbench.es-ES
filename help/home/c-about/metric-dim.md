---
description: Cree dimensiones definidas por atributos de métrica (dimensiones de métricas) mediante un asistente paso a paso. A continuación, pruebe, previsualice y guarde la nueva atenuación de métricas en la lista Dimensiones.
title: Asistente para atenuación de métricas
uuid: 411b2e28-0958-43bb-a853-7de7b3063818
translation-type: tm+mt
source-git-commit: d892186621e7acb9504254496b038efc3e9fd8ec

---


# Asistente para atenuación de métricas{#metric-dim-wizard}

Cree dimensiones definidas por atributos de métrica (dimensiones de métricas) mediante un asistente paso a paso. A continuación, pruebe, previsualice y guarde la nueva atenuación de métricas en la lista Dimensiones.

Una métrica Dim convierte una métrica en una nueva dimensión. Por ejemplo: una métrica Dim basada en una métrica de Vistas de página y nivel de Visitante mostrará los elementos de dimensión según el total de Vistas de página de cada Visitante. Le permite ampliar una métrica definida actualmente en función de los elementos de dimensión para crear y guardar como una nueva dimensión.

## Paso 1: Seleccionar dimensión y métrica {#section-58b6ea7bbba5487ba1a3c264aa3dcb95}

1. Abra el Asistente para atenuación de métricas.

   En un espacio de trabajo, haga clic con el botón derecho y seleccione Herramientas **[de]** UICONTROL > **[UICONTROL Crear atenuación]** de métrica.

1. Asigne un nombre a la dimensión de métrica.

   De forma predeterminada, el campo Nombre se rellenará automáticamente en función de las selecciones Nivel y Métrica.

1. Seleccione un nivel de dimensión.

   El nivel de dimensión es la dimensión principal que contiene todos los valores de elemento constituyente para filtrar la entrada y definir un tipo de dimensión.

   Los niveles de dimensión incluyen:

   * Pulsaciones
   * Visita individual
   * Product
   * Visita
   * Visitante

1. Seleccione una métrica.

   Seleccione una métrica prediseñada para ampliarla y guardarla como métrica atenuada.

   ![](assets/6_4_workstation_metricdim_metric.png)

1. (opcional) Crear una fórmula de métrica.

   Haga clic en el cuadro para introducir una fórmula de métrica personalizada. El valor de Vista previa calculado aparecerá validando la expresión.

   ![](assets/6_4_workstation_metricdim_create_metric.png)

   Puede agregar su propia expresión [de](https://docs.adobe.com/content/help/en/data-workbench/using/client/qry-lang-syntx/c-syntx-mtrc-exp.html) métrica o cortar y pegar desde otro editor de métricas o visualización. Los errores de sintaxis, los errores de fórmula, los filtros no definidos y otros errores se notifican en el asistente.

1. Haga clic en **[!UICONTROL Next]**.

## Paso 2: Formato y definición de contenedores {#section-5bddf3cd306545d7806a501637f80f77}

1. Seleccione un formato para la nueva métrica dim.

   ![](assets/6_4_workstation_metricdim_format_metric.png)

   El formato define cómo se presentará la métrica cuando se abra en una visualización. Estos formatos son estándares [](http://www.cplusplus.com/reference/cstdio/printf/)de impresión seleccionados, definidos a continuación:

   ```
   %[flags][width][.precision][length][specifier]
   % 0.2lf = % _ [flags] 0 [width] .2 [.precision] l [length] f[ specifier]
   ```

   En el **[!UICONTROL Preview]** campo, aparecerá un valor basado en la métrica y el formato seleccionados.

1. Agregar expresión de recuento de bloques.

   Puede definir una atenuación de métrica con varios rangos o bloques. Esto devuelve subconjuntos de elementos basados en el tamaño, como [0-4], [5-10],...). Los elementos del nivel de dimensión están relacionados con los elementos cuyo rango contiene el valor de la métrica. Consulte la descripción de la expresión de bloque en [Sintaxis para expresiones](https://docs.adobe.com/content/help/en/data-workbench/using/client/qry-lang-syntx/c-syntx-dim-exp.html)de dimensión.

1. Haga clic en **[!UICONTROL Preview]** para abrir la tabla de valores de Dim de métricas antes de guardar.

   ![](assets/6_4_workstation_metricdim_preview.png)

   La tabla detalla los valores de las métricas por cada dim de métrica.

1. Haga clic **[!UICONTROL Show in Dimension Menu]** para agregar la dimensión recién creada a la ficha **Dimensión** en el **Buscador**.

1. Haga clic en **[!UICONTROL Next]**.

## Paso 3: Finalizar y guardar {#section-d9043235b18a425f9de0db668d4b1683}

1. Seleccione esta opción para iniciar el Editor de atenuación de métricas, la visualización de gráficos o la tabla después de guardar.

   | Campo | Descripción |
   |---|---|
   | **[!UICONTROL Launch Metric Dim Editor]** | Abra el Editor de atenuación de métricas. |
   | **[!UICONTROL Launch Graph]** | Inicie un gráfico PNG de la tabla. |
   | **[!UICONTROL Launch Table]** | Inicie una tabla en el espacio de trabajo con valores en columnas que enumeren los valores de la nueva métrica atenuada en comparación con los valores de la métrica seleccionada. |

1. Haga clic en **[!UICONTROL Finish]** y guarde.

   Se abrirá un cuadro de diálogo para guardar el archivo. Las opciones seleccionadas para ver los valores se abrirán en el espacio de trabajo.
