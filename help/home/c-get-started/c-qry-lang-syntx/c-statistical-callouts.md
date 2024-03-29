---
description: Las llamadas estadísticas miden las relaciones significativas para identificar oportunidades ocultas y variables de interés para capacidades de minería de datos más avanzadas en agrupación de audiencias y puntuación de respuestas de visitantes.
title: Llamadas estadísticas
uuid: 04911ac4-bc3f-4813-800b-087d9668a782
exl-id: d4ed540e-f837-4db9-a81e-b8a30c15f270
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '273'
ht-degree: 22%

---

# Llamadas estadísticas{#statistical-callouts}

{{eol}}

Las llamadas estadísticas miden las relaciones significativas para identificar oportunidades ocultas y variables de interés para capacidades de minería de datos más avanzadas en agrupación de audiencias y puntuación de respuestas de visitantes.

Las llamadas estadísticas amplían los algoritmos para que se puedan correlacionar más tipos de datos, como variables binomiales (sí/no, 0/1 o comprador/no comprador) correlacionadas con métricas contables (visitas, pedidos o descargas).

Para agregar llamadas estadísticas:

1. En una tabla, haga clic con el botón derecho en el encabezado de métrica.
1. Select **[!UICONTROL Statistics]** y, a continuación, seleccione o borre las marcas de verificación para cada configuración necesaria. Todos los elementos de la llamada de visualización están seleccionados como la configuración predeterminada.

   ![](assets/statistical_callouts.png)

La llamada puede devolver valores estadísticos incluidos en las columnas del conjunto de datos.

<table id="table_B2A4F9D5938D4756A81ACF6F4D77E63D">
 <thead>
  <tr>
   <th colname="col1" class="entry"> Cálculo </th>
   <th colname="col2" class="entry"> Descripción </th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <td colname="col1"> Recuento </td>
   <td colname="col2"><p>Devuelve el número de filas de un conjunto de datos. </p></td>
  </tr>
  <tr>
   <td colname="col1"> Máximo </td>
   <td colname="col2"><p> Identifica el valor de métrica máximo en todos los elementos de la dimensión. </p></td>
  </tr>
  <tr>
   <td colname="col1"> Mínimo </td>
   <td colname="col2"><p> Identifica el valor de métrica mínimo en todos los elementos de la dimensión. </p></td>
  </tr>
  <tr>
   <td colname="col1"> Media </td>
   <td colname="col2"><p> La media es la media aritmética de los valores de Métrica de los elementos del Dimension, calculada por la suma total dividida por el recuento (suma/recuento). </p></td>
  </tr>
  <tr>
   <td colname="col1"> Desviación estándar </td>
   <td colname="col2"> La desviación estándar muestra cuánta variación existe con respecto a la media esperada. Una desviación estándar baja muestra puntos de datos cercanos a la media. Una desviación estándar alta muestra que los puntos de datos se reparten entre un gran rango de valores. </td>
  </tr>
  <tr>
   <td colname="col1"> Total </td>
   <td colname="col2"><p> Devuelve la suma total de los valores de Métrica. </p></td>
  </tr>
  <tr>
   <td colname="col1"> Varianza </td>
   <td colname="col2"><p> Medición de la varianza de los valores de la métrica respecto a la media de la métrica para esa dimensión. Es igual al cuadrado de la desviación estándar. </p></td>
  </tr>
 </tbody>
</table>
