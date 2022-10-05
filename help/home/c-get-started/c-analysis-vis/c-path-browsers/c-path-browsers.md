---
description: Un explorador de rutas le permite analizar la secuencia en la que se accedió a los elementos de una dimensión en particular.
title: Exploradores de rutas
uuid: 548091dc-935f-41ac-b67c-39080988f1ea
exl-id: 563cf0e3-39d7-49b7-b808-b0233169fb1a
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '907'
ht-degree: 0%

---

# Exploradores de rutas{#path-browsers}

{{eol}}

Un explorador de rutas le permite analizar la secuencia en la que se accedió a los elementos de una dimensión en particular.

Para crear un explorador de rutas, arrastre y suelte un elemento de una dimensión en una visualización del explorador de rutas en blanco. El elemento que arrastra y suelta en el explorador de rutas se convierte en la raíz del explorador de rutas. El explorador de rutas muestra las rutas que pasan por la raíz, lo que permite ver la secuencia de elementos a los que se accedió antes y después de la raíz.

El siguiente navegador de rutas muestra la secuencia de películas que los espectadores clasificaron antes y después de clasificar la película *El Aviador*, que es la raíz del explorador de rutas. Cada nombre de película es un elemento de la dimensión Película , que se define en un conjunto de datos que consta de datos de películas que incluyen los nombres de películas y las clasificaciones de los espectadores de esas películas.

![](assets/vis_PathBrowser_Movies.png)

Puede crear exploradores de rutas para mostrar la secuencia en la que se accedió a los elementos de cualquier dimensión del conjunto de datos. Por ejemplo, si trabaja con datos de sitios web, puede crear un explorador de rutas que muestre la secuencia de páginas de sitios web a las que se accedió antes y después de la raíz de cada sesión en la que se vio la raíz o de cada visitante del sitio que vio la raíz.

![](assets/vis_PathBrowser_Pages.png)

Cada explorador de rutas tiene asociada una dimensión base, una dimensión de grupo, una dimensión de nivel y una métrica, que proporcionan claves para interpretar los datos que se muestran en el explorador de rutas.

* **Dimensión base:** Cuando arrastra y suelta un elemento raíz en el explorador de rutas, arrastra y suelta un elemento de la dimensión base. Todos los demás elementos que aparecen en las rutas son elementos de la dimensión base. Puede cambiar la dimensión base arrastrando y soltando un elemento de otra dimensión en el explorador de rutas.
* **Dimensión de nivel:** Cada dimensión del conjunto de datos tiene una dimensión de nivel asociada (también denominada dimensión principal). La dimensión de nivel para el explorador de rutas debe ser la misma que la dimensión de nivel (o principal) para la dimensión base del explorador de rutas. La dimensión de nivel del explorador de rutas es importante por dos motivos principales:

   * A medida que sigue una ruta de un elemento de dimensión base al siguiente, pasa de un elemento de dimensión de nivel al siguiente. Por ejemplo, supongamos que ha creado un navegador de rutas que muestra las páginas de un sitio web. Cada página es un elemento de la dimensión Página y la dimensión de nivel de Página es Vista de página. A medida que pasa de una página a otra, pasa de una vista de página a la siguiente.
   * Al seleccionar una ruta de elementos de dimensión base dentro de un explorador de rutas, se seleccionan datos para los elementos correspondientes de la dimensión de nivel. La selección siempre incluye los elementos de la dimensión de nivel que se relacionan con la raíz y se refina añadiendo más elementos a la ruta. Por ejemplo, cuando selecciona una ruta de páginas, como root > A > B, está seleccionando datos para las vistas de página asociadas con la raíz, donde la siguiente página es A y la siguiente es B.

      Para obtener información sobre cómo seleccionar una ruta en un explorador de rutas, consulte [Selección de rutas](../../../../home/c-get-started/c-analysis-vis/c-path-browsers/t-sel-paths.md#task-bf44d08c71954ef2adec4b82f840adeb). Para obtener información sobre las selecciones, consulte [Realización de selecciones en visualizaciones](../../../../home/c-get-started/c-vis/c-sel-vis/c-sel-vis.md#concept-012870ec22c7476e9afbf3b8b2515746).
   >[!NOTE]
   >
   >El explorador de rutas ignora los elementos de la dimensión de nivel sin elementos de dimensión base asociados. Esta situación puede ocurrir cuando se crea un explorador de rutas a partir de un mapa de procesos. Consulte [Creación de exploradores de rutas](../../../../home/c-get-started/c-analysis-vis/c-path-browsers/c-create-path-browsers.md#concept-e120de6a740d4b6f98dda9e2b638f6ff).

* **Dimensión de grupo:** La dimensión de grupo determina cómo se agrupan los elementos de la dimensión de nivel para formar las rutas de un explorador de rutas. Específicamente, los elementos de dimensión de nivel asociados con una sola ruta en un explorador de rutas no pueden abarcar más de un elemento de una dimensión de grupo.

   Para entender esto, considere un ejemplo de uso de datos web. Supongamos que las dimensiones base, nivel y grupo para su navegador de rutas son Página, Vista de página y Sesión, respectivamente. Una ruta en el explorador de rutas muestra la secuencia de páginas A > B > C. La dimensión de grupo (Sesión) indica que las vistas de página (elementos de la dimensión Vista de página) asociadas con la secuencia de página A > B > C se produjeron durante cualquier sesión única. Es importante tener en cuenta que puede haber varias sesiones durante las cuales hubo vistas de página para la secuencia de página A > B > C. Por lo tanto, la ruta que muestra la secuencia de página A > B > C representa todas las sesiones individuales en las que se produjeron las vistas de página de esa secuencia.

* **Métrica**: El grosor de la ruta que conduce a un elemento determinado es proporcional al valor de la métrica para ese elemento. Las rutas más gruesas indican valores de métricas buenos que las rutas más delgadas.

La etiqueta de la esquina superior izquierda del explorador de rutas asigna un nombre a las dimensiones base y de grupo representadas en la visualización. El nombre de la dimensión de nivel no es visible en la visualización del explorador de rutas de acceso. La etiqueta adopta la forma &quot;Secuencia de *nombre de la dimensión base*+s para cada *nombre de la dimensión del grupo*.&quot; Por ejemplo, la etiqueta Secuencia de películas para cada usuario indica que la dimensión base es Película y la dimensión de grupo es Usuario.

![](assets/vis_PathBrowser_Movies.png)

Al hacer clic con el botón derecho en cualquier elemento del explorador de rutas, puede ver el nombre de la métrica asociada con el explorador de rutas y su valor para ese elemento.

![](assets/vis_PathBrowser_RightClick.png)

>[!NOTE]
>
>Puede cambiar las dimensiones y métricas predeterminadas de un explorador de rutas. Para obtener instrucciones para configurar una visualización del explorador de rutas, consulte [Configuración de exploradores de rutas](../../../../home/c-get-started/c-intf-anlys-ftrs/t-config-path-brwsr.md#task-bbb3ddaa140a414f984b697c2b8202a3).
