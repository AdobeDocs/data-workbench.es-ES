---
description: El agrupamiento de visitantes permite aprovechar las características del cliente para categorizar de forma dinámica a los visitantes y generar conjuntos de clústeres basados en entradas de datos seleccionadas, identificando así grupos con intereses y comportamientos similares para el análisis y la segmentación de clientes.
solution: Analytics
title: Clúster de visitantes
topic: Data workbench
uuid: 0c16aaa0-1d86-43a6-a7e2-b43b3ea80dc5
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Clúster de visitantes{#visitor-clustering}

El agrupamiento de visitantes permite aprovechar las características del cliente para categorizar de forma dinámica a los visitantes y generar conjuntos de clústeres basados en entradas de datos seleccionadas, identificando así grupos con intereses y comportamientos similares para el análisis y la segmentación de clientes.

**Proceso de agrupación**

El proceso de agrupación en clúster requiere que identifique las métricas y los elementos de dimensión para utilizarlos como entradas, y permite elegir una población objetivo específica para aplicar estos elementos a fin de crear clústeres específicos. Cuando se ejecuta el proceso de agrupación en clúster, el sistema utiliza las entradas de métrica y dimensión para determinar los centros iniciales adecuados para el número especificado de clústeres. Estos centros se utilizan luego como punto de partida para aplicar el algoritmo K-Means.

![](assets/K_algorithm.png)

* Los centros iniciales son elegidos de manera inteligente a través de un pase de Canopy Clustering.
* Los clústeres de datos se crean asociando cada punto de datos al centro más cercano.
* La media de cada uno de los clústeres K se convierte en el nuevo centro.
* El algoritmo se repite en los pasos 2 y 3 hasta que se alcance la convergencia. Esto puede llevar varios pases.

La opción **[!UICONTROL Maximum Iterations]** del **[!UICONTROL Options]** menú permite al analista especificar el número máximo de iteraciones que debe realizar el algoritmo de clúster. Si se establece esta opción, el proceso de agrupación en clúster se completará más rápidamente, en función del límite máximo de iteraciones, a expensas de la convergencia exacta de los centros de clúster.

>[!NOTE]
>
>Una vez definidos los clústeres, la dimensión de clúster se puede guardar para su uso como cualquier otra dimensión. También se puede cargar en el Explorador de clústeres para examinar la separación de los centros de clúster.

En el Generador de clústeres, puede seleccionar **[!UICONTROL Options]** > **[!UICONTROL Algorithm]** para seleccionar algoritmos al definir clústeres. Actualmente, hay 3 algoritmos admitidos:

* KMeans
* Ksignificado`++`
* Maximización de las expectativas

Existen dos formas de ejecutar el proceso de agrupación en clúster:

* Método 1: haga clic **[!UICONTROL Go]** en la ventana de visualización del clúster.
* Método 2: haga clic **[!UICONTROL Submit]** en la ventana de visualización de clúster, que envía directamente el trabajo de clúster al servidor. Puede realizar un seguimiento del progreso mediante la opción &quot;Estado detallado de la consulta&quot;.

![](assets/dwb_visitorclustering.png)

El algoritmo tiene las siguientes restricciones:

1. Si utiliza el método 1, puede seleccionar cualquiera de los algoritmos de clúster admitidos.
1. Si está utilizando el Método 2, puede seleccionar medios o medios++. La opción Maximización de la expectativa no estará disponible.

>[!NOTE]
>
>En el [!DNL DPU.cfg] archivo, el valor de &#39;Consulta, Límite de memoria&#39; se establece en 500 MB de forma predeterminada. Este valor debe incrementarse mientras se ejecutan varios trabajos de clúster. Por ejemplo, si está ejecutando 5 trabajos de clúster en paralelo, aumente este valor a 1 GB. No hay forma de cancelar el trabajo de clúster sin reiniciar el servidor.

**Recomendaciones**

El número de iteraciones (número de veces que se analizan los datos) y el umbral de convergencia que se configura afectan gravemente al rendimiento de la agrupación en clúster. La siguiente tabla proporciona una guía más amplia que puede seguir:

| Número de clústeres | Algoritmo | Iteraciones | Umbral de convergencia | Normalización |
|---|---|---|---|---|
| 6 | Ksignificado | 25,50 | 1e-3 | Mín.-Máx. |
| 6 | Ksignificado | 25,50 | 1e-6 | Mín.-Máx. |
| 6 | Kames++ | 50 | 1e-6 | Mín.-Máx. |
