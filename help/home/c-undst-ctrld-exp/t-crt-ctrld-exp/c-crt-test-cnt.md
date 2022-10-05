---
description: Antes de configurar el experimento, debe crear el contenido alternativo que desee utilizar en él.
solution: Analytics
title: Creación del contenido de la prueba
uuid: d7996522-38a6-4bb8-9736-d71157c17b45
exl-id: fd46c6af-37e8-452a-880d-147b7d0cfe21
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '164'
ht-degree: 4%

---

# Creación del contenido de la prueba{#creating-the-test-content}

{{eol}}

Antes de configurar el experimento, debe crear el contenido alternativo que desee utilizar en él.

El grupo de control se envía al URI original, mientras que el grupo de prueba se envía al URI alternativo nuevo.

Para evitar confusiones, no vuelva a utilizar los nombres de archivo del grupo de prueba. Por ejemplo, si ejecuta un experimento utilizando un archivo de grupo de prueba denominado [!DNL test2.asp], no use [!DNL test2.asp] como nombre del archivo de prueba en el siguiente experimento.

Para la hipótesis de que el desplazamiento del vínculo gráfico &quot;Solicitar una demostración&quot; en la página principal afecta a la conversión de visitantes, creamos la página principal alternativa que contiene el vínculo gráfico &quot;Solicitar una demostración&quot; en la nueva posición. En la siguiente sección se describe cómo especificar el URI del grupo de control [!DNL index.asp] se reemplazará por el URI del grupo de prueba [!DNL index2.asp] para un determinado porcentaje de visitantes.
