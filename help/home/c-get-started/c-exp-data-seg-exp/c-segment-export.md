---
description: Cree encabezados de exportación de columnas personalizados para los archivos de exportación de segmentos a fin de agregar descripciones fáciles de entender para los segmentos exportados. Esta función de exportación también le permite generar como archivos TSV y CSV.
title: Exportación de segmentos con encabezados personalizados
uuid: 186e7868-13b2-42e1-b83f-5a752ee9b407
translation-type: tm+mt
source-git-commit: 8f5c69541bdd97aefbad3840f75f06846615f222
workflow-type: tm+mt
source-wordcount: '210'
ht-degree: 4%

---


# Exportación de segmentos con encabezados personalizados{#segment-export-with-custom-headers}

Cree encabezados de exportación de columnas personalizados para los archivos de exportación de segmentos a fin de agregar descripciones fáciles de entender para los segmentos exportados. Esta función de exportación también le permite generar como archivos TSV y CSV.

Se ha añadido una nueva funcionalidad a la exportación de segmentos, incluida la capacidad de exportar con un encabezado o en los formatos CSV y TSV.

Puede crear encabezados de columna para los archivos de exportación.

## Creación de una nueva exportación de segmentos {#section-cffff55855f8467ea468b71393ab7676}

1. Abra un espacio de trabajo y haga clic con el botón derecho **[!UICONTROL Tools]** > **[!UICONTROL Detail Table]**.

1. Haga clic con el botón derecho y seleccione **[!UICONTROL Add Level > Extended]** > Elegir un elemento.
1. Haga clic con el botón derecho en el título y seleccione **[!UICONTROL Add Attribute.]** Seleccionar una dimensión en el menú.

1. Haga clic con el botón derecho en el título y seleccione **[!UICONTROL Add Metric.]** Seleccionar una métrica en el menú.

1. Haga clic con el botón derecho en el título y seleccione **[!UICONTROL New Segment Export]**.

   ![](assets/segment_export_headers.png)

   **[!UICONTROL New Segment Export with Header]** rellena automáticamente el Nombre de columna con el nombre de la métrica. **[!UICONTROL New Segment Export]** requiere que establezca un nombre personalizado. ![](assets/segment_export_with_headers.png)

   >[!NOTE]
   >
   >El campo Nombre de columna no puede dejarse vacío o el encabezado no estará presente.

1. Haga clic con el botón secundario, asigne un nombre al segmento y, a continuación, haga clic en **[!UICONTROL Save Export File]**.

   Se abrirá una ventana de exportación.

1. Haga clic con el botón secundario en el nombre de exportación y haga clic en **Guardar como`<export filename>`**.

   ![](assets/segment_export_headers_7.png)

1. Right-click [!DNL Admin] > [!DNL Profile Manager] > [!DNL Expand Export]. Busque el archivo de exportación que acaba de crear y guárdelo en un perfil existente.

   ![](assets/segment_export_headers_8.png)

