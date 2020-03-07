---
description: Información sobre la configuración general del sensor con una instancia de servidor web ejecutándose en un servidor web.
solution: Insight
title: Uso de varias instancias de un servidor Web
uuid: 778ea95f-e0f2-4c2a-b7ed-7e323fea1e48
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Uso de varias instancias de un servidor Web{#working-with-multiple-instances-of-a-web-server}

Información sobre la configuración general del sensor con una instancia de servidor web ejecutándose en un servidor web.

![](assets/web_inst.png)

En este escenario, una única instancia de servidor web está escribiendo datos en el archivo de cola de memoria asignada, que el transmisor lee y envía al servidor [!DNL data workbench server].

Cuando [!DNL Sensor] se instala en un servidor web que ejecuta varias instancias de recopilador, puede configurarlo de dos formas:

* Puede hacer que todos los módulos del recopilador compartan un archivo de cola.

   Cuando se utiliza un solo archivo de cola, la administración, la configuración y la administración se simplifican de alguna manera porque la arquitectura en sí es menos compleja. Sin embargo, con un solo archivo de cola, todo el servidor web, independientemente del número de instancias, se identifica como WEB1.

* Puede replicar la arquitectura anterior varias veces y hacer que cada instancia de servidor web tenga un archivo de cola independiente.

   Esto le permite identificar cada una de las instancias del servidor web de forma única. En otras palabras, la identificación del servidor web (y el correspondiente SensorID en la configuración) es una función de esta configuración. [!DNL Sensor]

En cualquier caso, los datos siguen teniendo toda la información del nombre del host para que pueda distinguir entre [!DNL www.client.com], [!DNL www2.client.com], etc. La configuración correcta está determinada por los objetivos de análisis y si los analistas necesitan segmentar los datos en función de una instancia específica que se ejecuta en un servidor web.

>[!NOTE]
>
>Este tipo de segmentación generalmente se utiliza solamente en el análisis operativo y no proporciona mucho uso práctico fuera de esa área.

