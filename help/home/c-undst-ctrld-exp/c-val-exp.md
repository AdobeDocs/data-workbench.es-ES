---
description: Después de implementar el experimento, debe validar que el experimento funciona correctamente.
solution: Analytics,Analytics
title: Validación del experimento
topic: Data workbench
uuid: 59769f5b-4175-479e-ad7d-7226e9c666af
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '273'
ht-degree: 2%

---


# Validación del experimento{#validating-the-experiment}

Después de implementar el experimento, debe validar que el experimento funciona correctamente.

Como se explica en [Modificación del parámetro ExpCookieURL (opcional)](../../home/c-undst-ctrld-exp/t-en-ctrld-exp/c-mod-expckurl-prm.md#concept-215bf86bab4e4ec0b0cc803ec48a8fcf)[!DNL Sensor] , la página especificada en el parámetro ExpCookieURL en el archivo de configuración puede utilizarse para ubicarse en un grupo de experimentos específico.

La página virtual predeterminada es [!DNL /setcookie.htm]pero debe utilizar el valor que ha establecido en el parámetro ExpCookieURL.

## Solicitud de la página de prueba {#section-8aed3b48d47f4e6c8869c0216f8781b1}

Para probar un grupo de experimentos específico para su sitio web, el explorador debe configurarse para aceptar cookies y no debe tener ya una cookie para este sitio web.

Cada vez que desee probar un nuevo grupo, asegúrese de borrar las cookies del sitio Web.

Para colocarse en un grupo específico dentro de un experimento específico, solicite la página de prueba con una cadena de consulta en el siguiente formulario:

[!DNL http://] *&lt;[!DNL sitename/?Experiment Name=Group Name]>*

Por ejemplo:

[!DNL http://www.omniture.com/setcookie.htm?New_Homepage=index2]

Cuando la solicitud de URL virtual se envía al servidor, [!DNL Sensor] lo identifica como miembro del grupo especificado dentro del experimento especificado y, a continuación, lo redirige a la raíz del sitio web. Ahora puede desplazarse a la ubicación adecuada en el sitio web para validar si se muestra el contenido correcto para ese experimento y grupo.

Si escribiera lo siguiente en el explorador, éste mostrará la página de inicio del sitio web y lo colocará en el grupo index2 dentro del experimento New_Homepage:

[!DNL http://www.omniture.com/setcookie.htm?New_Homepage=index2]

Cuando los visitantes del grupo index2 solicitan la página de inicio, el vínculo gráfico &quot;Solicitar una demostración&quot; aparece más arriba en la página, como en el siguiente gráfico:

![](assets/TestPage.png)

