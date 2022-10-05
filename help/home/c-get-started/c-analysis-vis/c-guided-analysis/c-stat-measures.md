---
description: Para ayudar con las estadísticas, Data Workbench proporciona tres medidas estadísticas en la visualización de análisis guiados.
title: Medidas estadísticas
uuid: a8782cd2-d657-4c04-9c5d-8e0af2a3b76e
exl-id: 166ff98b-d531-4b31-897e-0c7fedbd2f4d
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '467'
ht-degree: 0%

---

# Medidas estadísticas{#statistical-measures}

{{eol}}

Para ayudar con las estadísticas, Data Workbench proporciona tres medidas estadísticas en la visualización de análisis guiados.

>[!NOTE]
>
>Aunque las matemáticas pueden ayudarle a juzgar las correlaciones en los datos, también debe tenerse en cuenta el contexto que rodea a los datos.

* **Chi Sq p** es una prueba de relevancia estadística que controla el aspecto de la marca de verificación en la visualización. Matemáticamente, es probable que podamos rechazar la hipótesis nula, que indica que las diferencias observadas entre los dos grupos pueden explicarse por variaciones aleatorias. Prácticamente, si el valor de Chi Sq p es menor que casi el 100%, podemos ignorar la correlación independientemente de su fuerza medida (como se describe en las siguientes secciones de estadística U y V).
* **Estadística de U** es una medida de la fortaleza de la correlación estadística. Matemáticamente, proviene de una rama de las matemáticas llamada teoría de la información y está estrechamente relacionada con el concepto de información mutua entre las distribuciones de los dos grupos. Alternativamente, se puede considerar como la compresibilidad de un grupo a partir de un esquema de codificación óptimo para el otro grupo. Prácticamente, esta medida funciona muy bien en el caso común de una dimensión con muchos elementos que contienen pocos visitantes. La medida varía de 0 (débil) a 1 (fuerte).
* **Estadística V** es también una medida de la fortaleza de la correlación estadística. Matemáticamente, está relacionado con la conocida estadística de V de Cramer, que difiere solamente por un paso de normalización destinado a mejorar la simetría de la medida con respecto a la inversión de selección. Prácticamente, esta medida funciona razonablemente bien con muchos tipos de dimensiones y está relacionada con una medida estadística de uso común. La medida varía de 0 (débil) a 1 (fuerte).

>[!NOTE]
>
>Las estadísticas de U y V se seleccionaron para complementarse entre sí, cada una ajustada para detectar tipos de correlaciones a las que la otra podría no responder con tanta fuerza.

Con esta visualización como guía, puede añadir otras visualizaciones al espacio de trabajo para proporcionar más información sobre los datos en función de la selección.

Lo siguiente [!DNL Site] ejemplo contiene un gráfico de barras que muestra las sesiones de los días de enero, febrero, marzo y abril. Tenga en cuenta que se ha seleccionado un día de enero.

![](assets/vis_GuidedAnalysis_withVis.png)

La visualización de análisis guiado en la esquina inferior izquierda del espacio de trabajo indica que la dimensión Número de sesión proporciona información útil sobre el día seleccionado.

Al examinar el gráfico de barras Número de sesión en la esquina inferior derecha del espacio de trabajo, puede ver que los datos del Número de sesión 2 son mucho más bajos que el valor de referencia. Por lo tanto, podemos concluir que, como porcentaje, el día seleccionado hubo menos sesiones secundarias de las que es habitual. Para ver un gráfico de barras para cualquiera de las dimensiones enumeradas en la visualización de análisis guiado, simplemente seleccione la dimensión haciendo clic en la dimensión con el ratón.
