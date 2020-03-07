---
description: El Generador de clústeres ahora incluye un algoritmo KMeans++ (solo se admitía anteriormente el algoritmo KMeans) que utiliza un método más rápido para encontrar centros para un proceso de generación acelerada de clústeres.
title: Clustering 2.0
uuid: 14462bd3-06d1-4622-a2d8-f96aadb357f3
translation-type: tm+mt
source-git-commit: cb3ca4b3b993f5f04f6b6cee25850600ff3d8986

---


# Clustering 2.0{#clustering}

El Generador de clústeres ahora incluye un algoritmo KMeans++ (solo se admitía anteriormente el algoritmo KMeans) que utiliza un método más rápido para encontrar centros para un proceso de generación acelerada de clústeres.

## Algoritmos KMeans {#section-92383a1be1d6402c95a25c902e90b850}

En el Generador [de clústeres](https://docs.adobe.com/help/en/data-workbench/using/client/analysis-visualizations/visitor-cluster/c-visitor-cluster.html), ahora puede seleccionar **[!UICONTROL Options]** > **[!UICONTROL Algorithm]** para seleccionar algoritmos al definir clústeres.

* **[!UICONTROL KMeans]**. Este algoritmo utiliza la agrupación en canopy para definir los centros del clúster.
* **[!UICONTROL KMeans++]**. Este algoritmo acelera la creación de clústeres cuando se ejecuta con grandes conjuntos de datos.

<!-- <a id="section_8193A6D60C5540BB985085BE670B4544"></a> -->

KMeans++ es una implementación mejorada del algoritmo de clúster KMeans porque proporciona una mejor inicialización de los centros k iniciales. (El algoritmo original de KMeans elige los centros iniciales al azar). KMeans++ selecciona el primer centro al azar. Los centros k-1 restantes se elegirán uno por uno en función de la distancia que un punto de datos se encuentre al centro existente más cercano. Los puntos de datos más alejados tienen más posibilidades de ser elegidos como un nuevo centro que los puntos de datos cercanos. Una vez elegido el centro inicial, el procedimiento se realiza exactamente igual que el agrupamiento original de KMeans.

El flujo de trabajo para KMeans++ es exactamente el mismo que el flujo de trabajo para la agrupación en clúster KMeans, excepto que necesita seleccionar **Opciones** > **Algoritmo** > **KMeans++** en el generador de clústeres.

>[!NOTE]
>
>Cada DPU ejecuta su propio procedimiento KMeans++ en su propia porción de datos. Si el DPU tiene suficiente memoria disponible (la proporción se puede configurar en el archivo PAServer.cfg), entonces los datos de las variables involucradas se llevarán a la memoria. El resto de la selección central inicial k-1 y las iteraciones convergentes se producen en la memoria, lo que es más rápido que el anterior agrupamiento de KMeans.

