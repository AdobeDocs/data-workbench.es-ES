---
description: Información conceptual sobre subconjuntos.
solution: Analytics
title: Aspectos básicos de los subconjuntos
topic: Data workbench
uuid: ed185b63-dbb3-4ed4-9403-cf4dc8be2ff1
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Aspectos básicos de los subconjuntos{#understanding-subsets}

Información conceptual sobre subconjuntos.

Cuando utilice un subconjunto, tenga en cuenta lo siguiente:

* Todos los puntos de referencia ahora están relacionados con el subconjunto, no con todo el conjunto de datos, lo que resulta mucho más útil al analizar un subconjunto específico. Consulte [Explicación de los puntos de referencia](../../../../home/c-get-started/c-vis/c-ustd-benchmks.md#concept-c7b0f4102e92458096f8c4765cbe2914).
* El uso de un subconjunto afecta a todas las áreas de trabajo porque el subconjunto se aplica de forma global a Área de trabajo de datos.
* Los subconjuntos solo afectan a las métricas y a las dimensiones denormalizadas, no a las dimensiones normales.
* Al utilizar [!DNL Report], los subconjuntos no afectan a los datos de los informes publicados para que otros los vean.
* Una vez aplicado, el subconjunto estará en vigor para todo el trabajo subsiguiente en el perfil, incluida la próxima vez que abra esta instancia de Área de trabajo de datos, hasta que la elimine.
* El único lugar que indica que se ha aplicado un subconjunto es el menú contextual al que se accede haciendo clic con el botón derecho en un espacio de trabajo.

   ![](assets/mnu_Subset.png)

* Debe estar trabajando en línea para cambiar o eliminar un subconjunto. Si trabaja sin conexión y ha aplicado un subconjunto, no podrá ver los resultados de todo el conjunto de datos. Consulte [Trabajar sin conexión y en línea](../../../../home/c-get-started/c-off-on.md#concept-cef8758ede044b18b3558376c5eb9f54).

   >[!NOTE]
   >
   >El tamaño del subconjunto está limitado a la cantidad de datos del filtro que reside en un único servidor de Área de trabajo de datos. Por lo tanto, si el conjunto de datos abarca un clúster de servidores de Área de trabajo de datos, los datos del subconjunto provienen de un solo servidor de Área de trabajo de datos del clúster.

Un usuario de un gran minorista desea crear un subconjunto (caché local) de una semana de trabajo concreta de datos y, a continuación, ejecutar consultas solo en esa semana de datos. Para ello, el usuario crea un subconjunto para los días de interés.

El siguiente ejemplo muestra un gráfico de barras de Visitantes con el paso del tiempo y una leyenda de métrica de tráfico. La primera figura no contiene selecciones: se representan todos los datos del conjunto de datos. La segunda figura muestra los datos de un subconjunto de Días = {...} por Visitantes, en el que Días se basa en una selección de los elementos del 1 de abril al 5 de abril en la dimensión Día.

![](assets/client-sub1.png)

