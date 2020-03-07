---
description: Se definen los cálculos estadísticos de Puntuación de tendencia.
solution: Analytics
title: Cálculo de la puntuación de tendencia
topic: Data workbench
uuid: 67270864-0468-4cc9-b48b-0e880f813555
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Cálculo de la puntuación de tendencia{#calculating-propensity-scoring}

Se definen los cálculos estadísticos de Puntuación de tendencia.

Conceptualmente, la puntuación calculada para cada visitante es una probabilidad estimada de que se produzca el evento especificado (definido por el filtro de destino), lo que resulta en un rango de valor de puntuación de 0 a 100 por ciento. El procedimiento de puntuación utiliza muestras existentes como datos de formación para encontrar la relación entre la probabilidad del evento y las variables independientes de interés seleccionadas.

Desde el punto de vista matemático, esas relaciones se reflejan en cada valor cuantitativo asociado a cada variable independiente. Estos valores se denominan coeficientes de modelo. ScoreDim utiliza actualmente el algoritmo de cuadrados mínimos con ponderación iterativa (IRLS) para calcular los coeficientes del modelo. El IRLS atraviesa las muestras varias veces hasta que la diferencia de coeficientes entre la pasada actual y la pasada anterior es inferior a 1,0e-6, en cuyo momento se denomina **convergente**. Sin embargo, según los datos, es posible que el IRLS no pueda alcanzar la convergencia.

En ese caso, la iteración de formación del modelo finalizará cuando

* la diferencia de coeficiente aumenta en lugar de reducirse,
* Se han alcanzado 1.000 pases, o
* un error matemático evita la repetición continua.

Si IRLS no converge, se utilizará un algoritmo de copia de seguridad denominado Decente degradado estocástico (SGD). SGD también pasará varias veces por las muestras de formación. Pero a diferencia de IRLS, los coeficientes del modelo SGD están controlados de manera que la diferencia entre iteración siempre disminuirá de manera exponencial. Del mismo modo, SGD finalizará cuando se alcance una diferencia de coeficiente inferior a 1,0e-6 o a 100.000 pases. El fallo de IRLS y la participación de SGD se registrarán en el registro de seguimiento.

Para ambos algoritmos, no todos los ejemplos se incluyen en la formación de modelos. El 80 por ciento se utiliza actualmente para entrenar al modelo. Una vez entrenado el modelo, las muestras del 20 % restante se utilizarán para evaluar la intensidad del modelo en términos de precisión, recuperación y precisión, calculadas a partir de la matriz de confusión. Cuanto más se acerque al 100%, mejor será el modelo de puntuación.
