---
description: Seleccione las variables de entrada, el número de clústeres y una población de destino (si lo desea) para definir clústeres en el conjunto de datos.
solution: Analytics
title: Generación de clústeres
topic: Data workbench
uuid: f8462445-b7d2-48ae-aed7-2a3abc491cfb
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Generación de clústeres{#building-clusters}

Seleccione las variables de entrada, el número de clústeres y una población de destino (si lo desea) para definir clústeres en el conjunto de datos.

**Generación de clústeres**

1. Abra el **[!UICONTROL Cluster Builder]**.

   Haga clic en **Visualización** > Análisis **predictivos** > **Clúster** > Generador **de clústeres**.

   ![](assets/cluster-builder-step1.png)

1. Seleccione las variables de entrada.

   * Para agregar métricas a la **[!UICONTROL Input Variables]** lista, seleccione en el **[!UICONTROL Metric]** menú de la barra de herramientas.

      ![](assets/cluster_metric_select.png)

   * Agregue elementos de dimensión a la **[!UICONTROL Input Variables]** lista arrastrándolos desde una tabla de dimensión.

      Pulse **[!UICONTROL Ctrl + Alt]** y arrastre los elementos de dimensión seleccionados a la **[!UICONTROL Input Variables]** lista o al **[!UICONTROL Element]** cuadro de la barra de herramientas.

      ![](assets/cluster_dim_select.png)
   De forma predeterminada, la agrupación en clúster se realiza en todo el conjunto de datos. Puede ver todas las variables de entrada en el **[!UICONTROL Preprocessing]** panel izquierdo.
1. Utilice el **[!UICONTROL Options]** menú para seleccionar el número deseado de clústeres.

   ![](assets/build_cluster_2.png)

1. Si desea agrupar un subconjunto de Visitantes en el conjunto de datos, puede definir un filtro de población.

   ![](assets/build_cluster_3.png)

   Comience definiendo el subconjunto deseado mediante las selecciones realizadas en el espacio de trabajo o mediante el uso del **[!UICONTROL Filter Editor]**. Una vez seleccionado el subconjunto deseado, establezca la opción Población de destino en el **[!UICONTROL Options]** menú. Se recomienda asignar al grupo objetivo un nombre de identificación.

   El **[!UICONTROL Options]** menú también tiene opciones para controlar el número máximo de pasadas y el umbral aceptable para la convergencia central.

1. Una vez configuradas las entradas y las opciones, haga clic en el botón **Ir** para ejecutar el agrupamiento de forma local o presione **[!UICONTROL Submit]** para enviar la tarea al servidor de análisis predictivo. Los envíos al servidor guardarán la dimensión resultante en el conjunto de datos cuando se complete la convergencia.

   Cuando se ejecuta localmente, verá que el Generador de clústeres se mueve a través de cuatro etapas de agrupación en clústeres de dosel, ya que define centros inteligentes basados en las entradas.

   Una vez que los centros de los clústeres dejan de cambiar más que el umbral de convergencia especificado, la dimensión de clúster se convierte y el Generador de clústeres muestra información adicional sobre la importancia de una entrada para cada clúster.

1. Personalice los clústeres.

   Al hacer clic con el botón derecho en la barra de color de las estadísticas, se abre un menú contextual que permite personalizar los umbrales de relevancia y, en el caso de las distribuciones de elementos de dimensión, elegir qué prueba se muestra.

   ![](assets/build_cluster_7.png)

   Las entradas de métricas proporcionan una prueba t para cada clúster, mientras que las entradas de elementos de dimensión proporcionan tres pruebas de distribución (Chi squared, una estadística U de entropía y la estadística V de Cramer) para cada clúster.

   >[!NOTE]
   >
   >Si agrega o elimina entradas durante la convergencia, el proceso se detendrá hasta que vuelva a pulsar **Ir** .

   Después de crear clústeres, puede abrir el selector de color para asignar colores a diferentes resultados de distribución.

   ![](assets/build_cluster_5.png)

1. Con la dimensión de clúster convergente, puede agregar métricas a la tabla y realizar selecciones de forma normal. También puede hacer clic con el botón derecho en los nombres de elementos (Cluster 1, Cluster 2, etc.) para abrir el menú contextual y cambiarles el nombre por otro más significativo.

   ![](assets/build_cluster_6.png)

1. Si desea utilizar esta dimensión de clúster en otras visualizaciones, puede **[!UICONTROL Save]** hacerlo localmente o **[!UICONTROL Submit]** en el servidor.

Si desea volver a ejecutar la convergencia o ver la pertinencia de las entradas, el Generador de clústeres también puede cargar las dimensiones de clúster existentes.

>[!TIP]
>
>Cuando se selecciona, **[!UICONTROL Reset]** se liberan completamente todas las variables de entrada y se proporciona una visualización en blanco del generador de clústeres para definir nuevos clústeres.

