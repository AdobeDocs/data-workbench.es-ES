---
description: La agrupación de visitantes permite aprovechar las características de los clientes para categorizar de forma dinámica a los visitantes y generar conjuntos de clústeres basados en entradas de datos seleccionadas, lo que identifica grupos que tienen intereses y comportamientos similares para el análisis y la segmentación de los clientes.
title: Clúster de visitantes
uuid: 0c16aaa0-1d86-43a6-a7e2-b43b3ea80dc5
exl-id: 68c1845d-9c49-4ad9-adf3-c123d08cf758
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '495'
ht-degree: 2%

---

# Clúster de visitantes{#visitor-clustering}

{{eol}}

La agrupación de visitantes permite aprovechar las características de los clientes para categorizar de forma dinámica a los visitantes y generar conjuntos de clústeres basados en entradas de datos seleccionadas, lo que identifica grupos que tienen intereses y comportamientos similares para el análisis y la segmentación de los clientes.

**Proceso de agrupación en clúster**

El proceso de agrupación en clúster requiere que identifique métricas y elementos de dimensión para utilizarlos como entradas y permite elegir una población objetivo específica para aplicar estos elementos y crear clústeres especificados. Al ejecutar el proceso de agrupación en clústeres, el sistema utiliza las entradas de métricas y dimensiones para determinar los centros iniciales adecuados para el número especificado de clústeres. Estos centros se utilizan como punto de partida para aplicar el algoritmo K-Means.

![](assets/K_algorithm.png)

* Los centros iniciales se eligen de forma inteligente a través de un pase de Canopy Clustering.
* Los clústeres de datos se crean asociando cada punto de datos al centro más cercano.
* La media de cada grupo K se convierte en el nuevo centro.
* El algoritmo se repite en los pasos 2 y 3 hasta que se alcance la convergencia. Esto puede llevar varios pases.

La variable **[!UICONTROL Maximum Iterations]** en el **[!UICONTROL Options]** permite al analista especificar el número máximo de iteraciones que realizará el algoritmo de agrupación en clústeres. Si se establece esta opción, es posible que el proceso de agrupación en clúster se complete más rápido, en función del límite máximo de iteraciones, a expensas de la convergencia exacta de los centros de clúster.

>[!NOTE]
>
>Una vez definidos los clústeres, el Dimension de clúster se puede guardar para utilizarlo como cualquier otra dimensión. También se puede cargar en el Explorador de clústeres para examinar la separación de los centros de clúster.

En el Generador de clústeres, puede seleccionar **[!UICONTROL Options]** > **[!UICONTROL Algorithm]** para seleccionar algoritmos al definir clústeres. Actualmente, hay 3 algoritmos compatibles:

* KMeans
* KCalles`++`
* Maximización de expectativas

Existen dos maneras de ejecutar el proceso de agrupación en clúster:

* Método 1: Clic **[!UICONTROL Go]** en la ventana de visualización del clúster.
* Método 2: Clic **[!UICONTROL Submit]** en la ventana de visualización del clúster, que envía directamente el trabajo de agrupación en clúster al servidor. Puede realizar un seguimiento del progreso mediante la opción &quot;Estado detallado para la consulta&quot;.

![](assets/dwb_visitorclustering.png)

El algoritmo tiene las siguientes restricciones:

1. Si utiliza el método 1, puede seleccionar cualquiera de los algoritmos de agrupación en clúster admitidos.
1. Si utiliza el método 2, puede seleccionar kresources o kresources++. La opción Maximización de expectativas no está disponible.

>[!NOTE]
>
>En el [!DNL DPU.cfg] , el valor de &quot;Consulta, Límite de memoria&quot; se establece en 500 MB de forma predeterminada. Este valor debe aumentarse mientras se ejecutan varios trabajos de agrupación en clúster. Por ejemplo, si está ejecutando 5 trabajos de agrupación en clúster en paralelo, aumente este valor a 1 GB. No hay forma de cancelar el trabajo de agrupación en clúster sin reiniciar el servidor.

**Recomendaciones**

El número de iteraciones (número de veces que se analizan los datos) y el umbral de convergencia que se configura afectan gravemente al rendimiento de la agrupación en clúster. La siguiente tabla proporciona una guía más amplia que puede seguir:

| Número de clústeres | Algoritmo | Iteraciones | Umbral de convergencia | Normalización |
|---|---|---|---|---|
| 6 | KCalles | 25,50 | 1e-3 | Min-Max |
| 6 | KCalles | 25,50 | 1e-6 | Min-Max |
| 6 | Kmedia++ | 50 | 1e-6 | Min-Max |
