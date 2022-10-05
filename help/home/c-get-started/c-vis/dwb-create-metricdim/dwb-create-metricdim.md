---
description: Utilice el asistente de atenuación de métricas para crear un nuevo Dimension de métricas.
title: Asistente para atenuación de métricas
uuid: 77b9bc8e-7625-4fef-9de4-f113f9b2debd
exl-id: 109fbefc-5608-493d-aec9-8337f21eaa70
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '493'
ht-degree: 3%

---

# Asistente para atenuación de métricas{#metric-dim-wizard}

{{eol}}

Utilice el asistente de atenuación de métricas para crear un nuevo Dimension de métricas.

Una atenuación de métricas convierte una métrica en una nueva dimensión. Por ejemplo, una atenuación de métrica basada en una métrica de vistas de página y el nivel de visitante mostrará elementos de dimensión según el total de vistas de página de cada visitante. Permite ampliar una métrica definida actualmente basada en elementos de dimensión para crear y guardar como una nueva dimensión.

## Paso 1: seleccionar dimensión y métrica {#section-58b6ea7bbba5487ba1a3c264aa3dcb95}

1. **Abrir el Asistente para atenuación de métricas**.

   En un espacio de trabajo, haga clic con el botón derecho y seleccione **Herramientas** > **Crear atenuación de métrica**.

1. **Asigne un nombre a la atenuación de métricas**.

   De forma predeterminada, el campo Nombre se rellenará automáticamente en función de las selecciones Nivel y Métrica .

1. **Seleccione un nivel de Dimension.** El nivel de dimensión es la dimensión principal que contiene todos los valores de elemento constituyente para filtrar la entrada y definir un tipo de dimensión.

   Los niveles de Dimension incluyen:

   * Pulsación
   * Visita individual
   * Producto
   * Visita
   * Visitante.

1. **Seleccionar una métrica**.

   Seleccione una métrica prediseñada para ampliarla y guardarla como métrica atenuada.

   ![](assets/6_4_workstation_metricdim_metric.png)

1. (opcional) **Crear una fórmula de métrica**.

   Haga clic en el cuadro para introducir una fórmula de métrica personalizada. El valor Vista previa calculado aparecerá validando la expresión.

   ![](assets/6_4_workstation_metricdim_create_metric.png)

   Puede agregar su propio [expresión de métrica](https://experienceleague.adobe.com/docs/data-workbench/using/client/qry-lang-syntx/c-syntx-mtrc-exp.html) o cortar y pegar desde otro editor de métricas o visualización. Los errores de sintaxis, los errores de fórmula, los filtros no definidos y otros errores se informan en el asistente.

1. Haga clic en **Siguiente**.

## Paso 2: formatear y definir contenedores {#section-5bddf3cd306545d7806a501637f80f77}

Puede seleccionar el formato de métrica y establecer los valores de bloque para una expresión de dimensión.

1. Seleccione un **Formato** para la nueva métrica dim.

   ![](assets/6_4_workstation_metricdim_format_metric.png)

   El formato define cómo se presentará la métrica cuando se abra en una visualización. Estos formatos están seleccionados [normas printf](https://www.cplusplus.com/reference/cstdio/printf/), definida a continuación:

   ```
   %[flags][width][.precision][length][specifier]
   %
   0.2lf = % _ [flags] 0 [width] .2 [.precision] l [length] f[ specifier]
   ```

   En el **Vista previa** , aparece un valor en función de la métrica y el formato seleccionados.

1. Agregar **Recuento de bloques** expresión.

   Puede definir una atenuación de métrica con varios intervalos o bloques. Devuelve subconjuntos de elementos basados en el tamaño, como [0-4], [5-10],...). Los elementos del nivel de Dimension están relacionados con los elementos cuyo intervalo contiene el valor de la métrica. Consulte la descripción de la expresión del bloque en [Sintaxis para expresiones de Dimension](https://experienceleague.adobe.com/docs/data-workbench/using/client/qry-lang-syntx/c-syntx-dim-exp.html).

1. Haga clic en **Vista previa** para abrir la tabla de valores de atenuación de métricas antes de guardar.

   ![](assets/6_4_workstation_metricdim_preview.png)

   La tabla detalla los valores de las métricas por cada métrica atenuada.

1. Haga clic en **Mostrar en el menú del Dimension** para añadir la dimensión recién creada al **Dimension** en la ficha **Buscador**.
1. Haga clic en **Siguiente**.

## Paso 3: finalizar y guardar {#section-d9043235b18a425f9de0db668d4b1683}

1. Seleccione para iniciar el Editor de atenuación de métricas, la visualización de gráficos o la tabla después de guardar.

   | Campo | Descripción |
   |---|---|
   | Iniciar Editor de atenuación de métricas | Abra el Editor de atenuación de métricas. |
   | Gráfico de Launch | Inicie un gráfico PNG de la tabla. |
   | Tabla de lanzamiento | Inicie una tabla en el espacio de trabajo con valores en columnas que enumeran los valores de la nueva métrica atenuados en comparación con los valores de la métrica seleccionada. |

1. Haga clic en **Finalizar** y guarde.

   Se abrirá un cuadro de diálogo que le permitirá guardar el archivo. Las opciones seleccionadas para ver los valores se abrirán en el espacio de trabajo.
