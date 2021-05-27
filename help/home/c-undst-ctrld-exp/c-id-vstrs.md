---
description: Una configuración típica del sitio usa cookies para identificar de forma exclusiva a los visitantes del sitio web y rastrear su comportamiento a lo largo del tiempo.
solution: Analytics,Analytics
title: ¿Cómo identifica el sitio a los visitantes?
uuid: e1e451b8-e827-4010-bda9-9147c3b09958
exl-id: 2783ee11-6d6a-463d-86b5-dd63e490201f
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '331'
ht-degree: 3%

---

# ¿Cómo identifica el sitio a los visitantes?{#how-does-site-identify-visitors}

Una configuración típica del sitio usa cookies para identificar de forma exclusiva a los visitantes del sitio web y rastrear su comportamiento a lo largo del tiempo.

La primera vez que un navegador en particular (considerado un visitante) realiza una solicitud a su sitio web, [!DNL Sensor] trabaja con su servidor web para establecer una cookie persistente (de forma predeterminada [!DNL cs(cookie)(v1st)]), que se interpreta internamente dentro del sistema como [!DNL x-trackingid]. Esta cookie se establece solo una vez, en la primera solicitud que ese visitante realizó a su sitio web. A continuación, se recopila de ese visitante cada vez que el explorador realiza una solicitud (ya sea una página o una solicitud de objeto incrustado) de su sitio web en el futuro.

La aceptación de una cookie persistente se realiza a criterio del explorador. Si un usuario decide bloquear las cookies persistentes, sus solicitudes de vista de página se seguirán registrando, pero los datos de medición de esas solicitudes no se correlacionarán con un visitante concreto ni con sus sesiones en el sitio web a menos que implemente un método alternativo de identificación de visitantes, como el uso de la transformación hash en los campos IP y AgenteUsuario .

>[!NOTE]
>
>Los experimentos del sitio solo se pueden analizar en conjuntos de datos donde el único método de identificación de visitantes que se utiliza es el método de cookie persistente [!DNL Sensor] establecido. Los sensores que se ejecutan en servidores J2EE (JBoss, Tomcat, WebLogic y WebSphere) no admiten experimentación controlada.

Durante un experimento controlado, los usuarios que no aceptan cookies pueden colocarse en diferentes grupos de experimentos de un clic a otro. Esto solo se convierte en un problema si realiza el análisis de la prueba con el filtro de sesión roto desactivado en [!DNL Insight], que no se recomienda con el Adobe.

Para obtener más información sobre el filtro de sesión interrumpida, consulte la * [!DNL Insight] Guía del usuario*.

Si un visitante borra la cookie durante un experimento, se asigna al visitante una nueva cookie y potencialmente podría asignarse a un grupo diferente. Como el Adobe identifica al visitante como nuevo, el experimento no se invalida.
