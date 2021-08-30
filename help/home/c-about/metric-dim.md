---
description: Cree Dimension definidos por atributos de métrica (dimensiones de métricas) mediante un asistente paso a paso. A continuación, pruebe, previsualice y guarde la nueva atenuación de métricas en la lista de Dimension.
title: Asistente para atenuación de métricas
uuid: 411b2e28-0958-43bb-a853-7de7b3063818
exl-id: 4d283a00-409c-4d74-a558-40744caba71c
source-git-commit: 232117a8cacaecf8e5d7fcaccc5290d6297947e5
workflow-type: tm+mt
source-wordcount: '485'
ht-degree: 2%

---

# Asistente para atenuación de métricas{#metric-dim-wizard}

Cree Dimension definidos por atributos de métrica (dimensiones de métricas) mediante un asistente paso a paso. A continuación, pruebe, previsualice y guarde la nueva atenuación de métricas en la lista de Dimension.

Una atenuación de métricas convierte una métrica en una nueva dimensión. Por ejemplo, una atenuación de métrica basada en una métrica de vistas de página y el nivel de visitante mostrará elementos de dimensión según el total de vistas de página de cada visitante. Permite ampliar una métrica definida actualmente basada en elementos de dimensión para crear y guardar como una nueva dimensión.

## Paso 1: Seleccionar Dimension y métrica {#section-58b6ea7bbba5487ba1a3c264aa3dcb95}

1. Abra el Asistente para atenuación de métricas.

   En un espacio de trabajo, haga clic con el botón derecho y seleccione **[!UICONTROL Tools]** > **[!UICONTROL Create Metric Dim]**.

1. Asigne un nombre a la atenuación de métricas.

   De forma predeterminada, el campo Nombre se rellenará automáticamente en función de las selecciones Nivel y Métrica .

1. Seleccione un nivel de Dimension.

   El nivel de dimensión es la dimensión principal que contiene todos los valores de elemento constituyente para filtrar la entrada y definir un tipo de dimensión.

   Los niveles de Dimension incluyen:

   * Pulsación
   * Visita individual
   * Producto
   * Visita
   * Visitante.

1. Seleccione una métrica.

   Seleccione una métrica prediseñada para ampliarla y guardarla como métrica atenuada.

   ![](assets/6_4_workstation_metricdim_metric.png)

1. (opcional) Crear una fórmula de métrica.

   Haga clic en el cuadro para introducir una fórmula de métrica personalizada. El valor Vista previa calculado aparecerá validando la expresión.

   ![](assets/6_4_workstation_metricdim_create_metric.png)

   Puede agregar su propia [expresión de métrica](https://experienceleague.adobe.com/docs/data-workbench/using/client/qry-lang-syntx/c-syntx-mtrc-exp.html) o cortar y pegar desde otro editor o visualización de métricas. Los errores de sintaxis, los errores de fórmula, los filtros no definidos y otros errores se informan en el asistente.

1. Haga clic en **[!UICONTROL Next]**.

## Paso 2: Formato y configuración de contenedores {#section-5bddf3cd306545d7806a501637f80f77}

1. Seleccione un formato para la nueva atenuación de métrica.

   ![](assets/6_4_workstation_metricdim_format_metric.png)

   El formato define cómo se presentará la métrica cuando se abra en una visualización. Estos formatos están seleccionados [printf standard](http://www.cplusplus.com/reference/cstdio/printf/), definidos a continuación:

   ```
   %[flags][width][.precision][length][specifier]
   % 0.2lf = % _ [flags] 0 [width] .2 [.precision] l [length] f[ specifier]
   ```

   En el campo **[!UICONTROL Preview]**, aparecerá un valor basado en la métrica y el formato seleccionados.

1. Añadir expresión Recuento de bloques.

   Puede definir una atenuación de métrica con varios intervalos o bloques. Esto devuelve subconjuntos de elementos basados en el tamaño, como [0-4], [5-10],...). Los elementos del nivel de Dimension están relacionados con los elementos cuyo intervalo contiene el valor de la métrica. Consulte la descripción de la expresión del bloque en [Sintaxis para expresiones de Dimension](https://experienceleague.adobe.com/docs/data-workbench/using/client/qry-lang-syntx/c-syntx-dim-exp.html).

1. Haga clic en **[!UICONTROL Preview]** para abrir la tabla de valores de atenuación de métricas antes de guardar.

   ![](assets/6_4_workstation_metricdim_preview.png)

   La tabla detalla los valores de las métricas por cada métrica atenuada.

1. Haga clic **[!UICONTROL Show in Dimension Menu]** para añadir la dimensión recién creada a la pestaña **Dimension** en el **Finder**.

1. Haga clic en **[!UICONTROL Next]**.

## Paso 3: Finalizar y guardar {#section-d9043235b18a425f9de0db668d4b1683}

1. Seleccione para iniciar el Editor de atenuación de métricas, la visualización de gráficos o la tabla después de guardar.

   | Campo | Descripción |
   |---|---|
   | **[!UICONTROL Launch Metric Dim Editor]** | Abra el Editor de atenuación de métricas. |
   | **[!UICONTROL Launch Graph]** | Inicie un gráfico PNG de la tabla. |
   | **[!UICONTROL Launch Table]** | Inicie una tabla en el espacio de trabajo con valores en columnas que enumeran los valores de la nueva métrica atenuados en comparación con los valores de la métrica seleccionada. |

1. Haga clic en **[!UICONTROL Finish]** y guarde.

   Se abrirá un cuadro de diálogo que le permitirá guardar el archivo. Las opciones seleccionadas para ver los valores se abrirán en el espacio de trabajo.
