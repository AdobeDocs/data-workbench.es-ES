---
description: El Generador de clústeres ahora incluye un algoritmo KMeans++ (solo se admitía anteriormente el algoritmo KMeans) que usa un enfoque más rápido para encontrar centros para un proceso de generación de clústeres acelerado.
title: Clustering 2.0
uuid: 14462bd3-06d1-4622-a2d8-f96aadb357f3
exl-id: 6a779ddc-c8f1-4c55-9c17-1119fe1aa791
source-git-commit: 050468bf6a9ef9c07719ded79c8ab68753d58647
workflow-type: tm+mt
source-wordcount: '288'
ht-degree: 0%

---

# Clustering 2.0{#clustering}

El Generador de clústeres ahora incluye un algoritmo KMeans++ (solo se admitía anteriormente el algoritmo KMeans) que usa un enfoque más rápido para encontrar centros para un proceso de generación de clústeres acelerado.

## Algoritmos de KMeans {#section-92383a1be1d6402c95a25c902e90b850}

En el [Generador de clústeres](https://experienceleague.adobe.com/docs/data-workbench/using/client/analysis-visualizations/visitor-cluster/c-visitor-cluster.html?lang=en), ahora puede seleccionar **[!UICONTROL Options]** > **[!UICONTROL Algorithm]** para seleccionar algoritmos al definir clústeres.

* **[!UICONTROL KMeans]**. Este algoritmo utiliza la agrupación en canopy para definir los centros del clúster.
* **[!UICONTROL KMeans++]**. Este algoritmo acelera la creación de clústeres cuando se ejecuta con grandes conjuntos de datos.

<!-- <a id="section_8193A6D60C5540BB985085BE670B4544"></a> -->

KMeans++ es una implementación mejorada del algoritmo de agrupación en clúster KMeans porque proporciona una mejor inicialización de los centros k iniciales. (El algoritmo original de KMeans elige los centros iniciales de forma aleatoria). KMeans++ selecciona el primer centro aleatoriamente. Los demás centros k-1 se elegirán uno por uno en función de la distancia que un punto de datos tenga con respecto al centro existente más cercano. Los puntos de datos más alejados tienen más posibilidades de ser elegidos como un nuevo centro que los puntos de datos cercanos. Una vez elegido el centro inicial, el procedimiento se realiza exactamente igual que la agrupación KMeans original.

El flujo de trabajo para KMeans++ es exactamente el mismo que el flujo de trabajo para la agrupación en clúster de KMeans, excepto que necesita seleccionar **Opciones** > **Algoritmo** > **KMeans++** en el generador de clústeres.

>[!NOTE]
>
>Cada DPU ejecuta su propio procedimiento KMeans++ en su propia parte de datos. Si el DPU tiene suficiente memoria disponible (la proporción se puede configurar en el archivo PAServer.cfg), los datos de las variables involucradas se recordarán. La selección inicial del centro k-1 restante y las iteraciones convergentes se producen en la memoria, lo que es más rápido que la agrupación en clúster KMeans anterior.
