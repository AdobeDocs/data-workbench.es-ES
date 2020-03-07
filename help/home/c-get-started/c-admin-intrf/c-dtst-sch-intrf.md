---
description: La interfaz de esquema de conjunto de datos muestra las dimensiones extendidas (recuento, simples, muchas a muchas, numéricas, denormalizadas y de tiempo) definidas en cualquier archivo de configuración de conjunto de datos de transformación y proporciona una vista de las relaciones entre esas dimensiones.
solution: Analytics
title: Interfaz de esquema de conjunto de datos
topic: Data workbench
uuid: 3726e568-d3ea-47f8-8ac4-582c97fbbe0a
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Interfaz de esquema de conjunto de datos{#dataset-schema-interface}

La interfaz de esquema de conjunto de datos muestra las dimensiones extendidas (recuento, simples, muchas a muchas, numéricas, denormalizadas y de tiempo) definidas en cualquier archivo de configuración de conjunto de datos de transformación y proporciona una vista de las relaciones entre esas dimensiones.

Además, la [!DNL Dataset Schema] interfaz muestra las dimensiones derivadas que ha definido, así como cualquier dimensión ampliada configurada para ocultarse.

![](assets/vis_DatasetSchema_Example2.png)

>[!NOTE]
>
>Puede buscar dimensiones desde el diagrama de esquema. El nombre de las dimensiones encontradas por la cadena de búsqueda se resaltan y las líneas de la clase principal cambian de color para cualquier visita individual encontrada en dimensiones secundarias subordinadas. Las dimensiones contables permanecen visibles a medida que se desplaza para proporcionar jerarquía y contexto visibles.

**Interpretación de un tipo de dimensión mediante la[!DNL Dataset Schema]interfaz**

En la tabla siguiente se muestran los tipos de dimensión y los colores en los que aparecen sus nombres en la [!DNL Dataset Schema] interfaz. También se anotan los padres para las dimensiones de muestra (del ejemplo anterior).

<table id="table_CF888522626E49A4A10D87085CAB5CC1"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Tipo de dimensión </th> 
   <th colname="col2" class="entry"> Color </th> 
   <th colname="col3" class="entry"> Dimensión de muestra y principal </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Contable </td> 
   <td colname="col2"> Rosa </td> 
   <td colname="col3"> <p>Visitante: en este esquema, Visitante es una dimensión contable raíz. </p> <p>Sesión: el elemento principal es el visitante </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Denormal </td> 
   <td colname="col2"> Amarillo </td> 
   <td colname="col3"> DenormalPage: el principal es la vista de página </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Derivado </td> 
   <td colname="col2"> Azul </td> 
   <td colname="col3"> Página siguiente: principal es Vista de página </td> 
  </tr> 
  <tr> 
   <td colname="col1"> De varios a muchos </td> 
   <td colname="col2"> Rosa y Verde (la raíz del elemento principal es rosa, mientras que el nombre de la dimensión es verde). </td> 
   <td colname="col3"> Término de búsqueda: principal es Sesión </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Numéricos </td> 
   <td colname="col2"> Verde </td> 
   <td colname="col3"> Duración exacta de la página: el elemento principal es Vista de página. En este ejemplo, la duración exacta de la página es una dimensión numérica oculta. Consulte el tipo de dimensión Oculto en esta tabla. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Simple </td> 
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
   <td colname="col3"> Duración exacta de la página: el elemento principal es la vista de página </td> 
  </tr> 
 </tbody> 
</table>

Para obtener más información sobre estos tipos de dimensión, consulte la Guía *de configuración de* Dataset.

**Visualización de la visualización predeterminada de una dimensión**

* En la [!DNL Dataset Schema] interfaz, haga clic en la dimensión deseada. Se muestra la visualización predeterminada. Por ejemplo, si la visualización predeterminada es una tabla que muestra Sesiones y la dimensión seleccionada y hace clic en la dimensión URI, Área de trabajo de datos muestra una tabla con URI por Sesiones.

   >[!NOTE]
   >
   >Si desea cambiar la visualización predeterminada que se muestra, consulte [La interfaz](../../../home/c-get-started/c-admin-intrf/c-dtst-sch-intrf.md#concept-e147b3a5b542453ca2b121e1c85bb175)de esquema del conjunto de datos.

**Visualización de una visualización específica de una dimensión**

* En la [!DNL Dataset Schema] interfaz, haga clic con el botón derecho en la dimensión deseada y haga clic en **[!UICONTROL Add Visualization]** > *&lt;**[!UICONTROL visualization type]**>*.

