---
description: Configure un árbol de decisiones identificando un caso positivo y agregando entradas de métricas y dimensiones para evaluar los datos y explorar el árbol de decisiones.
title: Creación de un árbol de decisiones
uuid: 5790d322-5460-444d-95d8-a06696f9a55f
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Creación de un árbol de decisiones{#building-a-decision-tree}

Configure un árbol de decisiones identificando un caso positivo y agregando entradas de métricas y dimensiones para evaluar los datos y explorar el árbol de decisiones.

Siga estos pasos para crear un árbol de decisiones.

1. Abra un nuevo espacio de trabajo.

   Después de abrir un nuevo espacio de trabajo, es posible que tenga que hacer clic en **Agregar** > **Desbloquear** temporalmente.

1. Para abrir el Generador de árboles de decisiones, haga clic con el botón derecho **[!UICONTROL Visualization]** > **Análisis** predictivos > **Clasificación** > Generador **de árboles de** decisiones.

1. Configure un caso **positivo**.

   Puede definir un caso positivo para un árbol de decisiones seleccionando dimensiones en un Buscador o elementos de dimensión en una tabla, o diseñando un filtro en el Filtro de diseño. De hecho, el caso positivo puede ser una combinación de varias selecciones en el espacio de trabajo, incluyendo filtros, dimensiones, elementos y todos los tipos de valores de visualización del Área de trabajo de datos.

   * **Diseñar y aplicar un filtro** como un caso positivo. Haga clic con el botón derecho en el espacio de trabajo y seleccione **[!UICONTROL Tools]** > **[!UICONTROL Filter Editor]** para diseñar y aplicar un filtro.

   * Agregar **dimensiones** como un caso positivo. En el espacio de trabajo, haga clic con el botón derecho y seleccione **Herramientas** > **Buscadores** (o seleccione **[!UICONTROL Add]** > **[!UICONTROL Finders]** en el panel izquierdo). Escriba un nombre de dimensión en el campo **Buscar** y, a continuación, seleccione una dimensión.

   * Agregar **métricas** como un caso positivo. Haga clic con el botón derecho y seleccione **Herramientas** > **Buscadores** o seleccione **[!UICONTROL Add]** > **[!UICONTROL Finders]** en el panel izquierdo para abrir una tabla de métricas. Seleccione una métrica como caso positivo.

   * Agregue elementos **de** dimensión como un caso positivo. Haga clic con el botón derecho en el espacio de trabajo y seleccione **[!UICONTROL Table]** para abrir los elementos de dimensión y, a continuación, seleccione entre los elementos de dimensión para definir el caso positivo.

1. Haga clic **[!UICONTROL Options]** > **[!UICONTROL Set Positive Case]**.

   Esto establece el caso positivo y le permite asignarle un nombre. El nombre aparecerá debajo del **[!UICONTROL Positive Case]** encabezado en el espacio de trabajo.

   >[!NOTE]
   >
   >Cuando se establece el caso positivo, el árbol de decisiones utiliza la selección actual del espacio de trabajo, que puede definirse como visitantes (o cualquier recuento de nivel superior definido, pero en la mayoría de los casos visitantes) que coincida con la selección actual dentro del espacio de trabajo. Se combinan como un único filtro para un solo caso positivo (no varios casos positivos).

   Si hace clic **[!UICONTROL Set Positive Case]** cuando no hay selección, se borrará el caso positivo.

1. (opcional) Seleccione **[!UICONTROL Set Population Filters]** para definir la población de visitantes que se va a clasificar.

   Si no se aplica ningún filtro de población, el conjunto de formación se extrae de todos los visitantes (el valor predeterminado es &quot;Todos&quot;).

   >[!NOTE]
   >
   >Haga clic en **[!UICONTROL Show Complex Filter Description]** para ver las secuencias de comandos de filtrado para el caso positivo y el filtro de población.

1. Agregue **métricas**, **dimensiones** y elementos **** de dimensión como entradas.

   Puede seleccionar entradas arrastrando y soltando desde los paneles de Buscador o desde tablas para elementos de dimensión individuales. También puede seleccionarlo en el **[!UICONTROL Metrics]** menú de la barra de herramientas.

   * Agregar **métricas** como entradas.

      Seleccione Métricas en la barra de herramientas. Pulse **Ctrl** + **Alt** para arrastrar una o varias métricas al Generador de árboles de decisiones.

      La métrica aparecerá en la lista **** Entrada (Métricas) como una entrada con una codificación de color única.

      ![](assets/decision_tree_add_Metrics_inputs.png)

   * Agregar **dimensiones** como entradas.

      En el espacio de trabajo, haga clic con el botón derecho y seleccione **Herramientas** > **Buscador** y escriba el nombre de la dimensión en el campo **Buscar** . Pulse **Ctrl** + **Alt**, seleccione una dimensión y arrástrela al Generador de árboles de decisiones.

      La dimensión aparecerá en la lista **Entrada (dimensiones)** con una codificación de color única.

   * Agregar elementos **de dimensión** como entradas.

      En el espacio de trabajo, haga clic con el botón derecho y seleccione una tabla de dimensiones. Seleccione Elementos de dimensión, pulse **Ctrl** + **Alt** y arrastre los elementos seleccionados al Generador de árboles de decisiones.

      Los elementos de dimensión aparecerán en la lista **Entrada (elementos)** con una codificación de color única.
   >[!IMPORTANT]
   >
   >Puede seleccionar hasta un máximo de catorce entradas para evaluar. Si se agregan demasiadas entradas, aparecerá un mensaje de error.

1. Seleccione **[!UICONTROL Go]** en la barra de herramientas.

   El árbol de decisiones se generará en función de las dimensiones y métricas seleccionadas. Las métricas simples como Adiciones al carro de compras se generarán rápidamente, mientras que las dimensiones complejas como Duración de la visita con varios puntos de datos se generarán más lentamente con un porcentaje de la finalización mostrado a medida que se convierte. A continuación, el mapa de árbol se bloqueará y se abrirá para la interacción del usuario. Las entradas de dimensión y métrica tendrán un código de colores coherente con los nombres de nodo.

   ![](assets/decision_tree_builder.png)

   El nodo de hoja se muestra como verde (true) o rojo (false) si el árbol se ha copiado y si hay una predicción de **True** o **False** después de las ramas predefinidas.

   >[!NOTE]
   >
   >El ejemplo de formación se extrae del conjunto de datos para que el generador de árbol lo utilice. Área de trabajo de datos utiliza el 80 por ciento de la muestra para crear el árbol y el 20 por ciento restante para evaluar la precisión del modelo de árbol.

1. Compruebe la precisión con el **[!UICONTROL Confusion Matrix]**.

   Haga clic en **[!UICONTROL Options]** > **[!UICONTROL Confusion Matrix]** para ver los valores de Precisión, Reclamación, Precisión y F-Puntuación. Cuanto más se acerque al 100 por ciento, mejor será la puntuación.

   La matriz de confusión ofrece cuatro recuentos de precisión del modelo mediante una combinación de valores:

   * Positivo real (AP)
   * Positivo Predicho (PP)
   * Negativo real (AN)
   * Negativo previsto (PN)
   >[!TIP]
   >
   >Estos números se obtienen aplicando el modelo de puntuación resultante de los datos de prueba del 20 por ciento retenidos y ya conocidos como la respuesta verdadera. Si la puntuación es buena al 50 por ciento, se predice como un caso positivo (que coincide con el filtro definido). A continuación, Precisión = (TP + TN)/(TP + FP + TN + FN), Recuperación = TP / (TP + FN) y Precisión = TP / (TP + FP).

1. **Explore el árbol** de decisiones.

   Después de generar un árbol de decisiones, puede ver la ruta de la predicción e identificar a todos los visitantes que cumplan los criterios definidos. El árbol identifica la división de entrada para cada rama en función de su posición y codificación de color. Por ejemplo, si selecciona el nodo Dominio de referencia, los nodos que conducen a esa división se muestran por código de color a la izquierda del árbol.

   Puede realizar selecciones de los nodos de hoja para seleccionar ramas (conjuntos de reglas) del árbol de decisiones.

   Para este ejemplo: Si la duración de la visita es menor que 1, no existe ninguna campaña, existe al menos una vista de página, no se registra por correo electrónico y hubo al menos una visita. Las proyecciones sobre este criterio de cumplimiento y la realización de un pedido son del **94,73** por ciento.

   ![](assets/decision_tree_explore.png)

   **Interacción** del árbol de decisiones: Puede seleccionar varios nodos en el árbol con la **tecla Ctrl** estándar para agregar o **Mayús-clic** para eliminar.

   **Nodos** con código de color: El color de los nodos coincide con el color de las dimensiones de entrada y las métricas que asigna el área de trabajo de datos.

   Los nodos verdes y rojos brillantes en el nivel de hoja de una rama predicha el nodo como Verdadero o Falso.

   | ![](assets/decision_tree_node_true.png) Verde claro | Identifica que el nodo es igual a true y que se cumplen todas las condiciones. |
   |---|---|
   | ![](assets/decision_tree_node_false.png) Rojo claro | Identifica que el nodo es igual a false y que no se cumplen todas las condiciones. |

1. **Guarde el árbol** de decisiones.

   Puede guardar el árbol de decisiones en diferentes formatos:

   ![](assets/decison_tree_save.png)

   * Predictive Markup Language (**PMML**), un formato de archivo basado en XML que utilizan las aplicaciones para describir e intercambiar modelos de árbol de decisiones.
   * **Texto** que muestra columnas simples y filas de verdadero o falso, porcentajes, número de miembros y valores de entrada.
   * Una **dimensión** con ramas que corresponden a los elementos de resultado predichos.

