---
description: La interfaz de esquema de conjunto de datos muestra las dimensiones extendidas (recuento, simples, muchas a muchas, numéricas, denormalizadas y temporales) definidas en cualquier archivo de configuración de conjunto de datos de transformación y las relaciones entre esas dimensiones.
solution: Analytics
title: Esquema de conjunto de datos
topic: Data workbench
uuid: 4ef5f14b-dc19-4118-a2f2-d680ded8092c
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Esquema de conjunto de datos{#dataset-schema}

La interfaz de esquema de conjunto de datos muestra las dimensiones extendidas (recuento, simples, muchas a muchas, numéricas, denormalizadas y temporales) definidas en cualquier archivo de configuración de conjunto de datos de transformación y las relaciones entre esas dimensiones.

Además, la [!DNL Dataset Schema] interfaz muestra las dimensiones derivadas que ha definido, así como cualquier dimensión ampliada configurada para ocultarse.

![](assets/vis_DatasetSchema_Example.png)

Esta sección analiza los siguientes temas:

* [Interpretación del tipo de dimensión mediante la interfaz de esquema de conjunto de datos](../../../../home/c-dataset-const-proc/c-dataset-config-tools/c-dataset-config-int/c-dataset-schema.md#section-16a0a12b11334c07bec558c0b7d260b1)
* [Visualización de la visualización predeterminada de una dimensión](../../../../home/c-dataset-const-proc/c-dataset-config-tools/c-dataset-config-int/c-dataset-schema.md#section-1bbb73a5cbb34ffb844eb1932db85318)
* [Visualización de una visualización específica de una dimensión](../../../../home/c-dataset-const-proc/c-dataset-config-tools/c-dataset-config-int/c-dataset-schema.md#section-d46626df90bc4c44ae60c4b71eaeac7f)

## Interpretación del tipo de dimensión mediante la interfaz de esquema del conjunto de datos {#section-16a0a12b11334c07bec558c0b7d260b1}

En la tabla siguiente se muestran los tipos de dimensión y los colores en los que aparecen sus nombres en la [!DNL Dataset Schema] interfaz. También se anotan los padres para las dimensiones de muestra (del ejemplo anterior).

<table id="table_20D1A9EAAED247338476C475C63255F5"> 
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
   <td colname="col3"> <p>Visitante: en este esquema, Visitante es una dimensión contable raíz. </p> <p> Sesión: principal es visitante. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Denormal </td> 
   <td colname="col2"> Amarillo </td> 
   <td colname="col3"> DenormalPage: el elemento principal es la vista de página. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Derivado </td> 
   <td colname="col2"> Azul </td> 
   <td colname="col3"> Página siguiente: principal es Vista de página. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> De varios a muchos </td> 
   <td colname="col2"> Rosa y Verde (la raíz del elemento principal es rosa, mientras que el nombre de la dimensión es verde). </td> 
   <td colname="col3"> Término de búsqueda: principal es Sesión. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Numéricos </td> 
   <td colname="col2"> Verde </td> 
   <td colname="col3"> Duración exacta de la página: principal es Vista de página En este ejemplo, Duración exacta de la página es una dimensión numérica oculta. Consulte el tipo de dimensión Oculto en esta tabla. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Simple </td> 
   <td colname="col2"> Verde </td> 
   <td colname="col3"> Página - principal es Vista de página. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Fecha </td> 
   <td colname="col2"> Verde </td> 
   <td colname="col3"> Hora - principal es Sesión. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Oculto </td> 
   <td colname="col2"> Las dimensiones ocultas son una versión más oscura del color de tipo de dimensión correspondiente. Por ejemplo, una dimensión numérica oculta es un verde más oscuro y menos brillante. </td> 
   <td colname="col3"> Duración exacta de la página: el elemento principal es Vista de página. </td> 
  </tr> 
 </tbody> 
</table>

## Visualización de la visualización predeterminada de una dimensión {#section-1bbb73a5cbb34ffb844eb1932db85318}

* En la [!DNL Dataset Schema] interfaz, haga clic en la dimensión deseada. Se muestra la visualización predeterminada. Por ejemplo, si la visualización predeterminada es una tabla que muestra Sesiones y la dimensión seleccionada y hace clic en la dimensión URI, el área de trabajo de datos muestra una tabla con URI por Sesiones.

>[!NOTE]
>
>Si desea cambiar la visualización predeterminada que se muestra, consulte el capítulo Configuración de interfaz y características de análisis en la Guía *del usuario de Área de trabajo de* datos.

## Visualización de una visualización específica para una dimensión {#section-d46626df90bc4c44ae60c4b71eaeac7f}

* En la [!DNL Dataset Schema] interfaz, haga clic con el botón derecho en la dimensión deseada y haga clic en **[!UICONTROL Add Visualization]** > *&lt;**[!UICONTROL visualization type]**>*.

