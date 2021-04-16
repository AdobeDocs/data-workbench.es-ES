---
description: Un filtro binario en la matriz de correlación permite restringir los valores de una o ambas métricas correlacionadas para centrar mejor la comparación.
title: Filtro binario en la matriz de correlación
uuid: 61c3ca37-cfa2-49dc-87de-4e9a44647eca
exl-id: e693fc72-5697-4c47-a498-e0d4d875c688
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '210'
ht-degree: 5%

---

# Filtro binario en la matriz de correlación{#binary-filter-in-the-correlation-matrix}

Un filtro binario en la matriz de correlación permite restringir los valores de una o ambas métricas correlacionadas para centrar mejor la comparación.

Para establecer un filtro binario en una matriz de correlación:

1. En la matriz de correlación, haga clic con el botón derecho en el nombre de una métrica.
1. Seleccione **Editar detalles de métricas**.

   ![](assets/correlation_matrix_binary_filter.png)

   Se abrirá la ventana **[!UICONTROL Edit Correlation Metric Details]**.

   ![](assets/correlation_matrix_metric_details.png)

1. Configure un filtro binario.

   En primer lugar, haga clic en la configuración **[!UICONTROL Inactive]** . Se puede configurar el filtro como **[!UICONTROL Active]** y mostrar los campos **Comparison** y **Value**.

   A continuación, seleccione un operador **[!UICONTROL Comparison]** y establezca su **[!UICONTROL Value]** para configurar un filtro para la métrica seleccionada.

>[!IMPORTANT]
>
>El filtro binario para la Data Workbench 6.2 se ha actualizado con nuevas funciones, lo que requiere que reconstruya cualquier matriz de correlación con un filtro binario creado en versiones anteriores.

## Adición de elementos de Dimension {#section-f19f4e0368ca488e92d1e28bcc24417c}

También puede agregar un elemento de dimensión para restringir una métrica. Una métrica solo puede tener un elemento asociado.

![](assets/correlation_matrix_element.png)

Haga clic con el botón derecho en el espacio de trabajo y seleccione **Table**. Abra una dimensión con sus elementos y arrástrela a la configuración **[!UICONTROL Element]** en la ventana Editar detalles de métricas de correlación o suelte una métrica en la matriz de correlación.
