---
description: El sitio utiliza cookies para identificar de forma exclusiva a los visitantes del sitio web y realizar un seguimiento de su comportamiento a lo largo del tiempo.
title: Explicación de la cookie v1st
uuid: 6112cafe-51e3-42f0-8554-4a653dea782a
exl-id: c5e8e1cb-686b-4d31-821e-60beb2808f80
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '510'
ht-degree: 2%

---

# Explicación de la cookie v1st{#understanding-the-v-st-cookie}

{{eol}}

El sitio utiliza cookies para identificar de forma exclusiva a los visitantes del sitio web y realizar un seguimiento de su comportamiento a lo largo del tiempo.

La primera vez que un navegador en particular (considerado un visitante) realiza una solicitud a su sitio web, [!DNL Sensor] funciona con su servidor web para establecer una cookie persistente, cs(cookie)(v1st), que se interpreta internamente dentro del sistema como x-trackingid. Esta cookie persistente se configura además de cualquier otra cookie que su sitio pueda establecer de otra manera. Esta cookie optimiza su capacidad de rastrear a los visitantes en varias sesiones, lo que permite muchos tipos de análisis que, de lo contrario, son imposibles.

[!DNL Sensor] asigna una clave numérica de 64 bits en la cookie para identificar a los nuevos visitantes que realizan una solicitud al sitio como un identificador único. Cuando la variable [!DNL Sensor] ve una solicitud de un explorador, comprueba si &quot;cs(cookie)(v1st)&quot;, una cookie persistente de origen establecida por [!DNL Sensor], existe en los datos de solicitud. Si el cs(cookie)(v1st) no está presente, [!DNL Sensor], a través del servidor web, indica al explorador que lo establezca. A diferencia de otras soluciones, [!DNL Sensor] puede establecer esta cookie en la primera solicitud del visitante.

A continuación, se muestra el encabezado de cookie persistente estándar que su servidor web envía al explorador en la primera solicitud de su sitio, en la dirección de [!DNL Sensor]. El formato se puede definir en el momento de la configuración si se desea un nombre o una fecha de caducidad diferentes. Por ejemplo:

```
Set-Cookie:v1st=3D80DCA944D60E16; path=/; expires=Wed, 19 Feb 2020 14:28:00 GMT
```

Esta cookie se establece una sola vez, en la primera solicitud que hizo ese visitante a su sitio. A continuación, se recopila de ese visitante cada vez que el explorador realiza una solicitud del sitio (ya sea una página o una solicitud de objeto incrustado) en el futuro. El tamaño de la cookie es muy pequeño para minimizar la cantidad de ancho de banda usado para transmitirla a sus servidores con cada solicitud de ese explorador a su sitio.

La aceptación de una cookie persistente se realiza a criterio del explorador. La mayoría de los usuarios de la web entienden qué hacen las cookies y también reconocen que las cookies de origen les proporcionan una ventaja valiosa al permitirles personalizar el contenido del sitio según sus preferencias. Estas cookies de origen no están bloqueadas por la configuración de seguridad predeterminada de los navegadores más populares. Si un usuario decide bloquear las cookies de origen, sus solicitudes de vista de página se seguirán registrando, pero los datos de medición de esas solicitudes no se podrán correlacionar de forma fiable con un visitante concreto o con sus sesiones en el sitio. Muchos sitios, especialmente los sitios dinámicos sofisticados, ya utilizan cookies de origen, que en muchos casos son necesarias para permitir que las aplicaciones web funcionen para el visitante. Un paso atrás de una cookie persistente es una cookie de sesión, que permite unir una serie de solicitudes en una sesión, pero no permite el seguimiento de visitantes entre sesiones. [!DNL Site] es capaz de clasificar los datos del visitante en función de las cookies de sesión o por número de IP, pero ambos métodos reducen considerablemente los tipos y el valor de los análisis que se pueden realizar con [!DNL Site] o cualquier otro sistema de informes y análisis de actividad web.
