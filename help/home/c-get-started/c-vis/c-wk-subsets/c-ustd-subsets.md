---
description: Información conceptual sobre subconjuntos.
title: Aspectos básicos de los subconjuntos
uuid: ed185b63-dbb3-4ed4-9403-cf4dc8be2ff1
exl-id: a75b36f9-d34d-4a4a-8a2c-15ae5461823c
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '333'
ht-degree: 1%

---

# Aspectos básicos de los subconjuntos{#understanding-subsets}

{{eol}}

Información conceptual sobre subconjuntos.

Cuando utilice un subconjunto, tenga en cuenta lo siguiente:

* Todos los puntos de referencia ahora están relacionados con el subconjunto, no con todo el conjunto de datos, lo que resulta mucho más útil al analizar un subconjunto específico. Consulte [Explicación de los puntos de referencia](../../../../home/c-get-started/c-vis/c-ustd-benchmks.md#concept-c7b0f4102e92458096f8c4765cbe2914).
* El uso de un subconjunto afecta a todos los espacios de trabajo, ya que el subconjunto se aplica globalmente a la Data Workbench.
* Los subconjuntos solo afectan a las métricas y a las dimensiones denormalizadas, no a las dimensiones normales.
* Al usar [!DNL Report], los subconjuntos no afectan a los datos de los informes publicados para que los demás los vean.
* Una vez aplicado, el subconjunto estará en vigor para todas las tareas posteriores del perfil, incluida la próxima vez que abra esta instancia de Data Workbench, hasta que la elimine.
* El único lugar que indica que se ha aplicado un subconjunto es el menú contextual al que se accede haciendo clic con el botón derecho en un espacio de trabajo.

   ![](assets/mnu_Subset.png)

* Debe estar trabajando en línea para cambiar o quitar un subconjunto. Si está trabajando sin conexión y ha aplicado un subconjunto, no puede ver los resultados de todo el conjunto de datos. Consulte [Trabajar sin conexión y en línea](../../../../home/c-get-started/c-off-on.md#concept-cef8758ede044b18b3558376c5eb9f54).

   >[!NOTE]
   >
   >El tamaño del subconjunto está limitado a la cantidad de datos del filtro que residen en un solo servidor de Data Workbench. Por lo tanto, si el conjunto de datos abarca un clúster de servidores de Data Workbench, los datos del subconjunto proceden únicamente de un servidor de Data Workbench del clúster.

Un usuario de un gran minorista desea crear un subconjunto (caché local) de una semana de trabajo determinada de datos y luego ejecutar consultas solo en esa semana de datos. Para ello, el usuario crea un subconjunto para los días de interés.

El siguiente ejemplo muestra un gráfico de barras de Visitantes a lo largo del tiempo y una leyenda de métrica Tráfico. La primera figura no contiene selecciones: se representan todos los datos del conjunto de datos. La segunda figura muestra los datos de un subconjunto de Días = {...} por Visitantes, en el que Días se basa en una selección de los elementos del 1 de abril al 5 de abril en la dimensión Día.

![](assets/client-sub1.png)
