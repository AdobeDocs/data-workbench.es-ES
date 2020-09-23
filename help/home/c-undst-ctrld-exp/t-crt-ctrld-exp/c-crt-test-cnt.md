---
description: Antes de configurar el experimento, debe crear el contenido alternativo que desee utilizar en el experimento.
solution: Analytics,Analytics
title: Creación del contenido de la prueba
topic: Data workbench
uuid: d7996522-38a6-4bb8-9736-d71157c17b45
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '164'
ht-degree: 4%

---


# Creación del contenido de la prueba{#creating-the-test-content}

Antes de configurar el experimento, debe crear el contenido alternativo que desee utilizar en el experimento.

El grupo de control se envía al URI original, mientras que el grupo de prueba se envía al URI alternativo nuevo.

Para evitar confusiones, no vuelva a utilizar nombres de archivo de grupo de prueba. Por ejemplo, si ejecuta un experimento con un archivo de grupo de prueba denominado [!DNL test2.asp], no lo utilice [!DNL test2.asp] como nombre para el archivo de prueba en el siguiente experimento.

Para la hipótesis de que mover el vínculo gráfico &quot;Solicitar una demostración&quot; en su página de inicio impacta en la conversión de Visitante, creamos la página de inicio alternativa que contiene el vínculo gráfico &quot;Solicitar una demostración&quot; en la nueva posición. En la sección siguiente se describe cómo especificar que el URI de grupo de control [!DNL index.asp] se reemplace por el URI de grupo de prueba [!DNL index2.asp] para un determinado porcentaje de visitantes.
