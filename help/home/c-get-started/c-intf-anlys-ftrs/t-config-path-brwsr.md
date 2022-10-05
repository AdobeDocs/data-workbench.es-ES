---
description: Los exploradores de rutas se pueden configurar para que funcionen con cualquier combinación de dimensión base, dimensión de grupo, dimensión de nivel y métrica que tenga sentido para su aplicación y conjunto de datos.
title: Configuración de un explorador de rutas
uuid: 1ba3fb6e-b76f-428f-b6ec-077669c3b305
exl-id: be6a68f7-e3e3-4207-a112-3a4fdd5c5f57
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '422'
ht-degree: 1%

---

# Configuración de un explorador de rutas{#configure-a-path-browser}

{{eol}}

Los exploradores de rutas se pueden configurar para que funcionen con cualquier combinación de dimensión base, dimensión de grupo, dimensión de nivel y métrica que tenga sentido para su aplicación y conjunto de datos.

Después de configurar un explorador de rutas, se enumera con otros exploradores de rutas en la variable [!DNL Add Visualization] para abrir el Navegador.

1. En el [!DNL Profile Manager], haga clic en **[!UICONTROL Menu]** y haga clic en **[!UICONTROL Add Visualization]** y **[!UICONTROL Path Browser]**.

   Al menos una [!DNL *.vw] reside en el directorio del explorador de rutas.

1. Haga clic con el botón derecho en la marca de verificación del archivo deseado y haga clic en **[!UICONTROL Make Local]**.
1. Haga clic con el botón derecho en la marca de verificación del archivo en la [!DNL User] y haga clic en **[!UICONTROL Open]** > **[!UICONTROL in Notepad]**.
1. Edite los parámetros del archivo utilizando el siguiente archivo de ejemplo y la tabla como guías:

   ```
   window = simpleBorderWindow: 
     client = pathBrowser: 
       Left Path = vector: 0 items
       Map = ref: wdata/model/dim/base dimension name
       Map Group = ref: wdata/model/dim/group dimension name
       Map Level = ref: wdata/model/dim/level dimension name
       Metric = ref: wdata/model/metric/metric name
       Right Path = vector: 0 items
       size = v3d: (673, 279, 0)
     pos = v3d: (714, 143, 0)
     size = v3d: (673, 298, 0)
   ```

<table id="table_1DCCB4B24B554B72A781B304B5EB155E"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Para este parámetro... </th> 
   <th colname="col2" class="entry"> Proporcione esta información... </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><i>Nombre de la dimensión base</i> </p> </td> 
   <td colname="col2"> <p>Nombre de la dimensión cuyos elementos aparecen en el explorador de rutas. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><i>Nombre de la dimensión del grupo</i> </p> </td> 
   <td colname="col2"> <p>Nombre de la dimensión que determina cómo se agrupan los elementos de la dimensión de nivel para formar las rutas en un explorador de rutas. Específicamente, los elementos de dimensión de nivel asociados con una sola ruta en un explorador de rutas no pueden abarcar más de un elemento de una dimensión de grupo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><i>Nombre de dimensión de nivel</i> </p> </td> 
   <td colname="col2"> <p>Nombre del nivel (principal) de la dimensión base cuyos elementos arrastre al explorador de rutas. A medida que sigue una ruta de un elemento de dimensión base al siguiente, pasa de un elemento de dimensión de nivel al siguiente. Al seleccionar una ruta de elementos de dimensión base, se seleccionan los datos para los elementos correspondientes de la dimensión de nivel. La selección siempre incluye los elementos de la dimensión de nivel que se relacionan con la raíz y se refina añadiendo más elementos a la ruta. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><i>Nombre de la métrica</i> </p> </td> 
   <td colname="col2"> <p>Nombre de la métrica cuyo valor para un elemento determinado es proporcional al grosor de la ruta que conduce a ese elemento. </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>Para obtener más información sobre la dimensión base, la dimensión de grupo, la dimensión de nivel y la métrica de un navegador de rutas, consulte [Exploradores de rutas](../../../home/c-get-started/c-analysis-vis/c-path-browsers/c-path-browsers.md#concept-f2e9fdafed6e49c2bd111ab425cd6e2b).

1. En el Bloc de notas, haga clic en **[!UICONTROL File]** > **[!UICONTROL Save As]** para guardar el archivo con un nuevo nombre basado en la dimensión de grupo, es decir, *Nombre de la dimensión del grupo*.vw.

   Asegúrese de guardar el archivo en el directorio del explorador de rutas.

   >[!NOTE]
   >
   >Para asegurarse de que el explorador de rutas se guarde como un [!DNL *.vw] en el [!DNL Save As] , establezca Guardar como tipo en Todos los archivos.

1. (Opcional) Para que los cambios estén disponibles para todos los usuarios del perfil de trabajo, en la variable [!DNL Profile Manager], haga clic con el botón derecho en la marca de verificación del archivo en la variable [!DNL User] y haga clic en **[!UICONTROL Save to]** > *&lt;**[!UICONTROL working profile name]**>*.
