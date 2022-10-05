---
description: Configure un árbol de decisiones identificando un caso positivo y agregando entradas de métricas y dimensiones para evaluar los datos y explorar el árbol de decisiones.
title: Creación de un árbol de decisión
uuid: 5790d322-5460-444d-95d8-a06696f9a55f
exl-id: 06db9e77-72ea-44c7-8451-d3f195acd196
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '1110'
ht-degree: 0%

---

# Creación de un árbol de decisión{#building-a-decision-tree}

{{eol}}

Configure un árbol de decisiones identificando un caso positivo y agregando entradas de métricas y dimensiones para evaluar los datos y explorar el árbol de decisiones.

Siga estos pasos para crear un árbol de decisiones.

1. Abra un nuevo espacio de trabajo.

   Después de abrir un nuevo espacio de trabajo, es posible que tenga que hacer clic en **Agregar** > **Desbloquear temporalmente**.

1. Para abrir el Generador de árboles de decisiones, haga clic con el botón derecho **[!UICONTROL Visualization]** > **Predictive Analytics** > **Clasificación** > **Generador de árboles de decisión**.

1. Configure un **Caso positivo**.

   Puede definir un caso positivo para un árbol de decisiones seleccionando dimensiones en un Buscador o elementos de dimensión en una tabla, o diseñando un filtro en el Filtro de diseño. De hecho, el caso positivo puede ser una combinación de varias selecciones en el espacio de trabajo, incluidos filtros, dimensiones, elementos y todos los tipos de valores de visualización de Data Workbench.

   * **Diseño y aplicación de un filtro** como caso positivo. Haga clic con el botón derecho en el espacio de trabajo y seleccione **[!UICONTROL Tools]** > **[!UICONTROL Filter Editor]** para diseñar y aplicar un filtro.

   * Agregar **Dimension** como caso positivo. En el espacio de trabajo, haga clic con el botón derecho y seleccione **Herramientas** > **Buscadores** (o seleccione **[!UICONTROL Add]** > **[!UICONTROL Finders]** en el panel izquierdo). Escriba un nombre de dimensión en el **Buscar** y, a continuación, seleccione una dimensión.

   * Agregar **Métricas** como caso positivo. Haga clic con el botón derecho y seleccione **Herramientas** > **Buscadores** o seleccione **[!UICONTROL Add]** > **[!UICONTROL Finders]** en el panel izquierdo para abrir una tabla de métricas. Seleccione una métrica como caso positivo.

   * Agregar **Elementos de Dimension** como caso positivo. Haga clic con el botón derecho en el espacio de trabajo y seleccione **[!UICONTROL Table]** para abrir elementos de dimensión, seleccione entre los elementos de dimensión para establecer las mayúsculas y minúsculas positivas.

1. Haga clic **[!UICONTROL Options]** > **[!UICONTROL Set Positive Case]**.

   Esto establece el caso positivo y le permite asignarle un nombre. El nombre aparecerá debajo de **[!UICONTROL Positive Case]** en el espacio de trabajo.

   >[!NOTE]
   >
   >Cuando se define el caso positivo, el árbol de decisiones utiliza la selección actual del espacio de trabajo, que puede definirse como visitantes (o como el recuento de nivel superior definido, pero en la mayoría de los casos como visitantes) que coinciden con la selección actual dentro del espacio de trabajo. Se combinan como un único filtro para un único caso positivo (no varios casos positivos).

   Hacer clic **[!UICONTROL Set Positive Case]** cuando no haya selección, se borrará el caso positivo.

1. (opcional) Seleccione **[!UICONTROL Set Population Filters]** para definir la población de visitantes que se va a clasificar.

   Si no se aplica ningún filtro de población, el conjunto de formación se obtiene de todos los visitantes (el valor predeterminado es &quot;Todos&quot;).

   >[!NOTE]
   >
   >Haga clic en el **[!UICONTROL Show Complex Filter Description]** para ver las secuencias de comandos de filtrado para el caso positivo y el filtro de población.

1. Agregar **Métricas**, **Dimension** y **Elementos de Dimension** como entradas.

   Puede seleccionar entradas arrastrando y soltando desde los paneles Buscador o desde las tablas para elementos de dimensión individuales. También puede seleccionar entre las **[!UICONTROL Metrics]** en la barra de herramientas.

   * Agregar **Métricas** como entradas.

      Seleccione Métricas en la barra de herramientas. Press **Ctrl** + **Alt** para arrastrar una o más métricas al Generador de árboles de decisiones.

      La métrica aparecerá en la variable **Lista de entrada (métricas)** como entrada con codificación de color única.

      ![](assets/decision_tree_add_Metrics_inputs.png)

   * Agregar **Dimension** como entradas.

      En el espacio de trabajo, haga clic con el botón derecho y seleccione **Herramientas** > **Buscador** y escriba el nombre de la dimensión en la **Buscar** campo . Press **Ctrl** + **Alt**, seleccione una dimensión y arrastre la dimensión al Generador de árboles de decisiones.

      La dimensión aparecerá en el **Entrada (Dimension)** con una codificación de color única.

   * Agregar **Elementos de Dimension** como entradas.

      En el espacio de trabajo, haga clic con el botón derecho y seleccione una tabla de Dimension. Seleccionar elementos del Dimension, pulse **Ctrl** + **Alt** y arrastre los elementos seleccionados al Generador de árboles de decisiones.

      Los elementos de dimensión aparecerán en la variable **Entrada (elementos)** con una codificación de color única.
   >[!IMPORTANT]
   >
   >Puede seleccionar hasta un máximo de catorce entradas para evaluar. Si se añaden demasiadas entradas, aparecerá un mensaje de error.

