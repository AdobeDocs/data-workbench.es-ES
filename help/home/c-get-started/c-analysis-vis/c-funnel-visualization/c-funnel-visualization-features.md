---
description: La visualización de canal incluye funciones para crear un canal con varias dimensiones, números de visitantes sin procesar, porcentaje de visitantes en cada paso y ámbitos independientes.
solution: Analytics
title: Funciones de canal
topic: Data workbench
uuid: 7d2f5ff9-95d3-41f5-931c-689f140714c2
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Funciones de canal{#funnel-features}

La visualización de canal incluye funciones para crear un canal con varias dimensiones, números de visitantes sin procesar, porcentaje de visitantes en cada paso y ámbitos independientes.

Estas son las características básicas de la visualización del canal.

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
   <td colname="col2">Flecha de visitas en el orden previsto. Haga clic con el botón derecho y seleccione <span class="uicontrol"> Agregar navegador</span> de ruta para ver qué otros visitantes tomaron la ruta. </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <img id="image_0DA7567BDBDF4BEF9CA840D2F88A414E" src="assets/funnel_visualization_capture_5.png" /> </td> 
   <td colname="col1"> Porcentaje de visitas en el orden previsto </td> 
   <td colname="col2">Porcentajes que describen tres ámbitos de visitas en el orden previsto para usuarios que no completaron la ruta. <p>Los porcentajes se presentan en tres ámbitos: </p><p><img id="image_B85C46DDF12C41D5BF213D5F9DC04967" placement="break" src="assets/funnel_path_browser_5.png" /></p><p><img id="image_BC37007D7B4B425C8F87905CE68F0114" src="assets/funnel_path_browser_6.png" /> Porcentaje de visitas en el orden previsto desde el paso anterior a este paso. </p><p><img id="image_B10866B083424360AFF1B19E836A94CF" src="assets/funnel_path_browser_7.png" /> Porcentaje de visitas en el orden previsto desde el primer paso del canal. </p><p><img id="image_19B9AE916B584E18A82F5D5E10674414" src="assets/funnel_path_browser_8.png" /> El porcentaje de visitas en el orden previsto en función del número total de visitantes. </p></td> 
  </tr> 
 </tbody> 
</table>

## Pasos del canal {#section-96a6732558dd4740b73541844f06d3ef}

Los discos de un canal representan los pasos de la navegación, los conos representan las visitas en el orden previsto de un paso a otro y las flechas representan las visitas en el orden previsto. Al hacer clic en un cono, se seleccionarán los usuarios que se perdieron en ese punto e se incluirán en el filtro de espacio de trabajo actual. Al hacer clic en una flecha, se seleccionarán los visitantes que se hayan quedado sin página.

>[!NOTE]
>
>La visualización de canal tiene un límite de ocho pasos que se pueden aplicar.

## Funciones y características adicionales del canal {#section-22a3582db8114ca8bce77f50bbbf296a}

* **Ajuste el clip y el nivel del canal**. Seleccione la opción Canal en el menú Visualización. Una vez creado el canal, puede hacer clic con el botón derecho en el título para ajustar el clip y el nivel a cualquier métrica contable del sistema.

   ![](assets/funnel_path_browser_9.png)

* **Arrastre más elementos**. Agregue más elementos al canal arrastrándolos y soltándolos de la tabla Dimensión al canal mediante las teclas `<Ctrl>` + `<Alt>` . Puede arrastrar varios pasos al mismo tiempo desde la tabla Dimensión seleccionando varios elementos (con `<Ctrl>` + clic) y luego arrastrándolos a la visualización Embudo con las teclas `<Ctrl>` + `<Alt>` .
* **Eliminar un paso**: Elimine los elementos haciendo clic con el botón derecho en el paso de la visualización y haciendo clic en **Sí**.

   ![](assets/funnel_path_browser_4.png)

* **Reorganice los pasos arrastrados al canal**. Simplemente haga clic en el paso para seleccionarlo y arrástrelo a otra posición para reorganizar los pasos.
* **Abra un explorador** de rutas. Puede ver más detalles sobre dónde los clientes atraviesan o salen del proceso a través de la función [Agregar un navegador](../../../../home/c-get-started/c-analysis-vis/c-funnel-visualization/c-path-browser-funnel.md#concept-b0cedf7a28ae422696ded1258c9a4119) de rutas.

* **Agregue más pasos**. Puede agregar un máximo de ocho pasos a cada visualización de canal.
* **Cambie la métrica**. La métrica se puede cambiar para que los pasos sean el recuento de visitas o alguna otra métrica en cada paso. Las opciones disponibles varían según el conjunto de datos.
* **Se muestra en una vista** tabular. Haga clic con el botón secundario en el título para mostrar el menú Visualización de canal y haga clic en **[!UICONTROL Show Tabular View]**. Una vez en la vista de tabla, puede seleccionar **[!UICONTROL Show Graph View]** volver a la representación gráfica del canal. Para abrir la vista Tabla, haga clic con el botón derecho en el título y seleccione Mostrar vista Tabla en el menú.

* **Compare secuencias**. Una manera eficaz de comparar dos secuencias similares es mostrar las dos visualizaciones una al lado de la otra. También puede mostrar la vista de tabla y la vista de gráfico en paralelo mediante la función Duplicar. Para abrir, haga clic con el botón derecho en el título y seleccione Duplicar en el menú.
