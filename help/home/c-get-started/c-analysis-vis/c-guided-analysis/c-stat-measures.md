---
description: Para ayudar con las estadísticas, Área de trabajo de datos proporciona tres medidas estadísticas en la visualización de análisis guiado.
solution: Analytics
title: Medidas estadísticas
topic: Data workbench
uuid: a8782cd2-d657-4c04-9c5d-8e0af2a3b76e
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Medidas estadísticas{#statistical-measures}

Para ayudar con las estadísticas, Área de trabajo de datos proporciona tres medidas estadísticas en la visualización de análisis guiado.

>[!NOTE]
>
>Aunque las matemáticas pueden ayudarle a juzgar las correlaciones en los datos, también se debe tener en cuenta el contexto que rodea a los datos.

* **Chi Sq p** es una prueba de relevancia estadística que controla el aspecto de la marca de verificación en la visualización. Matemáticamente, es probable que podamos rechazar la hipótesis nula, que establece que las diferencias observadas entre los dos grupos pueden explicarse por variaciones aleatorias. Prácticamente, si el valor p de Chi Sq es inferior al 100%, podemos ignorar la correlación independientemente de su intensidad medida (como se describe en las siguientes secciones estadísticas de U y de V).
* **La estadística** U es una medida de la fortaleza de la correlación estadística. Matemáticamente, viene de una rama de las matemáticas llamada teoría de la información y está estrechamente relacionada con el concepto de información mutua entre las distribuciones de los dos grupos. Como alternativa, se puede considerar que es la compresibilidad de un grupo dado un esquema de codificación óptimo para el otro grupo. Prácticamente, esta medida funciona muy bien en el caso común de una dimensión con muchos elementos que contienen pocos visitantes. La medida varía entre 0 (débil) y 1 (fuerte).
* **La estadística** V también es una medida de la fortaleza de la correlación estadística. Matemáticamente, está relacionado con la conocida estadística V de Cramer, que difiere solamente por un paso de normalización destinado a mejorar la simetría de la medida con respecto a la inversión de selección. Prácticamente, esta medida funciona razonablemente bien con muchos tipos de dimensiones y está relacionada con una medida estadística de uso común. La medida varía entre 0 (débil) y 1 (fuerte).

>[!NOTE]
>
>Las estadísticas de U y V se seleccionaron para complementarse entre sí, cada una de ellas adaptada para detectar tipos de correlaciones a las que la otra podría no responder con tanta fuerza.

Con esta visualización como guía, puede agregar otras visualizaciones al espacio de trabajo para proporcionar una mayor perspectiva de los datos en función de la selección.

El [!DNL Site] ejemplo siguiente contiene un gráfico de barras que muestra las sesiones de los días de enero, febrero, marzo y abril. Tenga en cuenta que se selecciona un día en enero.

![](assets/vis_GuidedAnalysis_withVis.png)

La visualización de análisis guiado en la esquina inferior izquierda del espacio de trabajo indica que la dimensión Número de sesión proporciona información útil sobre el día seleccionado.

Al examinar el gráfico de la barra Número de sesión en la esquina inferior derecha del espacio de trabajo, puede ver que los datos de Número de sesión 2 son mucho menores que el valor de referencia. Por lo tanto, podemos concluir que, como porcentaje, el día seleccionado tuvo lugar menos segundas sesiones que las habituales. Para ver un gráfico de barras para cualquiera de las dimensiones enumeradas en la visualización de análisis guiado, simplemente seleccione la dimensión haciendo clic en la dimensión con el ratón.
