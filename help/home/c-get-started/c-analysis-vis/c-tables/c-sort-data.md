---
description: Pasos para ordenar los datos.
solution: Analytics
title: Ordenar datos en una tabla
topic: Data workbench
uuid: 66869478-922d-41e1-915d-3ed7bff3b08d
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Ordenar datos en una tabla{#sort-data-in-a-table}

Pasos para ordenar los datos.

Si la tabla solo tiene una dimensión, puede hacer clic en la etiqueta de la métrica en la que desee ordenar los datos.

1. Haga clic con el botón secundario en un elemento o en la etiqueta de la dimensión que desee ordenar y haga clic en **[!UICONTROL Sort]**.

   ![](assets/mnu_Table_Sort.png)

1. Haga clic en una de las opciones siguientes:

   * **[!UICONTROL By ordinal]** para ordenar los elementos según el orden natural de los elementos. Por ejemplo, los elementos de la dimensión Hora se muestran en orden cronológico. Si la dimensión no tiene orden natural, como con el referente o URI, el orden de clasificación no es útil, por lo que debe seleccionar ordenar alfabéticamente o por métrica.
   * **[!UICONTROL Alphabetically]** para ordenar la dimensión alfabéticamente por nombre de elemento.
   * **[!UICONTROL By metric]** para seleccionar una métrica por la cual desea ordenar los datos. Por ejemplo: puede ordenar la dimensión Referente según la métrica Sesiones para ver qué referentes contribuyen a la mayoría de las sesiones del sitio.

      Cuando ordena por una métrica, de forma predeterminada el orden de la tabla corresponde a los valores de la métrica afectados por la selección en ese momento. Si más adelante cambia la selección, el orden ordenado no cambia del orden original a menos que se reactive la dimensión o se active la selección dinámica. Al hacer clic en **[!UICONTROL Sort]** > **[!UICONTROL Dynamic Selection]**, la tabla se reinicia cada vez que cambia la selección.
   Para ordenar por una métrica existente en la tabla, haga clic en la etiqueta de la métrica.

1. (Opcional) Para elegir si desea ordenar en orden ascendente o descendente, haga clic con el botón derecho en un elemento o en la etiqueta de la dimensión que desee ordenar y haga clic en **[!UICONTROL Sort]** > **[!UICONTROL Order]** > **[!UICONTROL Ascending]** o **[!UICONTROL Sort]** > **[!UICONTROL Order]** > **[!UICONTROL Descending]**.

   Si la tabla solo tiene una dimensión, puede hacer clic en la etiqueta de la métrica para invertir el orden. Al volver a hacer clic en la etiqueta se invierte el orden.

