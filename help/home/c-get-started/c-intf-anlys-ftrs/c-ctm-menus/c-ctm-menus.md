---
description: Puede personalizar el aspecto de los menús, incluido el menú de la ventana del espacio de trabajo (al que se accede haciendo clic con el botón derecho en cualquier espacio de trabajo) y los menús con métricas, dimensiones y capas de mapa.
solution: Analytics
title: Personalización de un menú
topic: Data workbench
uuid: 8c409c50-40b3-4de3-8048-a825ef4d75f5
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Personalización de un menú{#customize-a-menu}

Puede personalizar el aspecto de los menús, incluido el menú de la ventana del espacio de trabajo (al que se accede haciendo clic con el botón derecho en cualquier espacio de trabajo) y los menús con métricas, dimensiones y capas de mapa.

La jerarquía de cualquier menú refleja la estructura de su directorio en el [!DNL Profile Manager]. Por ejemplo, el menú de la ventana del espacio de trabajo refleja la estructura del directorio Menú y el menú de métricas refleja la estructura del directorio Métricas. Para cualquier menú, el directorio correspondiente puede contener los siguientes elementos:

* **Archivos:** Estos archivos representan las visualizaciones, leyendas, anotaciones, interfaces administrativas, métricas, dimensiones o capas de mapa que puede abrir haciendo clic en el elemento de menú correspondiente.
* **Un[!DNL order.txt]archivo:** Este archivo especifica en qué orden muestra los elementos el menú.
* **Subdirectorios:** Cada subdirectorio representa un submenú. Cada subdirectorio puede contener sus propios archivos, subdirectorios y [!DNL order.txt] archivos.

Por ejemplo, el [!DNL Add Legend] menú contiene los elementos de menú Métrica, Color, Valor y Confianza, en ese orden. En comparación, el directorio Menu\Add Legend del [!DNL Profile Manager] contiene los archivos [!DNL Color.vw], [!DNL Confidence.vw], [!DNL Metric.vw]y [!DNL Value.vw] en orden alfabético, así como un [!DNL order.txt] archivo para controlar el orden de los demás archivos.
