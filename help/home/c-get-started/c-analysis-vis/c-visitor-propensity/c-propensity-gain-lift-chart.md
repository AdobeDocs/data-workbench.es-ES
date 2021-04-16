---
description: Los gráficos Alza y Ganancia ofrecen visualizaciones para evaluar el rendimiento potencial de un modelo puntuado para evaluar el rendimiento en partes definidas de la audiencia.
title: Gráficos de alza y ganancia de tendencia
uuid: 4f08277e-deea-48d3-ab15-214c43ad6664
exl-id: 5ac08512-ac9c-4e85-a4f9-ea6d819095d8
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '806'
ht-degree: 1%

---

# Gráficos de alza y ganancia de tendencia{#propensity-gain-and-lift-charts}

Los gráficos Alza y Ganancia ofrecen visualizaciones para evaluar el rendimiento potencial de un modelo puntuado para evaluar el rendimiento en partes definidas de la audiencia.

Los gráficos de ganancia y alza son visualizaciones creadas para evaluar el rendimiento potencial del modelo marcado. Estos gráficos evalúan el rendimiento en cada parte de la población.

**Apertura de un gráfico de alza o ganancia**

1. Seleccione [!DNL Add Visualization > Predictive Analytics > Scoring] .
1. Pase el ratón sobre **[!UICONTROL Model Complete]** de una puntuación guardada.

![](assets/propensity_lift_gain_1.png)

**Acerca de los gráficos de alza y ganancia**

Los gráficos de alza y ganancia son herramientas visuales útiles para medir el valor de un modelo predictivo. Ambos gráficos constan de una curva de alza (verde) y una línea base (rosa). Para el **Gráfico de ganancia**, la distancia entre la curva de alza y la línea de base representa cuánto puede mejorar el rendimiento en las respuestas (o la &quot;ganancia&quot;) al usar el modo predictivo. La ganancia se obtiene priorizando y segmentando los clientes potenciales (clientes/visitantes) que tienen más probabilidades de convertir, en lugar de dirigir marketing a clientes/visitantes al azar. De este modo, puede cuantificar el valor esperado de utilizar el modelo predictivo para elegir qué posibles clientes ponerse en contacto.

Al igual que el gráfico de ganancia, el **gráfico de alza** muestra la probabilidad de recibir respuestas positivas en comparación con los posibles clientes contactados al azar. Desea que la distancia entre la curva de alza y la línea de base sea lo más grande posible, lo que representa mayores ganancias esperadas al usar el modelo predictivo para contactar con los clientes. Matemáticamente, los gráficos de alza y ganancia se definen de la siguiente manera:

* **Ganancia**  = (Respuesta esperada mediante el modelo predictivo para contactar con los posibles clientes) / (Respuesta esperada desde los posibles contactos aleatorios)
* **Alza**  = (respuesta esperada entre un tamaño de grupo específico de posibles clientes identificado mediante el modelo predictivo) / (respuesta esperada entre el mismo tamaño de grupo específico de posibles clientes identificado aleatoriamente)

**Ejemplo de gráficos de alza y ganancia**

Por ejemplo, veamos el ejemplo de un minorista que quiere lanzar una campaña de remarketing por correo electrónico para vender pantalones de yoga. Históricamente, el analista espera una tasa de respuesta promedio del 20 por ciento en función de campañas de remarketing por correo electrónico anteriores similares a esta. Aunque el analista tiene cerca de 5 millones de clientes en su base de datos de correo electrónico, la empresa solo quiere comercializar con aquellos clientes que tienen más probabilidades de responder al correo electrónico y a la compra. De este modo, la empresa maximizará el ROI de la campaña y se asegurará de que no envíen correos electrónicos a clientes que no estén interesados de forma innecesaria. Dada la tasa de respuesta esperada del 20 por ciento, el especialista en marketing y analista esperan que aproximadamente 1 millón de clientes probablemente respondan y compren. En lugar de adivinar aleatoriamente cuál de esos clientes estará entre las respuestas del 20 por ciento, el analista quiere ser inteligente a la hora de predecir cuál de los 1 millón de clientes potenciales (entre la base de datos de 5 millones de clientes) tienen más probabilidades de responder.

Con la capacidad de Puntuación de audiencia de Adobe, el analista define el éxito como un posible cliente que hace clic en un correo electrónico y compra pantalones de yoga (la variable dependiente). Después de seleccionar las variables independientes (en función de la experiencia y los conocimientos adquiridos al analizar las correlaciones de datos y la agrupación de audiencias, entre otros análisis), cada posible cliente queda marcado por su probabilidad de responder positivamente a la campaña de remarketing por correo electrónico (hacer clic en el correo electrónico y comprar pantalones de yoga). El analista abre los gráficos de Ganancia y Alza resultantes basados en el modelo predictivo.

El eje Y muestra el porcentaje de las respuestas positivas esperadas acumulativas. En nuestro ejemplo, esperamos un total de 1 millón de respuestas positivas. Un valor del 20% en el eje Y corresponde al 20% de las 1 millón de respuestas positivas esperadas, o 200.000 respuestas positivas. El eje x muestra el porcentaje de clientes potenciales contactados. En nuestro ejemplo, el eje x representa una fracción de los 5 millones de clientes de la base de datos de correo electrónico. La línea de base (rosa) es la tasa de respuesta general: si se contacta con el X% de los posibles clientes, recibirá el X% de las respuestas positivas totales. Con el modelo predictivo, la curva de alza (verde) muestra el porcentaje de respuestas positivas obtenido (eje Y) poniéndose en contacto con un porcentaje determinado de perspectivas (eje x).

El gráfico Alza representa el alza esperada como resultado del uso del modelo predictivo para determinar el millón de posibles clientes que más probablemente comprarán pantalones de yoga después de recibir y hacer clic en el correo electrónico. Para contactar con el 20 por ciento de los posibles clientes seleccionados al azar sin usar un modelo predictivo, debería esperar obtener el 20 por ciento de los encuestados. Sin embargo, si utiliza el modelo predictivo para identificar el 20 % de los posibles clientes que tienen más probabilidades de responder, recibirá el 50 % de los encuestados. El valor y de la curva de alza del 20 por ciento es 50/20 = 2,5. El gráfico de alza muestra cuánta mayor probabilidad tendrá de recibir a los encuestados que si se pone en contacto con una muestra aleatoria de posibles clientes. Por ejemplo, si se pone en contacto con solo el 20 % de los posibles clientes basándose en el modelo predictivo, se obtendrán 2,5 veces más encuestados que no utilizando ningún modelo predictivo.
