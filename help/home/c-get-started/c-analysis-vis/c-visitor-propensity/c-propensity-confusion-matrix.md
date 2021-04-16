---
description: Se definen los cálculos estadísticos para la Puntuación de tendencia.
title: Cálculo de la puntuación de tendencia
uuid: 67270864-0468-4cc9-b48b-0e880f813555
exl-id: 679e1363-fd10-4a44-a85a-ef0daefaf303
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '320'
ht-degree: 1%

---

# Cálculo de la puntuación de tendencia{#calculating-propensity-scoring}

Se definen los cálculos estadísticos para la Puntuación de tendencia.

Conceptualmente, la puntuación calculada para cada visitante es una probabilidad estimada de que se pueda producir el evento especificado (definido por el filtro de objetivo), lo que da como resultado un rango de valor de puntuación del 0 al 100 por ciento. El procedimiento de puntuación utiliza las muestras existentes como datos de capacitación para encontrar la relación entre la probabilidad del evento y las variables de interés independientes seleccionadas.

Matemáticamente, esas relaciones se reflejan en cada valor cuantitativo asociado a cada variable independiente. Estos valores se denominan coeficientes modelo. Actualmente, ScoreDim utiliza el algoritmo de recuadros mínimos ponderados de forma iterativa (IRLS) para calcular los coeficientes del modelo. IRLS pasa por las muestras varias veces hasta que la diferencia de coeficientes entre la pasada actual y la pasada anterior es inferior a 1,0e-6, en cuyo punto se llama **convergente**. Sin embargo, dependiendo de los datos, es posible que el IRLS no pueda alcanzar la convergencia.

En tal caso, la iteración de formación modelo finalizará cuando

* la diferencia de coeficiente aumenta en lugar de ser menor,
* Se han alcanzado 1000 pases, o
* un error matemático evita la iteración continua.

Si IRLS no converge, se utilizará un algoritmo de copia de seguridad denominado Decente de degradado estocástico (SGD). SGD también pasará por las muestras de formación varias veces. Pero a diferencia de IRLS, los coeficientes del modelo SGD se controlan para que la diferencia entre iteración siempre disminuya de manera exponencial. Del mismo modo, la SGD finalizará cuando se haya alcanzado la diferencia de coeficiente inferior a 1,0e-6 o a 100.000 pasadas. El fallo de IRLS y la participación de SGD se registrarán en el registro de seguimiento.

Para ambos algoritmos, no todas las muestras se incluyen en la formación de modelos. El 80 por ciento se usa actualmente para entrenar al modelo. Una vez entrenado el modelo, el 20% restante de muestras se utilizará para evaluar la fuerza del modelo en términos de precisión, recuperación y precisión, que se calcula a partir de la matriz de confusión. Cuanto más cerca del 100%, mejor será el modelo de puntuación.
