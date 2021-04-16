---
description: Pasos para ordenar los datos.
title: Orden de datos en una tabla
uuid: 66869478-922d-41e1-915d-3ed7bff3b08d
exl-id: 9cacb9bc-1bad-417b-b506-ca54e644de00
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '296'
ht-degree: 5%

---

# Orden de datos en una tabla{#sort-data-in-a-table}

Pasos para ordenar los datos.

Si la tabla solo tiene una dimensión, simplemente puede hacer clic en la etiqueta de la métrica en la que desea ordenar los datos.

1. Haga clic con el botón derecho en un elemento o en la etiqueta de la dimensión que desee ordenar y haga clic en **[!UICONTROL Sort]**.

   ![](assets/mnu_Table_Sort.png)

1. Haga clic en una de las opciones siguientes:

   * **[!UICONTROL By ordinal]** para ordenar los elementos según el orden natural de los elementos. Por ejemplo, los elementos de la dimensión Hora se muestran en orden cronológico. Si la dimensión no tiene orden natural, como con el referente o URI, el orden de clasificación no es útil, por lo que debe seleccionar ordenar alfabéticamente o por métrica.
   * **[!UICONTROL Alphabetically]** para ordenar la dimensión alfabéticamente por nombre de elemento.
   * **[!UICONTROL By metric]** para seleccionar una métrica por la cual desee ordenar los datos. Por ejemplo, puede ordenar la dimensión Referente según la métrica Sesiones para ver qué referentes contribuyen a la mayoría de las sesiones del sitio.

      Al ordenar por una métrica, de forma predeterminada, el orden de la tabla corresponde a los valores de la métrica afectados por la selección en ese momento. Si más adelante cambia la selección, el orden ordenado no cambia del orden original a menos que se recurra a la dimensión o se habilite la selección dinámica. Al hacer clic en **[!UICONTROL Sort]** > **[!UICONTROL Dynamic Selection]**, la tabla se reinicia cada vez que cambia la selección.
   Para ordenar por una métrica existente en la tabla, haga clic en la etiqueta de métrica.

1. (Opcional) Para elegir si ordenar en orden ascendente o descendente, haga clic con el botón derecho en un elemento o en la etiqueta de la dimensión que desee ordenar y haga clic en **[!UICONTROL Sort]** > **[!UICONTROL Order]** > **[!UICONTROL Ascending]** o **[!UICONTROL Sort]** > **[!UICONTROL Order]** > **[!UICONTROL Descending]**.

   Si la tabla solo tiene una dimensión, simplemente puede hacer clic en la etiqueta de la métrica para invertir el orden. Al volver a hacer clic en la etiqueta, se invierte el orden.
