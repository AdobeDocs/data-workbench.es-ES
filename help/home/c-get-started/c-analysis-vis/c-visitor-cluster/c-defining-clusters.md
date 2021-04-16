---
description: Seleccione las variables de entrada, el número de clústeres y una población objetivo (si lo desea) para definir clústeres en el conjunto de datos.
title: Creación de clústeres
uuid: f8462445-b7d2-48ae-aed7-2a3abc491cfb
exl-id: 60bc75bf-2f89-455b-8be9-aa20bb837752
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '508'
ht-degree: 1%

---

# Creación de clústeres{#building-clusters}

Seleccione las variables de entrada, el número de clústeres y una población objetivo (si lo desea) para definir clústeres en el conjunto de datos.

**Creación de clústeres**

1. Abra el **[!UICONTROL Cluster Builder]**.

   Haga clic en **Visualización** > **Análisis predictivo** > **Clúster** > **Generador de clústeres**.

   ![](assets/cluster-builder-step1.png)

1. Seleccione las variables de entrada.

   * Agregue métricas a la lista **[!UICONTROL Input Variables]** seleccionando en el menú **[!UICONTROL Metric]** de la barra de herramientas.

      ![](assets/cluster_metric_select.png)

   * Agregue elementos de dimensión a la lista **[!UICONTROL Input Variables]** arrastrándolos desde una tabla de Dimension.

      Pulse **[!UICONTROL Ctrl + Alt]** y arrastre los elementos de dimensión seleccionados a la lista **[!UICONTROL Input Variables]** o al cuadro **[!UICONTROL Element]** de la barra de herramientas.

      ![](assets/cluster_dim_select.png)
   De forma predeterminada, la agrupación en clúster se realiza en todo el conjunto de datos. Puede ver todas las variables de entrada en el panel izquierdo **[!UICONTROL Preprocessing]**.
1. Utilice el menú **[!UICONTROL Options]** para seleccionar el número deseado de clústeres.

   ![](assets/build_cluster_2.png)

1. Si desea agrupar un subconjunto de los Visitantes en el conjunto de datos, puede definir un Filtro de población.

   ![](assets/build_cluster_3.png)

   Comience definiendo el subconjunto deseado mediante selecciones en el espacio de trabajo o utilizando el **[!UICONTROL Filter Editor]**. Una vez que haya seleccionado el subconjunto deseado, establezca la población objetivo en el menú **[!UICONTROL Options]** . Se recomienda asignar un nombre de identificación al grupo de destino.

   El menú **[!UICONTROL Options]** también tiene una configuración para controlar el número máximo de pasadas y el umbral aceptable para la convergencia central.

1. Una vez configuradas las entradas y las opciones, haga clic en el botón **Go** para ejecutar la agrupación localmente o presione **[!UICONTROL Submit]** para enviar la tarea al servidor de Predictive Analytics. Los envíos al servidor guardarán la dimensión resultante en el conjunto de datos cuando se complete la convergencia.

   Cuando se ejecuta localmente, verá que el Generador de clústeres se mueve a través de cuatro etapas de agrupación en clúster en canopy, ya que define centros inteligentes basados en las entradas.

   Una vez que los centros de los clústeres dejan de cambiar más del umbral de convergencia especificado, el Dimension de clúster se convierte y el Generador de clústeres muestra información adicional sobre la relevancia de una entrada para cada clúster.

1. Personalice los clústeres.

   Al hacer clic con el botón derecho en la barra de color de las estadísticas, se abre un menú contextual que le permite personalizar los umbrales de relevancia y, en el caso de las distribuciones de elementos de dimensión, elegir qué prueba se muestra.

   ![](assets/build_cluster_7.png)

   Las entradas de métricas proporcionan una prueba t para cada clúster, mientras que las entradas de elementos de dimensión proporcionan tres pruebas de distribución (Chi al cuadrado, una estadística U de entropía y la estadística V de Cramer) para cada clúster.

   >[!NOTE]
   >
   >Si agrega o elimina entradas durante la convergencia, el proceso se pausará hasta que vuelva a presionar **Go**.

   Después de crear clústeres, puede abrir el selector de color para asignar colores a diferentes resultados de distribución.

   ![](assets/build_cluster_5.png)

1. Con el Dimension de clúster convergido, puede agregar métricas a la tabla y realizar las selecciones normales. También puede hacer clic con el botón derecho en los nombres de elementos (Cluster 1, Cluster 2, etc.) para abrir el menú contextual y cambiarles el nombre por otro más significativo.

   ![](assets/build_cluster_6.png)

1. Si desea utilizar esta dimensión de clúster en otras visualizaciones, puede **[!UICONTROL Save]** hacerlo localmente o **[!UICONTROL Submit]** hacerlo en el servidor.

Si desea volver a ejecutar la convergencia o ver la relevancia de las entradas, el Generador de clústeres también puede cargar las dimensiones de clúster existentes.

>[!TIP]
>
>Cuando esté seleccionado, **[!UICONTROL Reset]** lanzará completamente todas las variables de entrada y le proporcionará una visualización en blanco del generador de clústeres para definir nuevos clústeres.
