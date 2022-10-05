---
description: Los resultados de las pruebas deben ser claros y significativos para que pueda sentirse seguro de tomar decisiones importantes en dólares basadas en esos resultados.
solution: Analytics
title: ¿Qué debería probar?
uuid: 9dfe3685-885e-4098-ab1d-ac891ccc5199
exl-id: 0f06ff0f-b385-4614-8007-afdb85191a85
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '431'
ht-degree: 1%

---

# ¿Qué debería probar?{#what-should-i-test}

{{eol}}

Los resultados de las pruebas deben ser claros y significativos para que pueda sentirse seguro de tomar decisiones importantes en dólares basadas en esos resultados.

Aunque puede probar varios diseños de página con [!DNL Sensor] y Sitio, el Adobe sugiere que se centre en probar las iniciativas empresariales estratégicas de alto valor o en la funcionalidad de sitios web nuevos o rediseñados que aborden los objetivos establecidos para su sitio web, así como para su negocio. Puede probar problemas como las mejores garantías de precios, la funcionalidad de personalización, las ofertas de mercado (por ejemplo, paquetes o paquetes), el diseño creativo y los procesos de aplicación.

Los siguientes conceptos son más importantes al desarrollar su experimento controlado:

* **Comprender los cambios correctos.** Esto requiere cierta investigación sobre cómo funciona su sitio web y los procesos comerciales subyacentes al sitio web front-end. Desea realizar cambios que proporcionen el mayor impacto y se puedan probar fácilmente.
* **Los cambios pequeños pueden tener un impacto significativo.** No todos los cambios que pruebe deben ser drásticos para tener un impacto significativo en su negocio. Siempre esté abierto a realizar cambios pequeños, pero muy importantes.

## Metodologías admitidas {#section-1071adaf54c64ba9bc5ef228c4a23635}

Se pueden realizar muchos tipos de experimentos con muchos objetivos diferentes a través del sitio. La siguiente lista proporciona algunos ejemplos:

* Modificar los procesos de páginas, contenido y sitio web para mejorar las tasas de conversión.
* Cambiar las campañas de marketing, las promociones, las ventas cruzadas y las ventas ascendentes para aumentar los ingresos.
* Diferentes tiempos de carga de las páginas para comprender la calidad del servicio del cliente y el valor real del rendimiento de la infraestructura.

Para alcanzar estos objetivos, Site admite los siguientes tipos de metodologías para la experimentación y prueba controladas:

* **Sustitución de página:** Reemplace la dirección URL estática X por la dirección URL estática Y. Esta metodología es de uso limitado en un entorno dinámico.
* **Sustitución de URI dinámico:** Se trata de una variante de Sustitución de página que sustituye la página estática X por la página dinámica Y para representar contenido dinámico.
* **Sustitución de objetos:** Reemplace el objeto fijo X por el objeto fijo Y.
* **Sustitución de contenido:** Reemplace el conjunto de contenido X (varios objetos, páginas, tabla, etc.) por el conjunto de contenido Y.
* **Sustitución de la variable del experimento:** Reemplace el objeto de JavaScript /writeCookie_X.js con el objeto de JavaScript /writeCookie_Y.js para escribir una cookie que pueda ser utilizada por un sistema back-end para servir contenido determinado.

>[!NOTE]
>
>Los experimentos controlados se basan en el reemplazo de URI, no en el reemplazo de cadena de consulta. El URI de una URL en particular se resalta en el siguiente ejemplo:
>
>`https://www.omniture.com/index.asp?id=1`
>
>Por ejemplo, en el experimento controlado, puede especificar que el URI del grupo de control [!DNL index.asp] se reemplazará por el URI del grupo de prueba [!DNL index2.asp] para determinar qué diseño de página resultaría en más valor.
