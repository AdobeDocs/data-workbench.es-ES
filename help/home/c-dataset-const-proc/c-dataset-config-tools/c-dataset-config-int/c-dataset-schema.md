---
description: La interfaz Esquema de conjunto de datos muestra las dimensiones extendidas (contables, simples, "varios a varios", numéricas, denormales y temporales) definidas en cualquier archivo de Configuración de conjunto de datos de transformación y las relaciones entre esas dimensiones.
title: Esquema del conjunto de datos
uuid: 4ef5f14b-dc19-4118-a2f2-d680ded8092c
exl-id: b80e6e8e-9147-46ec-8602-2d7e5d33f077
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '380'
ht-degree: 3%

---

# Esquema del conjunto de datos{#dataset-schema}

{{eol}}

La interfaz Esquema de conjunto de datos muestra las dimensiones extendidas (contables, simples, &quot;varios a varios&quot;, numéricas, denormales y temporales) definidas en cualquier archivo de Configuración de conjunto de datos de transformación y las relaciones entre esas dimensiones.

Además, la variable [!DNL Dataset Schema] la interfaz muestra las dimensiones derivadas que ha definido, así como cualquier dimensión ampliada que esté configurada para ocultarse.

![](assets/vis_DatasetSchema_Example.png)

Esta sección trata los siguientes temas:

* [Interpretación del tipo de dimensión mediante la interfaz de Esquema de conjunto de datos](../../../../home/c-dataset-const-proc/c-dataset-config-tools/c-dataset-config-int/c-dataset-schema.md#section-16a0a12b11334c07bec558c0b7d260b1)
* [Visualización predeterminada de una dimensión](../../../../home/c-dataset-const-proc/c-dataset-config-tools/c-dataset-config-int/c-dataset-schema.md#section-1bbb73a5cbb34ffb844eb1932db85318)
* [Visualización de una visualización específica de una dimensión](../../../../home/c-dataset-const-proc/c-dataset-config-tools/c-dataset-config-int/c-dataset-schema.md#section-d46626df90bc4c44ae60c4b71eaeac7f)

## Interpretación del tipo de Dimension mediante la interfaz de esquema del conjunto de datos {#section-16a0a12b11334c07bec558c0b7d260b1}

La tabla siguiente muestra los tipos de dimensiones y los colores en los que aparecen sus nombres en la [!DNL Dataset Schema] interfaz. También se indican los padres para las dimensiones de muestra (del ejemplo anterior).

<table id="table_20D1A9EAAED247338476C475C63255F5"> 
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
   <td colname="col3"> <p>Visitante : en este esquema, Visitante es una dimensión contable raíz. </p> <p> Sesión: la página principal es Visitante. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Denormal </td> 
   <td colname="col2"> Amarillo </td> 
   <td colname="col3"> DenormalPage - principal es Vista de página. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Derivado </td> 
   <td colname="col2"> Azul </td> 
   <td colname="col3"> Página siguiente: principal es Vista de página. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Varios a varios </td> 
   <td colname="col2"> Rosa y Verde (el origen del elemento principal es rosa, mientras que el nombre de la dimensión es verde). </td> 
   <td colname="col3"> Término de búsqueda: el principal es Sesión. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Ocultar grupos de informes </td> 
   <td colname="col2"> Verde </td> 
   <td colname="col3"> Duración exacta de la página: el elemento principal es Vista de página En este ejemplo, Duración exacta de la página es una dimensión numérica oculta. Consulte el tipo de dimensión Oculto en esta tabla. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Sencilla </td> 
   <td colname="col2"> Verde </td> 
   <td colname="col3"> Página - principal es Vista de página . </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Fecha </td> 
   <td colname="col2"> Verde </td> 
   <td colname="col3"> Hora: el elemento principal es Sesión. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Oculto </td> 
   <td colname="col2"> Las dimensiones ocultas son una versión más oscura del color de tipo de dimensión correspondiente. Por ejemplo, una dimensión numérica oculta es un verde más oscuro y menos brillante. </td> 
   <td colname="col3"> Duración exacta de la página: la página principal es Vista de página. </td> 
  </tr> 
 </tbody> 
</table>

## Visualización de la visualización predeterminada de un Dimension {#section-1bbb73a5cbb34ffb844eb1932db85318}

* En el [!DNL Dataset Schema] , haga clic en la dimensión que desee. Se muestra la visualización predeterminada. Por ejemplo, si la visualización predeterminada es una tabla que muestra Sesiones y la dimensión seleccionada y hace clic en la dimensión URI, Data Workbench muestra una tabla con URI por Sesiones.

>[!NOTE]
>
>Si desea cambiar la visualización predeterminada que se muestra, consulte el capítulo Configuración de interfaz y características de análisis en la sección *Guía del usuario de Data Workbench*.

## Visualización de una visualización específica para un Dimension {#section-d46626df90bc4c44ae60c4b71eaeac7f}

* En el [!DNL Dataset Schema] , haga clic con el botón derecho en la dimensión deseada y haga clic en **[!UICONTROL Add Visualization]** > *&lt;**[!UICONTROL visualization type]**>*.
