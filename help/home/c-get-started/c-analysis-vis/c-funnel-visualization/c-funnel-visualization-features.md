---
description: La visualización de canal incluye funciones para crear un canal con varias dimensiones, números de visitante sin procesar, porcentaje de visitantes en cada paso y ámbitos independientes.
title: Funciones de canal
uuid: 7d2f5ff9-95d3-41f5-931c-689f140714c2
exl-id: e78dcefe-6f92-45de-9990-0beac09ad82f
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '552'
ht-degree: 0%

---

# Funciones de canal{#funnel-features}

La visualización de canal incluye funciones para crear un canal con varias dimensiones, números de visitante sin procesar, porcentaje de visitantes en cada paso y ámbitos independientes.

Estas son las funciones básicas de la visualización del canal.

![](assets/funnel_visualization_capture.png)

<table id="table_49A08740CEE74D64B6F9C37CD91F1AE5"> 
 <tbody> 
  <tr> 
   <td colname="col01"> <img id="image_0C1701833FE049708CE38ADEB5EC7EEF" src="assets/funnel_visualization_capture_1.png" /> </td> 
   <td colname="col1"> Primer elemento </td> 
   <td colname="col2"> Primer paso del canal en el proceso. </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <img id="image_EF8AF94D833B4A249959B76F8FAF2318" src="assets/funnel_visualization_capture_2.png" /> </td> 
   <td colname="col1"> Tercer elemento </td> 
   <td colname="col2">Tercer paso del canal en el proceso. <p><p>Nota:  Los elementos seleccionados no tienen que pertenecer a la misma dimensión. </p></p></td> 
  </tr> 
  <tr> 
   <td colname="col01"> <img id="image_F3C5130B52234FAC9DEB50279F94FF90" src="assets/funnel_visualization_capture_3.png" /> </td> 
   <td colname="col1"> Porcentaje de visitas en el orden previsto </td> 
   <td colname="col2"> El porcentaje que completó la ruta definida se muestra en tres ámbitos. </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <img id="image_3F030396CEB14528980F5B965113BD36" src="assets/funnel_visualization_capture_4.png" /> </td> 
   <td colname="col1"> Explorador de visitas en el orden previsto </td> 
   <td colname="col2">Flecha de visitas en el orden previsto. Haga clic con el botón derecho y seleccione <span class="uicontrol"> Agregar explorador de rutas</span> para ver qué otras rutas tomaron los visitantes. </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <img id="image_0DA7567BDBDF4BEF9CA840D2F88A414E" src="assets/funnel_visualization_capture_5.png" /> </td> 
   <td colname="col1"> Visitas en el orden previsto porcentual </td> 
   <td colname="col2">Porcentajes que describen tres ámbitos de abandonos para usuarios que no completaron la ruta. <p>Los porcentajes se presentan en tres ámbitos: </p><p><img id="image_B85C46DDF12C41D5BF213D5F9DC04967" placement="break" src="assets/funnel_path_browser_5.png" /></p><p><img id="image_BC37007D7B4B425C8F87905CE68F0114" src="assets/funnel_path_browser_6.png" /> El porcentaje de visitas en el orden previsto desde el paso anterior a este paso. </p><p><img id="image_B10866B083424360AFF1B19E836A94CF" src="assets/funnel_path_browser_7.png" /> El porcentaje de visitas en el orden previsto desde el primer paso del canal. </p><p><img id="image_19B9AE916B584E18A82F5D5E10674414" src="assets/funnel_path_browser_8.png" /> El porcentaje de visitas en el orden previsto en función del número total de visitantes. </p></td> 
  </tr> 
 </tbody> 
</table>

## Pasos de canal {#section-96a6732558dd4740b73541844f06d3ef}

Los discos de un canal representan los pasos de la navegación, los conos representan la visita en el orden previsto de un paso a otro y las flechas representan la visita en el orden previsto. Al hacer clic en un cono, se seleccionarán los usuarios que perdieron el sitio en ese momento y se incluirán en el filtro de espacio de trabajo actual. Al hacer clic en una flecha, se seleccionarán los visitantes que abandonaron el sitio.

>[!NOTE]
>
>La visualización de canal tiene un límite de ocho pasos que se pueden aplicar.

## Funciones y funcionalidad de canal adicionales {#section-22a3582db8114ca8bce77f50bbbf296a}

* **Ajuste el clip y el nivel del canal**. Seleccione la opción Embudo en el menú Visualización. Una vez creado el canal, puede hacer clic con el botón derecho en el título para ajustar el clip y el nivel a cualquier métrica contable del sistema.

   ![](assets/funnel_path_browser_9.png)

* **Arrastre más elementos**. Agregue más elementos al canal arrastrándolos y soltándolos desde la tabla del Dimension al canal utilizando las teclas `<Ctrl>` + `<Alt>`. Puede arrastrar varios pasos al mismo tiempo desde la tabla del Dimension seleccionando varios elementos (utilizando `<Ctrl>` + clic) y luego arrastrándolos a la visualización Embudo utilizando las teclas `<Ctrl>` + `<Alt>` .
* **Eliminar un paso**: Elimine los elementos haciendo clic con el botón derecho en el paso de la visualización y haciendo clic en  **Yes**.

   ![](assets/funnel_path_browser_4.png)

* **Reorganice los pasos que ha arrastrado al canal**. Simplemente haga clic en el paso para seleccionarlo y arrástrelo a otra posición para reorganizar los pasos.
* **Abra un explorador de rutas**. Puede ver más detalles sobre dónde se encuentran los clientes o dónde están fuera del proceso a través de la función [Agregar un explorador de rutas](../../../../home/c-get-started/c-analysis-vis/c-funnel-visualization/c-path-browser-funnel.md#concept-b0cedf7a28ae422696ded1258c9a4119).

* **Añada más pasos**. Puede añadir un máximo de ocho pasos a cada visualización de canal.
* **Cambiar la métrica**. La métrica se puede cambiar para que los pasos sean el recuento de visitas o alguna otra métrica en cada paso. Las opciones disponibles varían según el conjunto de datos.
* **Se muestra en una vista** tabular. Haga clic con el botón derecho en el título para mostrar el menú Visualización de canal y haga clic en **[!UICONTROL Show Tabular View]**. Una vez en la vista de tabla, puede seleccionar **[!UICONTROL Show Graph View]** para volver a la representación gráfica del canal. Para abrir la Vista tabular, haga clic con el botón derecho en el título y seleccione Mostrar vista tabular en el menú.

* **Comparar secuencias**. Una forma eficaz de comparar dos secuencias similares es mostrar sus dos visualizaciones en paralelo. También puede mostrar en paralelo la vista de tabla y la vista de gráfico mediante la función Duplicar. Para abrir, haga clic con el botón derecho en el título y seleccione Duplicate en el menú.
