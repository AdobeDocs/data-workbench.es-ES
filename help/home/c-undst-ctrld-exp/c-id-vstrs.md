---
description: Una configuración típica del sitio utiliza cookies para identificar de forma exclusiva a los visitantes del sitio Web y rastrear su comportamiento con el paso del tiempo.
solution: Insight,Analytics
title: ¿Cómo identifica el sitio a los visitantes?
topic: Data workbench
uuid: e1e451b8-e827-4010-bda9-9147c3b09958
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# ¿Cómo identifica el sitio a los visitantes?{#how-does-site-identify-visitors}

Una configuración típica del sitio utiliza cookies para identificar de forma exclusiva a los visitantes del sitio Web y rastrear su comportamiento con el paso del tiempo.

La primera vez que un navegador en particular (considerado un visitante) realiza una solicitud de su sitio web, [!DNL Sensor] trabaja con su servidor web para configurar una cookie persistente (de forma predeterminada [!DNL cs(cookie)(v1st)]), que se interpreta internamente dentro del sistema como [!DNL x-trackingid]. Esta cookie se establece una sola vez, en la primera solicitud que el visitante hace a su sitio web. A continuación, se recopila de ese visitante cada vez que el explorador realiza una solicitud (ya sea de página o de objeto incrustado) del sitio web en el futuro.

La aceptación de una cookie persistente se realiza a discreción del explorador. Si un usuario decide bloquear las cookies persistentes, sus solicitudes de vistas de página se seguirán registrando, pero los datos de medición de dichas solicitudes no se correlacionarán con un visitante en particular ni con sus sesiones en el sitio web, a menos que implemente un método alternativo de identificación de visitantes, como el uso de la transformación hash en los campos IP y UserAgent.

>[!NOTE]
>
>Los experimentos del sitio solo se pueden analizar en conjuntos de datos donde el único método de identificación del visitante que se utiliza es el [!DNL Sensor] método de cookie persistente establecido. Los sensores que se ejecutan en servidores J2EE (JBoss, Tomcat, WebLogic y WebSphere) no admiten la experimentación controlada.

Durante un experimento controlado, los usuarios que no aceptan cookies pueden colocarse en diferentes grupos de experimentos de un clic al otro. Esto se convierte en un problema solamente si realiza el análisis de prueba con el filtro de sesión interrumpido desactivado en [!DNL Insight], que Adobe no recomienda.

Para obtener más información sobre el filtro de sesión interrumpida, consulte la * [!DNL Insight] Guía del usuario*.

Si un visitante borra la cookie durante un experimento, se le asigna una nueva cookie y posiblemente se le pueda asignar a otro grupo. Dado que Adobe identifica al visitante como nuevo, el experimento no se invalida.
