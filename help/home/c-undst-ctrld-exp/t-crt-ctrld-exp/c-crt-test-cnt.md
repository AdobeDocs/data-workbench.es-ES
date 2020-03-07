---
description: Antes de configurar el experimento, debe crear el contenido alternativo que desee utilizar en el experimento.
solution: Insight,Analytics
title: Creación del contenido de la prueba
topic: Data workbench
uuid: d7996522-38a6-4bb8-9736-d71157c17b45
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Creación del contenido de la prueba{#creating-the-test-content}

Antes de configurar el experimento, debe crear el contenido alternativo que desee utilizar en el experimento.

El grupo de control se envía al URI original, mientras que el grupo de prueba se envía al URI alternativo nuevo.

Para evitar confusiones, no vuelva a utilizar nombres de archivo de grupo de prueba. Por ejemplo, si ejecuta un experimento con un archivo de grupo de prueba denominado [!DNL test2.asp], no lo utilice [!DNL test2.asp] como nombre para el archivo de prueba en el siguiente experimento.

Para la hipótesis de que mover el vínculo gráfico &quot;Solicitar una demostración&quot; en la página principal afecta a la conversión del visitante, creamos la página principal alternativa que contiene el vínculo gráfico &quot;Solicitar una demostración&quot; en la nueva posición. En la sección siguiente se describe cómo especificar que el URI del grupo de control [!DNL index.asp] se reemplace por el URI del grupo de prueba [!DNL index2.asp] para un determinado porcentaje de visitantes.
