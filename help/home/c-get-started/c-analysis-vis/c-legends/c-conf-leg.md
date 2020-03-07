---
description: Las leyendas de confianza le ayudan a determinar la probabilidad de que los números que está viendo se deban al azar y a comprender las posibles desviaciones de los datos.
solution: Analytics
title: Leyendas de confianza
topic: Data workbench
uuid: 2559ff7c-6060-4fee-b509-9ae0c3912016
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Leyendas de confianza{#confidence-legends}

Las leyendas de confianza le ayudan a determinar la probabilidad de que los números que está viendo se deban al azar y a comprender las posibles desviaciones de los datos.

Incluso si no está muestreando datos, no puede extrapolar los números de un período de tiempo o subconjunto específico a otros períodos de tiempo o subconjuntos con total confianza. La leyenda de la confianza le permite explorar la probabilidad de que los números se encuentren dentro de un intervalo determinado.

Si uno piensa que los datos del mundo real son un gran experimento, el mundo real aún implica el azar, incluso cuando trabaja con números exactos. Por ejemplo: saber el número de personas que completaron una transacción entre las 8 AM y las 12 PM el martes no significa exactamente que el mismo número lo hará el martes siguiente.

La siguiente leyenda de confianza muestra detalles de confianza sobre la métrica de conversión, mientras que la siguiente tabla proporciona más información sobre el significado de cada punto de datos.

![](assets/lgd_ConfidenceLegend.png)

<table id="table_387F22C7EF4E4DE9AD810D3D9204676F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Campo </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Métrica o fórmula </p> </td> 
   <td colname="col2"> <p>El nombre de la métrica o la expresión de la métrica para la que desea ver la información de confianza. Las selecciones que realice en el espacio de trabajo se verán reflejadas en la leyenda. Este ejemplo muestra detalles sobre la métrica Conversión. </p> <p>Para obtener información sobre las reglas de sintaxis para introducir una expresión, consulte <a href="../../../../home/c-get-started/c-qry-lang-syntx/c-qry-lang-syntx.md#concept-15d1d3f5164a47d49468c5acb7299d9f"> Query Language Syntax (Sintaxis</a>del lenguaje de consulta). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Valor medido </p> </td> 
   <td colname="col2"> <p>Valor de los datos reales recopilados. En este ejemplo, la tasa de conversión para la selección actual es del 2,3 %. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Desviación estándar </p> </td> 
   <td colname="col2"> <p>Desviación estándar del valor medido. En este ejemplo, la desviación estándar de la tasa de conversión para la selección actual es 0,1%. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>El valor "true" </p> </td> 
   <td colname="col2"> <p>La probabilidad de que el valor medido se encuentre dentro del rango enumerado para cada probabilidad. En este ejemplo, si este "experimento del mundo real" se repitiera una y otra vez, podría estar un 90 % seguro de que el valor medido estaría entre el 2,1 % y el 2,4 %. </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>Al analizar los resultados de cualquier cálculo, debe tener en cuenta las siguientes advertencias: >
>* Las cifras son estimaciones. Si se repetían los mismos cálculos con un conjunto de datos diferente, se obtendría un resultado diferente. Esto se conoce como variación aleatoria.
>* Las extrapolaciones a probabilidades más altas dependen de un supuesto de normalidad que no es correcto para todas las métricas. Por lo tanto, los valores de probabilidad del 99 % son menos fiables que los valores de probabilidad del 90 %.
>
>
Si necesita números más exactos, consulte a un experto en estadísticas.

## Cambiar métricas o fórmulas {#section-7f09ff84c3514f26b78d29294e1f03d9}

* En la leyenda de confianza, haga clic en el **[!UICONTROL Metric or Formula]** campo y escriba la métrica o expresión que desee. Para ver las reglas de sintaxis de expresión, consulte Sintaxis [del lenguaje de consulta](../../../../home/c-get-started/c-qry-lang-syntx/c-qry-lang-syntx.md#concept-15d1d3f5164a47d49468c5acb7299d9f).

## Exportar a Microsoft Excel {#section-f36e2db7273740b7af278f8a2b79d564}

Para obtener información sobre la exportación de ventanas, consulte [Exportación de datos](../../../../home/c-get-started/c-wk-win-wksp/c-exp-win-data.md#concept-8df61d64ed434cc5a499023c44197349)de ventana.
