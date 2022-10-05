---
description: Para crear una dimensión de segmento, comience realizando una selección dentro de un espacio de trabajo y, a continuación, agregando el segmento a una visualización.
title: Creación de dimensiones de un segmento
uuid: 68dcf3bf-fbc9-4924-a0dd-d112cf366131
exl-id: 393d544e-e821-49e3-8cfb-5a3496aa7380
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '304'
ht-degree: 3%

---

# Creación de dimensiones de un segmento{#create-a-segment-dimensions}

{{eol}}

Para crear una dimensión de segmento, comience realizando una selección dentro de un espacio de trabajo y, a continuación, agregando el segmento a una visualización.

**Para crear una dimensión de segmento**

1. Agregue una visualización de segmentos al espacio de trabajo. Por ejemplo:

   ![](assets/vis_Segment.png)

1. Agregue visualizaciones al espacio de trabajo que quiera usar para definir el segmento y, a continuación, realice las selecciones que desee para definir el segmento.
1. En la visualización de segmentos, haga clic con el botón derecho en la etiqueta del segmento después del cual desea que se agregue el nuevo segmento y haga clic en **[!UICONTROL Add Segment]**.

   >[!NOTE]
   >
   >Para crear un nuevo primer segmento, haga clic con el botón derecho en el **[!UICONTROL Segments]** etiqueta y haga clic en **[!UICONTROL Add Segment]**.

   ![](assets/vis_SegmentNew.png)

   En la visualización aparece un nuevo segmento (denominado Nuevo segmento). El segmento Otro representa todos los datos que no se incluyen en los segmentos definidos: es en realidad la diferencia entre los datos de su conjunto de datos y los datos de su segmento.

1. Haga clic con el botón derecho en el segmento recién creado y haga clic en **[!UICONTROL Rename Segment]**.
1. Escriba un nombre descriptivo para el nuevo segmento en el campo de nombre.

   >[!NOTE]
   >
   >Si un valor de métrica, como un visitante en particular en [!DNL Site], cumple los criterios de varios segmentos, el valor de la métrica se incluye solo en el primer segmento de la lista que coincida.

**Para guardar la dimensión del segmento**

1. Haga clic con el botón derecho en la etiqueta Segmentos y, a continuación, haga clic en **[!UICONTROL Save Dimension]**. La variable [!DNL Save Dimension As] se abre. La ubicación de almacenamiento predeterminada es la carpeta User\*profile name*\Dimension.
1. En el [!DNL File name] , escriba un nombre descriptivo para los segmentos que está guardando como dimensión y haga clic en **[!UICONTROL Save]**.

Puede acceder a la dimensión del segmento siempre que esté trabajando con una visualización. También puede exportar datos asociados con los elementos de la dimensión guardada mediante la función de exportación de segmentos.

Para obtener más información sobre la función de exportación de segmentos e instrucciones para configurarla según sus necesidades, consulte [Configuración de segmentos para exportación](../../../../home/c-get-started/c-exp-data-seg-exp/t-config-sgts-expt.md#task-8857f221fa66463990ec9b60db6db372).
