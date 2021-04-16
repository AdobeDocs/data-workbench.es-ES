---
description: Las llamadas llaman la atención sobre un elemento de dimensión en particular creando una nueva visualización con una selección virtual de un elemento de dimensión en particular en una visualización.
title: Configuración de una llamada
uuid: 779764bd-86c3-49cf-aabc-edb39caf0490
exl-id: 509163b2-0bd1-47b4-8612-aac460a501cc
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '492'
ht-degree: 1%

---

# Configuración de una llamada{#configure-a-callout}

Las llamadas llaman la atención sobre un elemento de dimensión en particular creando una nueva visualización con una selección virtual de un elemento de dimensión en particular en una visualización.

Puede añadir o editar llamadas configurando los archivos de llamada almacenados en una carpeta de instalación Profiles\*profile name*\Context\Callout folder of the [!DNL Server]. Las llamadas que llaman la atención sobre una métrica en particular en una visualización de hoja de cálculo se denominan llamadas de métricas. Los archivos de llamadas de métricas se almacenan en Profiles\*profile name*\Context\Metric Callout folder.

Para obtener instrucciones para agregar una llamada o una llamada de métrica a una visualización, consulte [Adición de llamadas a un espacio de trabajo](../../../home/c-get-started/c-vis/c-call-wkspc.md#concept-212b09e763044d938987b4a9c658adc0).

**Para crear un nuevo tipo de llamada**

1. En cualquier espacio de trabajo, cree una visualización que contenga los datos que desea que aparezcan en el nuevo tipo de llamada. Por ejemplo, si desea que la llamada sea una tabla, cree una visualización de tabla que muestre la métrica y la dimensión deseadas.
1. Haga clic con el botón derecho en el borde superior de la ventana de llamada y haga clic en **[!UICONTROL Save]**.
1. En la ventana [!DNL Save], haga clic en ![](assets/btn_folder_up.png), haga doble clic en **[!UICONTROL Context]** y, a continuación, haga doble clic en **[!UICONTROL Callout]**. En el campo [!DNL File Name], escriba un nombre para el archivo y haga clic en **[!UICONTROL Save]**. El archivo de llamada se guarda en User\*working profile name*\Context\Callout folder.

   >[!NOTE]
   >
   >Al asignar un nombre a la llamada, elija un nombre descriptivo que refleje el tipo de visualización y la métrica y la dimensión que se muestra. Por ejemplo, si desea crear una llamada a partir de una visualización de tabla que muestre la métrica Sesiones a lo largo de la dimensión Día , puede asignar el nombre &quot;Sesiones por tabla de día&quot; a la llamada.

1. (Opcional) Para que este cambio esté disponible para todos los usuarios del perfil de trabajo:

   1. En [!DNL Profile Manager], haga clic en **[!UICONTROL Context]** y, a continuación, haga clic en **[!UICONTROL Callout]**. Esta carpeta contiene todos los archivos de visualización ( [!DNL .vw]) que definen los tipos de llamada existentes.

   1. Haga clic con el botón derecho en la marca de verificación situada junto al nombre de archivo de la nueva llamada en la columna [!DNL User] y haga clic en **[!UICONTROL Save to]** > *&lt;**[!UICONTROL working profile name]**>*.

**Para cambiar una llamada a una llamada de métrica**

1. En [!DNL Profile Manager], haga clic en **[!UICONTROL Context]** y, a continuación, haga clic en **[!UICONTROL Callout]**. Esta carpeta contiene todos los archivos de visualización ( [!DNL .vw]) que definen los tipos de llamada existentes.

1. Haga clic con el botón derecho en la marca de verificación situada junto al nombre del archivo del tipo de llamada que desea cambiar y haga clic en **[!UICONTROL Make Local]**. Una vez descargado el archivo en el equipo local, aparece una marca de verificación en la columna [!DNL User].

1. Haga clic con el botón derecho en la marca de verificación situada junto al nombre del archivo en la columna [!DNL User] y haga clic en **[!UICONTROL Open]** > **[!UICONTROL In Notepad]**.

1. Busque la entrada [!DNL metric_y = ref:] en el archivo de llamada y reemplace el valor existente por la palabra Métrica. El texto resaltado en el siguiente fragmento de archivo muestra dónde se inserta esta palabra.

   ```
   window = simpleBorderWindow: 
     client = graph: 
       bars = bool: true
       dim_x = ref: wdata/model/dim/dimension name
       lines = bool: false
       metrics = vector: 1 items
         0 = gr_metric: 
           metric_y = ref: Metric
           yaxis = axisLegend: 
             max_value = double: maximum y-value
             min_value = double: minimum y-value
             zoom_max = double: maximum y-zoom
             zoom_min = double: minimum y-zoom
   . . . 
   ```

1. Haga clic **[!UICONTROL File]** > **[!UICONTROL Save As]**. En la ventana **[!UICONTROL Save As]**, haga clic una vez y, a continuación, haga doble clic en **[!UICONTROL Metric Callout]**. En el campo [!DNL File Name], escriba un nombre para el archivo y haga clic en **[!UICONTROL Save]**. El archivo de llamada de métrica se guarda en el User\*working profile name*\Context\Metric Callout folder.

1. (Opcional) Para que esta llamada de métrica esté disponible para todos los usuarios del perfil de trabajo, en [!DNL Profile Manager], haga clic con el botón derecho en la marca de verificación situada junto al nombre del archivo en la columna [!DNL User] y haga clic en **[!UICONTROL Save to]** > *&lt;**[!UICONTROL working profile name]***.
