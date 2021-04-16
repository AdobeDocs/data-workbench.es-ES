---
description: En un experimento, puede definir cualquier número de grupos de prueba además del grupo de control.
solution: Analytics,Analytics
title: ¿Cómo funcionan los experimentos controlados?
uuid: 9549e2ab-dca9-4fb1-9729-65072f951900
exl-id: 1d3af6a2-078e-4eb8-848e-685f531a60c5
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '265'
ht-degree: 3%

---

# ¿Cómo funcionan los experimentos controlados?{#how-do-controlled-experiments-work}

En un experimento, puede definir cualquier número de grupos de prueba además del grupo de control.

Cuando se ejecuta un experimento, todos los visitantes del sitio web forman parte del experimento, ya sea como parte de un grupo de prueba o del grupo de control, en cuanto acceden a cualquier página involucrada en el experimento. Los visitantes se asignan a los grupos de experimentos de forma aleatoria, en proporciones definidas durante la configuración del experimento.

Los experimentos controlados se implementan utilizando el software [!DNL Sensor] que se instala en cada uno de los servidores de contenido del clúster web. A medida que los servidores de contenido reciben solicitudes, [!DNL Sensor] selecciona de forma aleatoria a los visitantes de los grupos de prueba y redirige sus solicitudes de página al contenido experimental. Cuando [!DNL Sensor] selecciona un visitante para ver el contenido de la prueba, la barra de direcciones continúa enumerando el URI solicitado originalmente, pero el visitante se redirige al URI de la prueba. Debido a que este proceso se lleva a cabo internamente en la aplicación de servidor, los usuarios no son conscientes de cuándo se están probando, lo que es una consideración importante para una experimentación imparcial.

[!DNL Sensor] pasa los URI de prueba, no el URI original mostrado al usuario, a los archivos de registro para su uso en análisis.

Los resultados de los experimentos se pueden analizar fácilmente utilizando [!DNL Insight] para determinar si la hipótesis experimental que estaba probando es correcta.

>[!NOTE]
>
>Adobe recomienda encarecidamente que los experimentos controlados se coordinen y realicen con la información de las personas de su organización responsables de configurar y mantener sus conjuntos de datos de análisis.
