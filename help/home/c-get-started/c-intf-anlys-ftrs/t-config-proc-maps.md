---
description: Los mapas de procesos se pueden configurar para que funcionen con cualquier combinación de dimensión base, dimensión de grupo, dimensión de nivel y métrica que tenga sentido para la aplicación y el conjunto de datos.
title: Configuración de un mapa de proceso
uuid: e629191e-48b9-4b58-b6aa-3705ff7b387e
exl-id: 0b37e942-4596-45cc-bc31-db147626f4eb
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '449'
ht-degree: 2%

---

# Configuración de un mapa de proceso{#configure-a-process-map}

Los mapas de procesos se pueden configurar para que funcionen con cualquier combinación de dimensión base, dimensión de grupo, dimensión de nivel y métrica que tenga sentido para la aplicación y el conjunto de datos.

Después de configurar un mapa de proceso, aparece junto con otros mapas de proceso en el [!DNL Add Visualization menu].

1. En [!DNL Profile Manager], haga clic en **[!UICONTROL Menu]**, haga clic en **[!UICONTROL Add Visualization]** y, a continuación, haga clic en el tipo de mapa de proceso que desea configurar (Mapa de métricas 2D, Mapa de proceso 2D o Mapa de proceso 3D).

   Al menos un archivo [!DNL *.vw] reside en el directorio .

1. Haga clic con el botón derecho en la marca de verificación del archivo deseado y haga clic en **[!UICONTROL Make Local]**.
1. Haga clic con el botón derecho en la marca de verificación del archivo en la columna [!DNL User] y haga clic en **[!UICONTROL Open]** > **[!UICONTROL in Notepad]**.
1. Edite los parámetros del archivo utilizando el siguiente archivo de ejemplo y la tabla como guías:

   ```
   window = simpleBorderWindow: 
     client = processMap: 
       Traffic Metric = ref: wdata/model/metric/metric name
       center = v3d: (-0.741014, 0, 0.0639476)
       color_links = bool: true
       Map = PrefixDim: 
         Name = string: Map
         Base Dimension = ref: wdata/model/dim/base dimension name
         Element Prefixes = vector: 0 items
         Element Names = vector: 0 items
       Map Level = ref: wdata/model/dim/level dimension name
       Map Group = ref: wdata/model/dim/group dimension name
       node_label = vector<bool>: 
       node_positions = vector: 0 items
       quantify_links = int: 2
       range = double: 2.37386
       size = v3d: (430, 290, 0)
       xAxisMetric = ref: wdata/model/metric/metric name for metric map
     pos = v3d: (880, 595, 0)
     size = v3d: (430, 309, 0)
   ```

<table id="table_3F072DB1B68746C49DF9332718982EBE"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Para este parámetro... </th> 
   <th colname="col2" class="entry"> Proporcione esta información... </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><i>Nombre de la métrica</i> </p> </td> 
   <td colname="col2"> <p>Nombre de la métrica cuyo valor para un nodo determinado es proporcional al tamaño del nodo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><i>Nombre de la dimensión base</i> </p> </td> 
   <td colname="col2"> <p>Nombre de la dimensión cuyos elementos aparecen como nodos en el mapa de procesos. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><i>Nombre de dimensión de nivel</i> </p> </td> 
   <td colname="col2"> <p>Nombre del nivel (principal) de la dimensión base cuyos elementos arrastre al mapa de proceso. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><i>Nombre de la dimensión del grupo</i> </p> </td> 
   <td colname="col2"> <p>Nombre de la dimensión que determina cómo se agrupan los elementos de la dimensión de nivel para formar las conexiones entre nodos. Una conexión entre dos nodos no puede abarcar más de un elemento de una dimensión de grupo. Al realizar una selección basada en un nodo dentro de un mapa de procesos, se seleccionan todos los elementos de la dimensión de grupo que involucraron ese nodo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><i>Nombre de la métrica para el mapa de métricas</i> </p> </td> 
   <td colname="col2"> <p>Este parámetro se aplica únicamente a los mapas de métricas 2D. </p> <p>Nombre de la métrica cuyo valor determina la posición horizontal de los nodos en el mapa. </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>Para obtener más información sobre la dimensión base, la dimensión de grupo, la dimensión de nivel y la métrica de un mapa de proceso, consulte [Mapas de proceso](../../../home/c-get-started/c-analysis-vis/c-proc-maps/c-proc-maps.md#concept-880aee224404429785b733a4e80d275e).

1. En el Bloc de notas, haga clic en **[!UICONTROL File]** > **[!UICONTROL Save As]** para guardar el archivo con un nuevo nombre basado en la dimensión base, es decir, *Base dimension name*.vw.

   (Si está configurando un mapa de métricas 2D, debe guardar el archivo con un nombre basado en el nombre de la métrica para el mapa de métricas, es decir, *Nombre de métrica para el mapa de métrica*.vw.) Asegúrese de guardar el archivo en el directorio de asignación de procesos correspondiente.

   >[!NOTE]
   >
   >Para asegurarse de que la asignación de proceso se guarde como un archivo [!DNL *.vw], en la ventana [!DNL Save As], establezca Guardar como tipo en Todos los archivos.

1. (Opcional) Para que los cambios estén disponibles para todos los usuarios del perfil de trabajo, en [!DNL Profile Manager], haga clic con el botón derecho en la marca de verificación del archivo en la columna [!DNL User] y haga clic en **[!UICONTROL Save to]** > *&lt;**[!UICONTROL working profile name]**>*.
