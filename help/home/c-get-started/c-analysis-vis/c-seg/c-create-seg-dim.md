---
description: Para crear una dimensión de segmento, comience haciendo una selección dentro de un espacio de trabajo y luego agregando el segmento a una visualización.
solution: Analytics
title: Creación de dimensiones de segmentos
topic: Data workbench
uuid: 68dcf3bf-fbc9-4924-a0dd-d112cf366131
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Creación de dimensiones de segmentos{#create-a-segment-dimensions}

Para crear una dimensión de segmento, comience haciendo una selección dentro de un espacio de trabajo y luego agregando el segmento a una visualización.

**Para crear una dimensión de segmento**

1. Agregue una visualización de segmentos al espacio de trabajo. Por ejemplo:

   ![](assets/vis_Segment.png)

1. Agregue visualizaciones al espacio de trabajo que desee utilizar para definir el segmento y, a continuación, realice las selecciones que desee para definirlo.
1. En la visualización de segmentos, haga clic con el botón secundario en la etiqueta del segmento después del cual desee agregar el nuevo segmento y haga clic en **[!UICONTROL Add Segment]**.

   >[!NOTE]
   >
   >Para crear un nuevo primer segmento, haga clic con el botón secundario en la etiqueta **[!UICONTROL Segments]** y haga clic en **[!UICONTROL Add Segment]**.

   ![](assets/vis_SegmentNew.png)

   En la visualización aparece un nuevo segmento (denominado Nuevo segmento). El segmento Otro representa todos los datos no incluidos en los segmentos definidos: es la diferencia efectiva entre los datos del conjunto de datos y los datos del segmento.

1. Haga clic con el botón secundario en el segmento recién creado y haga clic en **[!UICONTROL Rename Segment]**.
1. Escriba un nombre descriptivo para el nuevo segmento en el campo de nombre.

   >[!NOTE]
   >
   >Si un valor de métrica, como un visitante en particular en [!DNL Site], cumple los criterios de varios segmentos, el valor de la métrica se incluye solamente en el primer segmento de la lista que coincida.

**Para guardar la dimensión de segmento**

1. Haga clic con el botón secundario en la etiqueta Segmentos y haga clic en **[!UICONTROL Save Dimension]**. Aparecerá la [!DNL Save Dimension As] ventana. La ubicación de almacenamiento predeterminada es la carpeta User\*profile name*\Dimensions.
1. En el [!DNL File name] campo, escriba un nombre descriptivo para los segmentos que está guardando como dimensión y haga clic en **[!UICONTROL Save]**.

Puede acceder a la dimensión de segmento siempre que esté trabajando con una visualización. También puede exportar datos asociados con los elementos de la dimensión guardada mediante la función de exportación de segmentos.

Para obtener más información sobre la función de exportación de segmentos e instrucciones para configurarla según sus necesidades, consulte [Configuración de segmentos para exportación](../../../../home/c-get-started/c-exp-data-seg-exp/t-config-sgts-expt.md#task-8857f221fa66463990ec9b60db6db372).
