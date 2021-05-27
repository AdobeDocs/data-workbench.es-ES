---
description: La interfaz Esquema de conjunto de datos muestra las dimensiones extendidas (contable, simple, de varios a varios, numéricas, denormalizadas y temporales) definidas en cualquier archivo de configuración de conjunto de datos de transformación y proporciona una vista de las relaciones entre esas dimensiones.
title: Interfaz de Esquema de conjunto de datos
uuid: 3726e568-d3ea-47f8-8ac4-582c97fbbe0a
exl-id: a8d4cf02-4ff7-4fcc-9062-425c1fe1fb28
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '414'
ht-degree: 3%

---

# Interfaz de Esquema de conjunto de datos{#dataset-schema-interface}

La interfaz Esquema de conjunto de datos muestra las dimensiones extendidas (contable, simple, de varios a varios, numéricas, denormalizadas y temporales) definidas en cualquier archivo de configuración de conjunto de datos de transformación y proporciona una vista de las relaciones entre esas dimensiones.

Además, la interfaz [!DNL Dataset Schema] muestra todas las dimensiones derivadas que haya definido, así como cualquier dimensión ampliada que esté configurada para ocultarse.

![](assets/vis_DatasetSchema_Example2.png)

>[!NOTE]
>
>Puede buscar dimensiones desde el diagrama de esquema. El nombre de las dimensiones que encuentra la cadena de búsqueda se resalta y las líneas de la clase principal cambian de color para cualquier visita individual que se encuentre en las dimensiones secundarias subordinadas. Las dimensiones contables permanecen visibles mientras se desplaza para proporcionar jerarquía y contexto visibles.

**Interpretación de un tipo de dimensión mediante la  [!DNL Dataset Schema] interfaz**

En la tabla siguiente se enumeran los tipos de dimensiones y los colores en los que aparecen sus nombres en la interfaz [!DNL Dataset Schema]. También se indican los padres para las dimensiones de muestra (del ejemplo anterior).

<table id="table_CF888522626E49A4A10D87085CAB5CC1"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Tipo de Dimension </th> 
   <th colname="col2" class="entry"> Color </th> 
   <th colname="col3" class="entry"> Dimension de muestra y principal </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Contable </td> 
   <td colname="col2"> Rosa </td> 
   <td colname="col3"> <p>Visitante : en este esquema, Visitante es una dimensión contable raíz. </p> <p>Sesión: la página principal es Visitante </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Denormal </td> 
   <td colname="col2"> Amarillo </td> 
   <td colname="col3"> DenormalPage - página principal es vista de página </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Derivado </td> 
   <td colname="col2"> Azul </td> 
   <td colname="col3"> Página siguiente: página principal es vista de página </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Varios a varios </td> 
   <td colname="col2"> Rosa y Verde (el origen del elemento principal es rosa, mientras que el nombre de la dimensión es verde). </td> 
   <td colname="col3"> Término de búsqueda: el principal es Sesión </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Numéricos </td> 
   <td colname="col2"> Verde </td> 
   <td colname="col3"> Duración exacta de la página: la página principal es Vista de página. En este ejemplo, Duración exacta de la página es una dimensión numérica oculta. Consulte el tipo de dimensión Oculto en esta tabla. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Sencilla </td> 
   <td colname="col2"> Verde </td> 
   <td colname="col3"> Página - principal es Vista de página </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Fecha </td> 
   <td colname="col2"> Verde </td> 
   <td colname="col3"> Hora - principal es Sesión </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Oculto </td> 
   <td colname="col2"> Las dimensiones ocultas son una versión más oscura del color de tipo de dimensión correspondiente. Por ejemplo, una dimensión numérica oculta es un verde más oscuro y menos brillante. </td> 
   <td colname="col3"> Duración exacta de la página: la página principal es Vista de página </td> 
  </tr> 
 </tbody> 
</table>

Para obtener más información sobre estos tipos de dimensiones, consulte la *Guía de configuración del conjunto de datos*.

**Visualización predeterminada de una dimensión**

* En la interfaz [!DNL Dataset Schema] , haga clic en la dimensión deseada. Se muestra la visualización predeterminada. Por ejemplo, si la visualización predeterminada es una tabla que muestra Sesiones y la dimensión seleccionada y hace clic en la dimensión URI, la Data Workbench muestra una tabla con URI por Sesiones.

   >[!NOTE]
   >
   >Si desea cambiar la visualización predeterminada que se muestra, consulte [Interfaz de esquema del conjunto de datos](../../../home/c-get-started/c-admin-intrf/c-dtst-sch-intrf.md#concept-e147b3a5b542453ca2b121e1c85bb175).

**Visualización de una visualización específica de una dimensión**

* En la interfaz [!DNL Dataset Schema], haga clic con el botón derecho en la dimensión deseada y haga clic en **[!UICONTROL Add Visualization]** > *&lt;**[!UICONTROL visualization type]**>*.
