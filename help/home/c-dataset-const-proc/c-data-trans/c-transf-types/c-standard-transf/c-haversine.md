---
description: En matemáticas, la fórmula de la haversina es una ecuación que da distancias de círculo entre dos puntos en una esfera identificada de sus longitudes y latitudes.
solution: Analytics
title: Haversina
topic: Data workbench
uuid: 835fa9dd-db70-4498-a03e-59595bc041fe
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Haversina{#haversine}

En matemáticas, la fórmula de la haversina es una ecuación que da distancias de círculo entre dos puntos en una esfera identificada de sus longitudes y latitudes.

Al igual que la fórmula, la [!DNL Haversine] transformación requiere dos conjuntos de [!DNL Latitude] configuraciones y [!DNL Longitude] configuraciones, utilizando estas cuatro entradas para calcular la verdadera distancia a través de la Tierra entre dos ubicaciones.

Esta distancia puede representarse como millas o kilómetros cambiando la bandera &quot;En kilómetros&quot; de false a true.

![](assets/cfg_TransformationType_Haversine.png)

| Parámetro | Descripción | Valor predeterminado |
|---|---|---|
| Nombre | Nombre descriptivo de la transformación. Aquí puede introducir cualquier nombre. |  |
| Comentarios | Opcional. Notas sobre la transformación. |  |
| Condición | Condiciones en las que se aplica esta transformación. |  |
| Campo Latitude 1 | La latitud del punto 1. |  |
| Campo Latitude 2 | La latitud del punto 2. |  |
| Campo Longitud 1 | Longitud del punto 1. |  |
| Campo Longitud 2 | Longitud del punto 2. |  |
| Salida | Una vez calculado, el [!DNL Output] campo contiene distancias entre los puntos designados como elementos en una dimensión. |  |

Por ejemplo, si codifica en latitud y longitud de su tienda como Lat1, Lon1 y utiliza una búsqueda IP larga y larga para sus clientes, se pueden determinar las distancias a una tienda desde la que la mayoría de los clientes compran o de la que provienen.

>[!NOTE]
>
>Si desea identificar las distancias para otras ubicaciones, cada ubicación individual debe tener su propio conjunto de campos lat y lon.

