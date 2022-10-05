---
description: En las matemáticas, la fórmula de la haversina es una ecuación que da distancias de círculo entre dos puntos en una esfera identificada de sus longitudes y latitudes.
title: Haversine
uuid: 835fa9dd-db70-4498-a03e-59595bc041fe
exl-id: e700c0a0-1a1a-4c56-bb4f-1deb1b39b059
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '235'
ht-degree: 4%

---

# Haversine{#haversine}

{{eol}}

En las matemáticas, la fórmula de la haversina es una ecuación que da distancias de círculo entre dos puntos en una esfera identificada de sus longitudes y latitudes.

Al igual que la fórmula, la variable [!DNL Haversine] la transformación requiere dos conjuntos de [!DNL Latitude] y [!DNL Longitude] , usando estas cuatro entradas para calcular la distancia verdadera a través de la Tierra entre dos ubicaciones.

Esta distancia puede representarse como millas o kilómetros cambiando la bandera &quot;En kilómetros&quot; de falso a verdadero.

![](assets/cfg_TransformationType_Haversine.png)

| Parámetro | Descripción | Predeterminado |
|---|---|---|
| Nombre | Nombre descriptivo de la transformación. Puede introducir cualquier nombre aquí. |  |
| Comentarios | Opcional. Notas sobre la transformación. |  |
| Condición | Condiciones en las que se aplica esta transformación. |  |
| Campo Latitude 1 | Latitud del punto 1. |  |
| Campo Latitude 2 | Latitud del punto 2. |  |
| Campo Longitud 1 | Longitud del punto 1. |  |
| Campo Longitud 2 | Longitud del punto 2. |  |
| Output | Una vez calculado, la variable [!DNL Output] contiene distancias entre los puntos designados como elementos en un Dimension. |  |

Por ejemplo, si codifica en una latitud y longitud de su tienda como Lat1, Lon1 y utiliza una búsqueda IP larga y tardía para sus clientes, se pueden determinar las distancias a una tienda desde la que la mayoría de los clientes compran o vienen.

>[!NOTE]
>
>Si desea identificar distancias para otras ubicaciones, cada ubicación individual debe tener su propio conjunto de campos de latitud y longitud.
