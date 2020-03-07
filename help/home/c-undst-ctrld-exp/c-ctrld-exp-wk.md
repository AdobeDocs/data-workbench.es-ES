---
description: En un experimento, puede definir cualquier número de grupos de prueba además del grupo de control.
solution: Insight,Analytics
title: ¿Cómo funcionan los experimentos controlados?
topic: Data workbench
uuid: 9549e2ab-dca9-4fb1-9729-65072f951900
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# ¿Cómo funcionan los experimentos controlados?{#how-do-controlled-experiments-work}

En un experimento, puede definir cualquier número de grupos de prueba además del grupo de control.

Cuando se ejecuta un experimento, todos los visitantes del sitio Web pasan a formar parte del mismo, ya sea como parte de un grupo de prueba o del grupo de control, en cuanto acceden a cualquier página involucrada en el experimento. Los visitantes se asignan a los grupos de experimentos de forma aleatoria, en proporciones definidas durante la configuración del experimento.

Los experimentos controlados se implementan utilizando el [!DNL Sensor] software que se instala en cada uno de los servidores de contenido del clúster web. A medida que los servidores de contenido reciben solicitudes, selecciona de forma aleatoria los visitantes para los grupos de prueba y redirecciona las solicitudes de página al contenido experimental. [!DNL Sensor] Cuando [!DNL Sensor] selecciona un visitante para ver el contenido de la prueba, la barra de direcciones sigue enumerando el URI solicitado originalmente, pero el visitante se enruta al URI de la prueba. Dado que este proceso se lleva a cabo internamente en la aplicación de servidor, los usuarios no saben cuándo se están probando, lo que es una consideración importante para una experimentación imparcial.

[!DNL Sensor] pasa los URI de prueba, no el URI original que se muestra al usuario, a los archivos de registro para su uso en análisis.

Los resultados de los experimentos se pueden analizar fácilmente [!DNL Insight] para determinar si la hipótesis experimental que estaba probando es correcta.

>[!NOTE]
>
>Adobe recomienda encarecidamente que los experimentos controlados se coordinen y realicen con la participación de las personas de su organización responsables de configurar y mantener sus conjuntos de datos de análisis.

