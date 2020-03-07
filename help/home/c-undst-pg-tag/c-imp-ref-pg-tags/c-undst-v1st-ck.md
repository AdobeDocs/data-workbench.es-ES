---
description: El sitio utiliza cookies para identificar de forma exclusiva a los visitantes del sitio Web y rastrear su comportamiento con el paso del tiempo.
solution: Analytics
title: Explicación de la cookie v1st
topic: Data workbench
uuid: 6112cafe-51e3-42f0-8554-4a653dea782a
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Explicación de la cookie v1st{#understanding-the-v-st-cookie}

El sitio utiliza cookies para identificar de forma exclusiva a los visitantes del sitio Web y rastrear su comportamiento con el paso del tiempo.

La primera vez que un navegador en particular (considerado un visitante) realiza una solicitud de su sitio web, [!DNL Sensor] trabaja con su servidor web para configurar una cookie persistente, cs(cookie)(v1st), que se interpreta internamente dentro del sistema como x-trackingid. Esta cookie persistente se configura además de cualquier otra cookie que su sitio pueda configurar de otra manera. Esta cookie optimiza su capacidad para rastrear a los visitantes en varias sesiones, lo que permite muchos tipos de análisis que de otra manera son imposibles.

[!DNL Sensor] asigna una clave numérica de 64 bits en la cookie para identificar a los nuevos visitantes que realizan una solicitud al sitio como un identificador único. Cuando el usuario [!DNL Sensor] ve una solicitud desde un explorador, comprueba si &quot;cs(cookie)(v1st)&quot;, una cookie persistente de origen configurada por [!DNL Sensor], existe en los datos de la solicitud. Si la cookie cs(cookie)(v1st) no está presente, [!DNL Sensor]a través de su servidor web, indica al explorador que la configure. A diferencia de otras soluciones, [!DNL Sensor] puede establecer esta cookie en la primera solicitud del visitante.

A continuación se muestra el encabezado de cookie persistente estándar enviado al explorador en la primera solicitud de su sitio por su servidor Web, en la dirección de [!DNL Sensor]. El formato se puede definir en el momento de la configuración si se desea un nombre o una fecha de caducidad diferentes. Por ejemplo:

```
Set-Cookie:v1st=3D80DCA944D60E16; path=/; expires=Wed, 19 Feb 2020 14:28:00 GMT
```

Esta cookie se configura una sola vez, en la primera solicitud que ese visitante hace a su sitio. Luego se recopila de ese visitante cada vez que ese explorador realiza una solicitud (ya sea de página o de objeto incrustado) del sitio en el futuro. El tamaño de la cookie es muy pequeño para minimizar la cantidad de ancho de banda utilizado para transmitirla a los servidores con cada solicitud de ese explorador a su sitio.

La aceptación de una cookie persistente se realiza a discreción del explorador. La mayoría de los usuarios de la Web entienden qué hacen las cookies y también reconocen que las cookies de origen les proporcionan una ventaja valiosa al permitirles personalizar el contenido del sitio según sus preferencias. Estas cookies de origen no están bloqueadas por la configuración de seguridad predeterminada de los navegadores más populares. Si un usuario decide bloquear las cookies de origen, sus solicitudes de vista de página se seguirán registrando, pero los datos de medición de dichas solicitudes no se pueden correlacionar de forma fiable con un visitante en particular o con sus sesiones en el sitio. Muchos sitios, especialmente los sitios dinámicos sofisticados, ya utilizan cookies de origen, que en muchos casos son necesarias para permitir que las aplicaciones Web funcionen para el visitante. Un paso atrás de una cookie persistente es una cookie de sesión, que permite unir una serie de solicitudes en una sesión, pero no permite el seguimiento de visitantes entre sesiones. [!DNL Site] es capaz de clasificar los datos del visitante en función de cookies de sesión o por número de IP, pero ambos métodos reducen considerablemente los tipos y el valor de los análisis que se pueden realizar con [!DNL Site] o con cualquier otro sistema de informes y análisis de actividad web.
