---
description: Los gráficos de alza y ganancia ofrecen visualizaciones para evaluar el rendimiento potencial de un modelo puntuado con el fin de evaluar el rendimiento sobre las partes definidas de la audiencia.
solution: Analytics
title: Gráficos de alza y ganancia de tendencia
topic: Data workbench
uuid: 4f08277e-deea-48d3-ab15-214c43ad6664
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Gráficos de alza y ganancia de tendencia{#propensity-gain-and-lift-charts}

Los gráficos de alza y ganancia ofrecen visualizaciones para evaluar el rendimiento potencial de un modelo puntuado con el fin de evaluar el rendimiento sobre las partes definidas de la audiencia.

Los gráficos de alza y ganancia son visualizaciones creadas para evaluar el rendimiento potencial del modelo ranurado. Estos gráficos evalúan el rendimiento en cada porción de la población.

**Apertura de un gráfico de alza o ganancia**

1. Select [!DNL Add Visualization > Predictive Analytics > Scoring] .
1. Pase el ratón sobre **[!UICONTROL Model Complete]** una puntuación guardada.

![](assets/propensity_lift_gain_1.png)

**Acerca de los gráficos de alza y ganancia**

Los gráficos de alza y ganancia son herramientas visuales útiles para medir el valor de un modelo predictivo. Ambos gráficos constan de una curva de alza (verde) y una línea base (rosa). Para el gráfico **de** ganancia, la distancia entre la curva de alza y la línea base representa cuánto puede mejorar el rendimiento en las respuestas (o la &quot;ganancia&quot;) mediante el uso del modo predictivo. La ganancia se logra priorizando y dirigiendo los posibles clientes (clientes/visitantes) que tienen más probabilidades de convertirse, en lugar de la mercadotecnia a clientes/visitantes al azar. De este modo, puede cuantificar el valor esperado de utilizar el modelo predictivo para elegir los posibles clientes con los que establecer contacto.

Al igual que en el gráfico de ganancias, el gráfico **de** alza muestra la probabilidad de recibir respuestas positivas que si se contactó con posibles clientes al azar. Desea que la distancia entre la curva de alza y la línea base sea lo más grande posible, lo que representa mayores ganancias esperadas del uso del modelo predictivo para contactar con los clientes. Matemáticamente, los gráficos de alza y ganancia se definen de la siguiente manera:

* **Ganancia** = (respuesta esperada mediante modelo predictivo a perspectiva de contacto) / (respuesta esperada desde perspectivas de contacto aleatorio)
* **Alza** = (respuesta esperada entre un tamaño de grupo específico de perspectivas identificadas mediante el modelo predictivo) / (respuesta esperada entre el mismo tamaño de grupo específico de perspectivas identificado aleatoriamente)

**Ejemplo de gráficos de alza y ganancia**

Por ejemplo: piense en el ejemplo de un minorista que quiere lanzar una campaña de remercadotecnia por correo electrónico para vender pantalones de yoga. Históricamente, el analista espera una tasa de respuesta promedio del 20 por ciento en base a campañas de remercadotecnia por correo electrónico anteriores similares a esta. Aunque el analista tiene cerca de 5 millones de clientes en su base de datos de correo electrónico, el negocio sólo quiere comercializar a aquellos clientes que tienen más probabilidades de responder al correo electrónico y la compra. De este modo, la empresa maximizará el ROI de la campaña y, al mismo tiempo, se asegurará de que no envíen correos electrónicos innecesariamente a clientes no interesados. Dada una tasa de respuesta esperada del 20 por ciento, el especialista en mercadotecnia y analista espera que aproximadamente un millón de clientes respondan y compren. En lugar de adivinar al azar cuál de esos clientes estará entre el 20 por ciento de respuestas, el analista quiere ser inteligente al predecir cuál de los 1 millón de posibles clientes (entre la base de datos de 5 millones de clientes) tiene más probabilidades de responder.

Al utilizar la función Audience Scoring de Adobe, el analista define el éxito como un posible cliente que hace clic en un correo electrónico y compra pantalones de yoga (la variable dependiente). Después de seleccionar las variables independientes (en base a la experiencia y los conocimientos adquiridos al analizar las correlaciones de datos y la agrupación de audiencias, entre otros análisis), cada posible cliente queda marcado por la probabilidad de responder positivamente a la campaña de remercadotecnia por correo electrónico (haciendo clic en el correo electrónico y comprando pantalones de yoga). El analista abre los gráficos de Ganancia y Alza resultantes según el modelo predictivo.

El eje Y muestra el porcentaje de las respuestas positivas esperadas acumulativas. En nuestro ejemplo, esperamos un total de 1 millón de respuestas positivas. Un valor del 20 % en el eje Y corresponde al 20 % del millón de respuestas positivas esperadas, o 200 000 respuestas positivas. El eje x muestra el porcentaje de clientes potenciales con los que se contactó. En nuestro ejemplo, el eje x representa una fracción de los 5 millones de clientes de la base de datos de correo electrónico. La línea de base (rosa) es la tasa de respuesta global; si se pone en contacto con X% de posibles clientes, recibirá X% del total de respuestas positivas. Utilizando el modelo predictivo, la curva de alza (verde) muestra el porcentaje de respuestas positivas obtenidas (eje Y) al contactar con un porcentaje determinado de posibles clientes (eje X).

El gráfico del alza representa el alza esperada como resultado del uso del modelo predictivo para determinar el millón de posibles clientes más propensos a comprar pantalones de yoga después de recibir y hacer clic en el correo electrónico. Para contactar con el 20 por ciento de los posibles clientes seleccionados al azar sin un modelo predictivo, se debería esperar que el 20 por ciento de los encuestados obtengan respuesta. Sin embargo, si se utiliza el modelo predictivo para identificar el 20 % de los posibles clientes que tienen más probabilidades de responder, se espera que el 50 % de los encuestados obtenga respuesta. El valor y de la curva de alza del 20 por ciento es 50/20 = 2,5. El gráfico de alza muestra la probabilidad de recibir a los encuestados que si se pone en contacto con una muestra aleatoria de posibles clientes. Por ejemplo: al contactar con sólo el 20 por ciento de las perspectivas en base al modelo predictivo, llegaremos a 2,5 veces más a los encuestados que a no haber utilizado ningún modelo predictivo.
