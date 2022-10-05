---
description: Puede personalizar el aspecto de los menús, incluido el menú de la ventana del espacio de trabajo (al que se accede haciendo clic con el botón derecho en cualquier espacio de trabajo) y los menús que incluyen métricas, dimensiones y capas de asignación.
title: Personalización de un menú
uuid: 8c409c50-40b3-4de3-8048-a825ef4d75f5
exl-id: 7a377d9c-d339-43d8-a71a-a322416b2e60
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '206'
ht-degree: 2%

---

# Personalización de un menú{#customize-a-menu}

{{eol}}

Puede personalizar el aspecto de los menús, incluido el menú de la ventana del espacio de trabajo (al que se accede haciendo clic con el botón derecho en cualquier espacio de trabajo) y los menús que incluyen métricas, dimensiones y capas de asignación.

La jerarquía de cualquier menú refleja la estructura de su directorio en la variable [!DNL Profile Manager]. Por ejemplo, el menú de la ventana del espacio de trabajo refleja la estructura del directorio Menú y el menú de métricas refleja la estructura del directorio Métricas. Para cualquier menú, el directorio correspondiente puede contener los siguientes elementos:

* **Archivos:** Estos archivos representan las visualizaciones, leyendas, anotaciones, interfaces administrativas, métricas, dimensiones o capas de mapa que puede abrir haciendo clic en el elemento de menú correspondiente.
* **Un [!DNL order.txt] archivo:** Este archivo especifica en qué orden el menú muestra sus elementos.
* **Subdirectorios:** Cada subdirectorio representa un submenú. Cada subdirectorio puede contener sus propios archivos, subdirectorios y [!DNL order.txt] archivo.

Por ejemplo, la variable [!DNL Add Legend] contiene los elementos de menú Métrica, Color, Valor y Confianza, en ese orden. En comparación, el directorio Menu\Add Legend en la variable [!DNL Profile Manager] contiene los archivos [!DNL Color.vw], [!DNL Confidence.vw], [!DNL Metric.vw]y [!DNL Value.vw] archivos en orden alfabético, así como [!DNL order.txt] para controlar el orden de los demás archivos.
