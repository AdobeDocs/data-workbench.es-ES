---
description: Cree encabezados de exportación de columnas personalizados para sus archivos de exportación de segmentos a fin de añadir descripciones fáciles de entender para los segmentos exportados. Esta función de exportación también permite generar como archivos TSV y CSV.
title: Exportación de segmentos con encabezados personalizados
uuid: 186e7868-13b2-42e1-b83f-5a752ee9b407
exl-id: 1d27f926-35e1-4886-b7a6-702d9947dabb
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '210'
ht-degree: 4%

---

# Exportación de segmentos con encabezados personalizados{#segment-export-with-custom-headers}

{{eol}}

Cree encabezados de exportación de columnas personalizados para sus archivos de exportación de segmentos a fin de añadir descripciones fáciles de entender para los segmentos exportados. Esta función de exportación también permite generar como archivos TSV y CSV.

Se ha añadido una nueva funcionalidad a la exportación de segmentos, incluida la capacidad de exportar con un encabezado o en los formatos CSV y TSV.

Puede crear encabezados de columna para los archivos de exportación.

## Creación de una nueva exportación de segmentos {#section-cffff55855f8467ea468b71393ab7676}

1. Abra un espacio de trabajo y haga clic con el botón derecho **[!UICONTROL Tools]** > **[!UICONTROL Detail Table]**.

1. Haga clic con el botón derecho y seleccione **[!UICONTROL Add Level > Extended]** > Elija un elemento.
1. Haga clic con el botón derecho en el título y seleccione **[!UICONTROL Add Attribute.]** Seleccione una dimensión del menú.

1. Haga clic con el botón derecho en el título y seleccione **[!UICONTROL Add Metric.]** Seleccione una métrica en el menú .

1. Haga clic con el botón derecho en el título y seleccione **[!UICONTROL New Segment Export]**.

   ![](assets/segment_export_headers.png)

   **[!UICONTROL New Segment Export with Header]** rellena automáticamente el nombre de columna con el nombre de la métrica. **[!UICONTROL New Segment Export]** requiere que establezca un nombre personalizado. ![](assets/segment_export_with_headers.png)

   >[!NOTE]
   >
   >El campo Nombre de columna no puede dejarse vacío o el encabezado no estará presente.

1. Haga clic con el botón derecho, asigne un nombre al segmento y, a continuación, haga clic en **[!UICONTROL Save Export File]**.

   Se abrirá una ventana de exportación.

1. Haga clic con el botón derecho en el nombre de la exportación y haga clic en **Guardar como`<export filename>`**.

   ![](assets/segment_export_headers_7.png)

1. Clic con el botón derecho [!DNL Admin] > [!DNL Profile Manager] > [!DNL Expand Export]. Busque el archivo de exportación que acaba de crear y guárdelo en un perfil existente.

   ![](assets/segment_export_headers_8.png)
