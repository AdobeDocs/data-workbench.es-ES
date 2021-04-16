---
description: Después de haber implementado el experimento, debe validar que funcione correctamente.
solution: Analytics,Analytics
title: Validación del experimento
uuid: 59769f5b-4175-479e-ad7d-7226e9c666af
exl-id: 6dfd01ca-288d-40fd-aad4-75a588902ebd
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '273'
ht-degree: 2%

---

# Validación del experimento{#validating-the-experiment}

Después de haber implementado el experimento, debe validar que funcione correctamente.

Como se explica en [Modificación del parámetro ExpCookieURL (opcional)](../../home/c-undst-ctrld-exp/t-en-ctrld-exp/c-mod-expckurl-prm.md#concept-215bf86bab4e4ec0b0cc803ec48a8fcf), la página especificada en el parámetro ExpCookieURL del archivo de configuración [!DNL Sensor] puede utilizarse para colocarse en un grupo de experimentos específico.

La página virtual predeterminada es [!DNL /setcookie.htm], pero debe utilizar el valor establecido en el parámetro ExpCookieURL.

## Solicitud de la página de prueba {#section-8aed3b48d47f4e6c8869c0216f8781b1}

Para probar un grupo de experimentos específico para su sitio web, su explorador debe estar configurado para aceptar cookies y no debe tener ya una cookie para este sitio web.

Cada vez que desee probar un grupo nuevo, asegúrese de borrar las cookies del sitio web.

Para colocarse en un grupo específico dentro de un experimento específico, solicite la página de prueba con una cadena de consulta en el siguiente formulario:

[!DNL http://] *&lt; [!DNL sitename/?Experiment Name=Group Name]>*

Por ejemplo:

[!DNL http://www.omniture.com/setcookie.htm?New_Homepage=index2]

Cuando se envía la solicitud de URL virtual al servidor, [!DNL Sensor] lo identifica como miembro del grupo especificado en el experimento especificado y luego lo redirige a la raíz del sitio web. Ahora puede desplazarse a la ubicación apropiada del sitio web para validar si el contenido correcto se muestra para ese experimento y grupo.

Si escribiera lo siguiente en su explorador, el explorador mostraría la página principal del sitio web y lo colocaría en el grupo index2 dentro del experimento New_Homepage :

[!DNL http://www.omniture.com/setcookie.htm?New_Homepage=index2]

Cuando los visitantes del grupo index2 solicitan la página principal, el vínculo gráfico &quot;Solicitar una demostración&quot; aparece más arriba en la página, como en el siguiente gráfico:

![](assets/TestPage.png)
