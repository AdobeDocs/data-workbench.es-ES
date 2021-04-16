---
description: Información sobre la configuración general del sensor con una instancia de servidor web que se ejecuta en un servidor web.
title: Uso de varias instancias de un servidor web
uuid: 778ea95f-e0f2-4c2a-b7ed-7e323fea1e48
exl-id: a371f9ed-6c27-4b3d-843f-ae5621013410
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '278'
ht-degree: 5%

---

# Uso de varias instancias de un servidor web{#working-with-multiple-instances-of-a-web-server}

Información sobre la configuración general del sensor con una instancia de servidor web que se ejecuta en un servidor web.

![](assets/web_inst.png)

En esta situación, una sola instancia de servidor web está escribiendo datos en el archivo de cola asignado a memoria, que el transmisor lee y envía al [!DNL data workbench server].

Cuando [!DNL Sensor] está instalado en un servidor web que ejecuta varias instancias de recopilación, puede configurarlo de una de las dos maneras siguientes:

* Puede hacer que todos los módulos de recopilación compartan un archivo de cola.

   Cuando se utiliza un solo archivo de cola, la administración, la configuración y la administración se simplifican en cierta medida porque la arquitectura en sí es menos compleja. Sin embargo, con un solo archivo de cola, todo el servidor web, independientemente del número de instancias, se identifica como WEB1.

* Puede replicar la arquitectura anterior varias veces y hacer que cada instancia de servidor web tenga un archivo de cola independiente.

   Esto permite identificar cada una de las instancias del servidor web de forma única. En otras palabras, la identificación del servidor web (y el SensorID correspondiente en la configuración [!DNL Sensor]) es una función de esta configuración.

En cualquier caso, los datos siguen teniendo toda la información del nombre de host, de modo que se pueda distinguir entre [!DNL www.client.com], [!DNL www2.client.com], etc. La configuración correcta está determinada por los objetivos de análisis y si los analistas deben segmentar los datos en función de una instancia específica que se ejecute en un servidor web.

>[!NOTE]
>
>Este tipo de segmentación generalmente se utiliza solamente en análisis operativos y no proporciona mucho uso práctico fuera de esa área.
