---
description: Seleccione las variables de entrada, el número de clústeres y una población objetivo (si lo desea) para definir clústeres en el conjunto de datos.
title: Creación de clústeres
uuid: f8462445-b7d2-48ae-aed7-2a3abc491cfb
exl-id: 60bc75bf-2f89-455b-8be9-aa20bb837752
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '508'
ht-degree: 1%

---

# Creación de clústeres{#building-clusters}

{{eol}}

Seleccione las variables de entrada, el número de clústeres y una población objetivo (si lo desea) para definir clústeres en el conjunto de datos.

**Creación de clústeres**

1. Abra el **[!UICONTROL Cluster Builder]**.

   Haga clic en **Visualización** > **Predictive Analytics** > **Clustering** > **Generador de clústeres**.

   ![](assets/cluster-builder-step1.png)

1. Seleccione las variables de entrada.

   * Agregue métricas a **[!UICONTROL Input Variables]** seleccionando en la lista **[!UICONTROL Metric]** en la barra de herramientas.

      ![](assets/cluster_metric_select.png)

   * Añadir elementos de dimensión a la variable **[!UICONTROL Input Variables]** arrastrándolos desde la tabla de un Dimension.

      Press **[!UICONTROL Ctrl + Alt]** y arrastre los elementos de dimensión seleccionados al **[!UICONTROL Input Variables]** o a la **[!UICONTROL Element]** en la barra de herramientas.

      ![](assets/cluster_dim_select.png)
   De forma predeterminada, la agrupación en clúster se realiza en todo el conjunto de datos. Puede ver todas las variables de entrada a la izquierda **[!UICONTROL Preprocessing]** panel.
1. Utilice la variable **[!UICONTROL Options]** para seleccionar el número deseado de clústeres.

   ![](assets/build_cluster_2.png)

1. Si desea agrupar un subconjunto de los Visitantes en el conjunto de datos, puede definir un Filtro de población.

   ![](assets/build_cluster_3.png)

   Comience definiendo el subconjunto deseado mediante las selecciones realizadas en el espacio de trabajo o utilizando la variable **[!UICONTROL Filter Editor]**. Una vez que tenga seleccionado el subconjunto deseado, establezca la población objetivo en la variable **[!UICONTROL Options]** para abrir el Navegador. Se recomienda asignar un nombre de identificación al grupo de destino.

   La variable **[!UICONTROL Options]** también tiene ajustes para controlar el número máximo de pasadas y el umbral aceptable para la convergencia central.

1. Una vez configuradas las entradas y las opciones, haga clic en el botón **Ir** para ejecutar la agrupación localmente o pulse **[!UICONTROL Submit]** para enviar la tarea al servidor de Predictive Analytics. Los envíos al servidor guardarán la dimensión resultante en el conjunto de datos cuando se complete la convergencia.

   Cuando se ejecuta localmente, verá que el Generador de clústeres se mueve a través de cuatro etapas de agrupación en clúster en canopy, ya que define centros inteligentes basados en las entradas.

   Una vez que los centros de los clústeres dejan de cambiar más del umbral de convergencia especificado, el Dimension de clúster se convierte y el Generador de clústeres muestra información adicional sobre la relevancia de una entrada para cada clúster.

1. Personalice los clústeres.

   Al hacer clic con el botón derecho en la barra de color de las estadísticas, se abre un menú contextual que le permite personalizar los umbrales de relevancia y, en el caso de las distribuciones de elementos de dimensión, elegir qué prueba se muestra.

   ![](assets/build_cluster_7.png)

   Las entradas de métricas proporcionan una prueba t para cada clúster, mientras que las entradas de elementos de dimensión proporcionan tres pruebas de distribución (Chi al cuadrado, una estadística U de entropía y la estadística V de Cramer) para cada clúster.

   >[!NOTE]
   >
   >Si agrega o elimina entradas durante la convergencia, el proceso se pausará hasta que presione **Ir** de nuevo.

   Después de crear clústeres, puede abrir el selector de color para asignar colores a diferentes resultados de distribución.

   ![](assets/build_cluster_5.png)

1. Con el Dimension de clúster convergido, puede agregar métricas a la tabla y realizar las selecciones normales. También puede hacer clic con el botón derecho en los nombres de elementos (Cluster 1, Cluster 2, etc.) para abrir el menú contextual y cambiarles el nombre por otro más significativo.

   ![](assets/build_cluster_6.png)

1. Si desea utilizar esta dimensión de clúster en otras visualizaciones, puede **[!UICONTROL Save]** o localmente o **[!UICONTROL Submit]** al servidor.

Si desea volver a ejecutar la convergencia o ver la relevancia de las entradas, el Generador de clústeres también puede cargar las dimensiones de clúster existentes.

>[!TIP]
>
>Cuando se selecciona, **[!UICONTROL Reset]** liberará completamente todas las variables de entrada y le proporcionará una visualización del generador de clústeres en blanco para definir nuevos clústeres.
