---
description: Los resultados de las pruebas deben ser claros y significativos para que pueda sentirse seguro de tomar decisiones importantes en dólares basadas en esos resultados.
solution: Analytics,Analytics
title: ¿Qué debería probar?
topic: Data workbench
uuid: 9dfe3685-885e-4098-ab1d-ac891ccc5199
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '431'
ht-degree: 1%

---


# ¿Qué debería probar?{#what-should-i-test}

Los resultados de las pruebas deben ser claros y significativos para que pueda sentirse seguro de tomar decisiones importantes en dólares basadas en esos resultados.

Aunque puede probar varios diseños de página con [!DNL Sensor] y sitio, Adobe sugiere que se centre en probar las iniciativas comerciales estratégicas de alto valor o las funcionalidades de sitios web nuevos o rediseñados que se dirijan a los objetivos establecidos para el sitio web y para su negocio. Puede probar problemas como las mejores garantías de precios, la funcionalidad de personalización, las ofertas de mercado (por ejemplo, paquetes o paquetes), el diseño creativo y los procesos de aplicación.

Los siguientes conceptos son los más importantes al desarrollar el experimento controlado:

* **Comprender los cambios correctos que se deben realizar.** Esto requiere una cierta investigación sobre cómo funciona su sitio web y los procesos comerciales subyacentes al sitio web front-end. Desea realizar cambios que proporcionen el mayor impacto y se puedan probar fácilmente.
* **Los cambios pequeños pueden tener un impacto significativo.** No todos los cambios que pruebe deben ser drásticos para tener un impacto significativo en su negocio. Siempre esté abierto a realizar cambios pequeños pero muy importantes.

## Metodologías admitidas {#section-1071adaf54c64ba9bc5ef228c4a23635}

Se pueden realizar muchos tipos de experimentos con muchos objetivos diferentes mediante el uso del sitio. La siguiente lista proporciona algunos ejemplos:

* Modificar los procesos de páginas, contenido y sitios web para mejorar las tasas de conversión.
* Cambiar las campañas de mercadotecnia, las promociones, las ventas cruzadas y las ventas ascendentes para aumentar los ingresos.
* Variación de los tiempos de carga de la página para comprender la calidad del servicio del cliente y el valor real del rendimiento de la infraestructura.

Para alcanzar estos objetivos, el sitio admite los siguientes tipos de metodologías para pruebas y experimentos controlados:

* **Sustitución de página:** Reemplazar la dirección URL estática X con la dirección URL estática Y. Esta metodología es de uso limitado en un entorno dinámico.
* **Sustitución de URI dinámica:** Se trata de una variante de Sustitución de página que sustituye la página estática X por la página dinámica Y para representar contenido dinámico.
* **Sustitución de objetos:** Reemplazar el objeto fijo X con el objeto fijo Y.
* **Reemplazo de contenido:** Reemplace el conjunto de contenido X (varios objetos, páginas, tabla, etc.) por el conjunto de contenido Y.
* **Sustitución de la variable del experimento:** Reemplace el objeto JavaScript /writeCookie_X.js con el objeto JavaScript /writeCookie_Y.js para escribir una cookie que pueda ser utilizada por un sistema back-end para proporcionar contenido determinado.

>[!NOTE]
>
>Los experimentos controlados se basan en la sustitución de URI, no en la sustitución de cadenas de consulta. El URI dentro de una dirección URL concreta se resalta en el siguiente ejemplo:
>
>`http://www.omniture.com/index.asp?id=1`
>
>Por ejemplo, en el experimento controlado puede especificar que el URI de grupo de control [!DNL index.asp] se reemplace por el URI de grupo de prueba [!DNL index2.asp] para determinar qué diseño de página resultaría en más valor.