1. Select **[!UICONTROL Go]** en la barra de herramientas.

   El árbol de decisiones se generará en función de las dimensiones y métricas seleccionadas. Las métricas simples, como Adiciones al carro de compras, se generarán rápidamente, mientras que las dimensiones complejas, como la duración de la visita con varios puntos de datos, se generarán más lentamente, con un porcentaje de la finalización mostrado a medida que se convierta. A continuación, el mapa de árbol se recortará y se abrirá para la interacción del usuario. Las entradas de dimensión y métrica se codificarán con colores y serán coherentes con los nombres de nodo.

   ![](assets/decision_tree_builder.png)

   El nodo de hoja se muestra como verde (verdadero) o rojo (falso) si el árbol se ha copiado y si hay una predicción de **True** o **False** siguiendo las ramas recortadas.

   >[!NOTE]
   >
   >El ejemplo de formación se extrae del conjunto de datos para que el generador de árboles lo utilice. La Data Workbench utiliza el 80 % de la muestra para crear el árbol y el 20 % restante para evaluar la precisión del modelo de árbol.

1. Verificar la precisión utilizando la variable **[!UICONTROL Confusion Matrix]**.

   Haga clic en **[!UICONTROL Options]** > **[!UICONTROL Confusion Matrix]** para ver los valores de precisión, recuperación, precisión y puntuación F. Cuanto más cerca del 100 por ciento, mejor será la puntuación.

   La matriz de confusión ofrece cuatro recuentos de precisión del modelo mediante una combinación de valores:

   * Positivo real (AP)
   * Predicted Positive (PP)
   * Negativo real (AN)
   * Predicted Negative (PN)

   >[!TIP]
   >
   >Estos números se obtienen aplicando el modelo de puntuación resultante de los datos de prueba del 20 % retenidos y ya conocidos como la respuesta verdadera. Si la puntuación es buena al 50 por ciento, se predice como un caso positivo (que coincide con el filtro definido). A continuación, Precisión = (TP + TN)/(TP + FP + TN + FN), Recuperación = TP / (TP + FN) y Precisión = TP / (TP + FP).

1. **Explorar el árbol de decisiones**.

   Después de generar un árbol de decisiones, puede ver la ruta de la predicción e identificar a todos los visitantes que cumplan los criterios definidos. El árbol identifica la división de entrada de cada rama en función de su posición y codificación de color. Por ejemplo, si selecciona el nodo Dominio de referencia , los nodos que conducen a esa división se enumeran por código de color a la izquierda del árbol.

   Puede realizar selecciones de los nodos de hoja para seleccionar ramas (conjuntos de reglas) del árbol de decisiones.

   Para este ejemplo: Si la duración de la visita es menor que 1, no existe ninguna campaña, existe al menos una vista de página, no hay registros por correo electrónico y hubo al menos una visita. Las proyecciones sobre este criterio de reunión y la realización de un pedido son **94,73** porcentaje.

   ![](assets/decision_tree_explore.png)

   **Interacción del árbol de decisiones**: Puede seleccionar varios nodos en el árbol mediante el estándar **Ctrl-clic** para agregar, o **Mayús-clic** para eliminar.

   **Nodos codificados por color**: El color de los nodos coincide con el color de las dimensiones y métricas de entrada según la Data Workbench asignada.

   Los nodos verdes y rojos brillantes en el nivel de hoja de una rama recortada predicen el nodo como Verdadero o Falso.

   | ![](assets/decision_tree_node_true.png) Verde claro | Identifica que el nodo es igual a verdadero y que se cumplen todas las condiciones. |
   |---|---|
   | ![](assets/decision_tree_node_false.png) Rojo claro | Identifica que el nodo es igual a falso y que no se cumplen todas las condiciones. |

1. **Guardar el árbol de decisiones**.

   Puede guardar el árbol de decisiones en diferentes formatos:

   ![](assets/decison_tree_save.png)

   * Lenguaje de marcado predictivo (**PMML**), un formato de archivo basado en XML que utilizan las aplicaciones para describir e intercambiar modelos de árbol de decisiones.
   * **Texto** mostrar columnas simples y filas de true o false, porcentajes, número de miembros y valores de entrada.
   * A **Dimension** con ramas correspondientes a los elementos de resultado predichos.
