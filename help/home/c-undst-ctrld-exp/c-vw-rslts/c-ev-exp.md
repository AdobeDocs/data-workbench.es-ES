---
description: Después de ejecutar el experimento hasta que el número mínimo requerido de visitantes haya participado en él, puede estar seguro de que cuenta con suficiente confianza estadística para evaluar los resultados del experimento.
solution: Analytics
title: Evaluación del experimento
uuid: 88fd81bc-b944-48ea-bd4d-8716979ec69e
exl-id: 5add2168-f6bc-45c5-bf1d-1191a38c5bac
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '333'
ht-degree: 1%

---

# Evaluación del experimento{#evaluating-the-experiment}

{{eol}}

Después de ejecutar el experimento hasta que el número mínimo requerido de visitantes haya participado en él, puede estar seguro de que cuenta con suficiente confianza estadística para evaluar los resultados del experimento.

Uso [!DNL Insight], compare las métricas o los indicadores clave de rendimiento que se hayan definido como parte de la hipótesis para determinar si el experimento fue un éxito (es decir, la hipótesis se validó con la confianza especificada).

En nuestro experimento de ejemplo, nuestra hipótesis se demuestra correcta si la conversión de visitantes aumenta al menos en un 1,5 %, que es el criterio de éxito que definimos anteriormente.

El siguiente ejemplo de espacio de trabajo muestra que la Conversión para el grupo de prueba index2 era en realidad un 1,8% más alta que para el grupo de control, lo que demuestra nuestra hipótesis.

![](assets/experimentresults.png)

* [Resumen de los resultados del experimento](../../../home/c-undst-ctrld-exp/c-vw-rslts/c-ev-exp.md#section-24a496c080a04e929764094acb00bab7)
* [Acción basada en los resultados](../../../home/c-undst-ctrld-exp/c-vw-rslts/c-ev-exp.md#section-1623e26ced524fd9beab48ac1f9165d9)
* [Supervisión de acciones](../../../home/c-undst-ctrld-exp/c-vw-rslts/c-ev-exp.md#section-1954311950c34637800cbd7c0711983f)

## Resumen de los resultados del experimento {#section-24a496c080a04e929764094acb00bab7}

Uso [!DNL Insight], puede crear informes detallados para resumir e ilustrar los resultados del experimento.

A continuación, puede usar los informes, como se muestra en el siguiente ejemplo, para hacer recomendaciones basadas en los resultados, que están respaldados por la información visual que ha proporcionado en los informes:

![](assets/experimentresults2.png)

## Acción basada en los resultados {#section-1623e26ced524fd9beab48ac1f9165d9}

Una vez que los resultados sean claros, estará listo para actuar sobre esos resultados realizando cambios en el nivel de producción en las páginas probadas, aplicando los mismos cambios en otras áreas del sitio web y asegurándose de documentar completamente la prueba, sus resultados y los cambios realizados.

## Supervisión de acciones {#section-1954311950c34637800cbd7c0711983f}

Una vez completado el experimento controlado y haya implementado los cambios correspondientes, asegúrese de seguir monitorizando los cambios realizados, por ejemplo, viendo las métricas de validación, creando gráficos de control y proporcionando métricas de tablero.

Siempre esté preparado para volver a probar la hipótesis si cree que los cambios que probó y realizó no están reflejando los resultados originales.
