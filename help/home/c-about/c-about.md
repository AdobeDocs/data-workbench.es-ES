---
description: Las métricas, las dimensiones y los filtros proporcionan un marco dentro del cual se realizan cálculos sobre los datos procesados en un conjunto de datos del área de trabajo de datos.
solution: Analytics
title: Métricas, dimensiones y filtros del área de trabajo de datos
topic: Data workbench
uuid: 3c0300a0-ae19-4817-aab8-7294e0eabdd9
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Métricas, dimensiones y filtros del área de trabajo de datos{#data-workbench-metrics-dimensions-and-filters}

Las métricas, las dimensiones y los filtros proporcionan un marco dentro del cual se realizan cálculos sobre los datos procesados en un conjunto de datos del área de trabajo de datos.

Los resultados de los cálculos definidos con esta estructura se muestran en espacios de trabajo, tableros, informes u otros resultados. En resumen, cualquier número que vea en una aplicación o desde ella es el resultado de una consulta de un conjunto de datos que involucra una métrica, una dimensión y un filtro.

En el nivel más básico, una métrica describe lo que se calcula a partir del conjunto de datos y sobre él, una dimensión desglosa los datos del conjunto de datos en categorías y un filtro describe una parte o subconjunto seleccionado de los datos en el conjunto de datos.

Cuando el servidor del área de trabajo de datos procesa los datos para crear un conjunto de datos, las dimensiones de los datos se crean y luego se actualizan de forma continua a medida que el servidor lee y procesa los nuevos datos. Las métricas y los filtros se calculan a partir de estas dimensiones de datos.

>[!CAUTION]
>
>Si redefine una métrica interna, el sistema se comportará de forma inesperada debido al valor incorrecto. Los informes no se generarán a menos que una métrica indique el 100 %. Se recomienda no cambiar las definiciones de métricas.

## Un ejemplo {#section-ecc465d1a5e34d559c1983e96fa409ec}

Imaginen un conjunto de datos que contenga información sobre todas las personas del mundo. Este conjunto de datos contiene, como mínimo, todas las personas del mundo y sus edades. Una métrica útil para calcular a partir de este conjunto de datos sería la edad promedio. La evaluación de esta métrica resultaría en un número: la edad media de la población mundial.

Al agregar una dimensión al conjunto de datos, esta información resulta más útil y manejable. Si el conjunto de datos también contiene el país de residencia de cada persona, la definición de una dimensión País permitiría segmentar a las personas en grupos para cada país del mundo. La evaluación de la métrica Edad promedio en la dimensión País daría como resultado una lista de números, uno por cada país, cada uno de los cuales representa la edad promedio de las personas en ese país.

La aplicación de un filtro (o filtro de selección) en una fórmula de métrica puede proporcionar información más detallada o permitir la definición de una nueva métrica basada en las métricas y dimensiones existentes. La evaluación de la métrica Edad promedio con un filtro de &quot;donde el país es igual que Suecia&quot; resulta en un número: la edad media de las personas en Suecia. Una métrica basada en este filtro podría ser Edad promedio sueca.

Por ejemplo:

```
Swedish_Average_Age=Average_Age[country = ‘Sweden’]
```

## Relación entre métricas, dimensiones y filtros {#section-28622596124140b280e6b993b174ef84}

En general, la evaluación de una métrica sobre una dimensión hace que esa métrica se evalúe para cada elemento de dimensión (o elemento). En el ejemplo anterior, la dimensión País tiene un elemento para cada país del mundo. La evaluación de la edad promedio por país daría como resultado la edad promedio de cada uno de los elementos (países), incluido el elemento Suecia.

Es importante tener en cuenta que cuando evalúe una métrica sobre una dimensión, recibirá el mismo resultado numérico para un elemento de dimensión específico independientemente de si evalúa esa métrica para toda la dimensión o define un filtro que corresponda a ese elemento de dimensión específico. En el ejemplo anterior, al buscar la edad media de las personas en Suecia, cualquiera de los siguientes métodos daría resultados idénticos:

* Evalúe la métrica Edad promedio en la dimensión País y luego observe el número del elemento de dimensión Suecia.
* Evalúe la métrica Edad promedio con un filtro de &quot;personas en Suecia&quot; (expresado como [!DNL Promedio_[EdadPaís=&#39;Suecia&#39;]]).

Los filtros son expresiones sintácticas que hacen referencia a una o varias dimensiones y elementos de dimensión. Como se ha visto en el ejemplo anterior, el uso de la expresión [!DNL [dimension=element]] es una forma sencilla de especificar un filtro.

Es igual de fácil aplicar este filtro para definir una nueva métrica con una expresión como [!DNL New_Metric=[MetricFilter]]. Este filtro se puede utilizar para definir una nueva métrica basada en un elemento de dimensión específico. Para utilizar el ejemplo anterior, [!DNL average_[AgeCountry=&#39;Suecia&#39;]]especifica una métrica para la edad promedio de las personas en Suecia. Si se le diera un nombre a esta métrica, como Swiss_Average_Age, se podría usar en otros cálculos como métrica. Por ejemplo, la evaluación [!DNL Swedish_Average_Age/Average_Age] resultaría en un solo número: la relación entre la edad media de las personas en Suecia y la de las personas en el resto del mundo.

Si el conjunto de datos con información sobre todas las personas del mundo también incluye una dimensión Color de ojo, la expresión [!DNL sueco_average_[AgeEye_Color=&#39;verde&#39;]] resultaría en la edad promedio de suecos con ojos verdes. También puede obtener el mismo resultado sin usar una definición de métrica intermedia aplicando un filtro diferente: [!DNL average_[AgeCountry=&#39;Suecia&#39; AND Eye_Color=&#39;verde&#39;]]. En este caso, el [!DNL AND] operador especifica una expresión de filtro que utiliza otras dos expresiones de filtro básicas.
