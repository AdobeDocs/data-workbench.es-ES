---
description: Las tablas de detalles permiten ver información adicional sobre un subconjunto de datos, que se define mediante las selecciones que se realizan en otras visualizaciones.
title: Tabla de detalles
uuid: 2becff5e-c78d-4ac7-8cda-814ad0193efd
exl-id: d7f0b768-f341-41e8-904b-ec98a25f7aa9
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '498'
ht-degree: 3%

---

# Tabla de detalles{#detail-table}

Las tablas de detalles permiten ver información adicional sobre un subconjunto de datos, que se define mediante las selecciones que se realizan en otras visualizaciones.

La información adicional que ve es un muestreo de todos los datos disponibles.

![](assets/vis_details.png)

En la tabla siguiente se describen los elementos de una tabla de detalles.

<table id="table_C88C7F7F5AEA4820B908923E45CC0A62"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Elemento </th> 
   <th colname="col02" class="entry"> Color </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Nivel </p> </td> 
   <td colname="col02"> <p>Rosa </p> </td> 
   <td colname="col2"> <p>Cualquier dimensión contable para la que desee ver información detallada de atributos y métricas. El nivel va precedido del número de elementos mostrados del número de elementos disponibles, por ejemplo, 6/444 indica que se están mostrando 6 elementos de un posible 444. En el ejemplo anterior, el nivel Visitantes indica que todos los detalles proporcionados se basan en el visitante. El nivel Vistas de página indica que todos los detalles proporcionados se basan en la vista de página. La visualización de varios niveles al mismo tiempo es útil cuando desea analizar datos que tienen diferentes elementos principales contables. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Atributo </p> </td> 
   <td colname="col02"> <p>Verde </p> </td> 
   <td colname="col2"> <p>Cualquier dimensión que sea de uno a varios o de uno a uno con el nivel, como Ciudad a los visitantes. Cada fila muestra el elemento relacionado con cada elemento del nivel seleccionado. En el ejemplo anterior, los atributos Dominio y Ciudad enumeran el dominio y la ciudad de cada uno de los visitantes de muestra. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Métrica </p> </td> 
   <td colname="col02"> <p>Azul </p> </td> 
   <td colname="col2"> <p>Detalles de métrica sobre el nivel que ha seleccionado. En el ejemplo anterior, con el nivel establecido en Visitantes, la métrica Vistas de página muestra el número de vistas de página para un visitante individual, mientras que el nivel Vistas de página proporciona el detalle sobre cada una de esas vistas de página. </p> </td> 
  </tr> 
 </tbody> 
</table>

Supongamos que trabaja con datos de sitios web y desea averiguar qué páginas visitaron los visitantes de determinadas ciudades y dominios durante un período de tiempo determinado.

En primer lugar, debe crear una visualización que muestre el lapso de tiempo en el que esté interesado y, a continuación, seleccionar ese lapso de tiempo. Ahora puede agregar una tabla de detalles para ver los detalles deseados para un número de visitantes de muestra en el conjunto de datos.

Para ver los detalles descritos anteriormente, debe completar los siguientes pasos:

1. Haga clic con el botón derecho en la tabla de detalles y haga clic en **[!UICONTROL Add Level]** > **[!UICONTROL Visitor]**.
1. Haga clic con el botón derecho en la tabla de detalles y haga clic en **[!UICONTROL Add Level]** > **[!UICONTROL Page View]**.
1. Haga clic con el botón derecho en el encabezado de nivel **[!UICONTROL Visitors]** y haga clic en **[!UICONTROL Add Attribute]** > **[!UICONTROL Geography]** > **[!UICONTROL Domain]**.
1. Haga clic con el botón derecho en el encabezado de nivel Visitantes y haga clic en **[!UICONTROL Add Attribute]** > **[!UICONTROL Geography]** > **[!UICONTROL City]**.
1. Haga clic con el botón derecho en el encabezado de nivel Visitantes y haga clic en **[!UICONTROL Add Metric]** > **[!UICONTROL Page Views]**.
1. Haga clic con el botón derecho en el encabezado de nivel Vistas de página y haga clic en **[!UICONTROL Add Attribute]** > **[!UICONTROL Page]** > **[!UICONTROL Page]**.

El siguiente espacio de trabajo de muestra muestra los detalles relacionados de una muestra aleatoria de seis visitantes del sitio durante el lapso de tiempo especificado.

![](assets/client-tab1.png)

## Añadir un nivel {#section-f948d3361fd84906ac4d9ebce520bfd0}

* Haga clic con el botón derecho en la tabla de detalles y haga clic en **[!UICONTROL Add Level]** > *&lt;**[!UICONTROL dimension name]**>*.

![](assets/mnu_DetailsTable_AddLevel.png)

## Eliminar un nivel {#section-a8c820e0b656451e98e5ea75373edefc}

* Haga clic con el botón derecho en el encabezado de nivel existente y haga clic en **[!UICONTROL Remove Level]** > *&lt;**[!UICONTROL dimension name]***.

![](assets/mnu_DetailsTable_Level.png)

## Agregar atributos y métricas {#section-cdda2df3c9a448d5b9770686c8b8efb3}

* Haga clic con el botón derecho en un encabezado de atributo o métrica y haga clic en **[!UICONTROL Add Attribute]** > *&lt;**[!UICONTROL attribute name]**>* o **[!UICONTROL Add Metric]** > *&lt;**[!UICONTROL metric name]**>*.

![](assets/mnu_DetailsTable.png)

## Eliminar atributos y métricas {#section-4002ac957a2846678f9940270987d651}

* Haga clic con el botón derecho en la columna que desee eliminar y haga clic en **[!UICONTROL Remove Attribute]** > *&lt;**[!UICONTROL attribute name]**>* o **[!UICONTROL Remove Metric]** > *&lt;**[!UICONTROL metric name]**>*.

![](assets/mnu_DetailsTable.png)

## Exportación a Microsoft Excel {#section-a9eaba63c88a4598836a34669ba8cac1}

Para obtener información sobre la exportación de ventanas, consulte [Exportación de datos de ventana](../../../home/c-get-started/c-wk-win-wksp/c-exp-win-data.md#concept-8df61d64ed434cc5a499023c44197349).
