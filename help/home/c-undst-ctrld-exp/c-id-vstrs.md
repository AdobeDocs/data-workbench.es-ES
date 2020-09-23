---
description: Una configuración típica del sitio utiliza las cookies para identificar de forma exclusiva los visitantes del sitio Web y rastrear su comportamiento a lo largo del tiempo.
solution: Analytics,Analytics
title: ¿Cómo identifica el sitio a los visitantes?
topic: Data workbench
uuid: e1e451b8-e827-4010-bda9-9147c3b09958
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '331'
ht-degree: 3%

---


# ¿Cómo identifica el sitio a los visitantes?{#how-does-site-identify-visitors}

Una configuración típica del sitio utiliza las cookies para identificar de forma exclusiva los visitantes del sitio Web y rastrear su comportamiento a lo largo del tiempo.

La primera vez que un navegador en particular (considerado un visitante) realiza una solicitud de su sitio web, [!DNL Sensor] trabaja con su servidor web para configurar una cookie persistente (de forma predeterminada [!DNL cs(cookie)(v1st)]), que se interpreta internamente dentro del sistema como [!DNL x-trackingid]. Esta cookie se configura sólo una vez, en la primera solicitud que ese visitante hace a su sitio web. Luego se recopila de ese visitante cada vez que el explorador realiza una solicitud (ya sea de página o de objeto incrustado) del sitio web en el futuro.

La aceptación de una cookie persistente se realiza a discreción del explorador. Si un usuario decide bloquear las cookies persistentes, sus solicitudes de vista de página se seguirán registrando, pero los datos de medición de dichas solicitudes no estarán correlacionados con un visitante en particular o con sus sesiones en el sitio web, a menos que implemente un método alternativo de identificación de visitantes, como el uso de la transformación hash en los campos IP y UserAgent.

>[!NOTE]
>
>Los experimentos del sitio sólo se pueden analizar en conjuntos de datos en los que el único método de identificación de visitantes en uso es el [!DNL Sensor] método de cookie persistente establecido. Los sensores que se ejecutan en servidores J2EE (JBoss, Tomcat, WebLogic y WebSphere) no admiten la experimentación controlada.

Durante un experimento controlado, los usuarios que no aceptan cookies pueden colocarse en diferentes grupos de experimentos de un clic al otro. Esto se convierte en un problema solamente si realiza la análisis de prueba con el filtro de sesión interrumpido desactivado en [!DNL Insight], Adobe que no se recomienda.

Para obtener más información sobre el filtro de sesión interrumpida, consulte la * [!DNL Insight] Guía del usuario*.

Si un visitante borra la cookie durante un experimento, al visitante se le asigna una nueva cookie y se le puede asignar potencialmente a un grupo diferente. Como Adobe identifica el visitante como nuevo, el experimento no se invalida.
