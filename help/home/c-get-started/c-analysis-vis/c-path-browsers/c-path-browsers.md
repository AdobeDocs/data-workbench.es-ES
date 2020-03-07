---
description: Un navegador de rutas permite analizar la secuencia en la que se accedió a los elementos de una dimensión concreta.
solution: Analytics
title: Exploradores de rutas
topic: Data workbench
uuid: 548091dc-935f-41ac-b67c-39080988f1ea
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Exploradores de rutas{#path-browsers}

Un navegador de rutas permite analizar la secuencia en la que se accedió a los elementos de una dimensión concreta.

Para crear un navegador de rutas, arrastre y suelte un elemento de una dimensión en una visualización del navegador de rutas en blanco. El elemento que arrastra y suelta en el explorador de rutas se convierte en la raíz del explorador de rutas. El navegador de rutas muestra las rutas que pasan por la raíz, lo que permite ver la secuencia de elementos a los que se accedió antes y después de la raíz.

El siguiente navegador de rutas muestra la secuencia de películas que los visores clasificaron antes y después de clasificar la película *The Aviator*, que es la raíz del navegador de rutas. Cada nombre de película es un elemento de la dimensión Película, que se define en un conjunto de datos formado por datos de películas que incluyen los nombres de las películas y las clasificaciones de los visores de dichas películas.

![](assets/vis_PathBrowser_Movies.png)

Puede crear exploradores de rutas para mostrar la secuencia en la que se accedió a los elementos de cualquier dimensión del conjunto de datos. Por ejemplo: si está trabajando con datos de sitios web, puede crear un explorador de rutas que muestre la secuencia de páginas de sitios web a las que se accedió antes y después de la raíz para cada sesión en la que se vio la raíz o para cada visitante del sitio que vio la raíz.

![](assets/vis_PathBrowser_Pages.png)

Cada explorador de rutas tiene una dimensión base, una dimensión de grupo, una dimensión de nivel y una métrica asociadas, que proporcionan claves para interpretar los datos que se muestran en el explorador de rutas.

* **Dimensión base:** Cuando arrastra y suelta un elemento raíz en el navegador de rutas, arrastra y suelta un elemento de la dimensión base. Todos los demás elementos que aparecen en las rutas son elementos de la dimensión base. Puede cambiar la dimensión base arrastrando y soltando un elemento de otra dimensión en el navegador de rutas.
* **Dimensión de nivel:** Cada dimensión del conjunto de datos tiene una dimensión de nivel asociada (también denominada principal). La dimensión de nivel para el explorador de rutas debe ser la misma que la dimensión de nivel (o principal) para la dimensión base del explorador de rutas. La dimensión de nivel del navegador de rutas es importante por dos motivos principales:

   * A medida que sigue una ruta de un elemento de dimensión base al siguiente, pasa de un elemento de dimensión de nivel al siguiente. Por ejemplo, supongamos que ha creado un navegador de rutas que muestra las páginas de un sitio web. Cada página es un elemento de la dimensión Página y la dimensión de nivel para Página es Vista de página. A medida que se mueve de una página a otra, se pasa de una vista de página a otra.
   * Al seleccionar una ruta de elementos de dimensión base en un navegador de rutas, se seleccionan los datos para los elementos correspondientes de la dimensión de nivel. La selección siempre incluye los elementos de la dimensión de nivel que se relacionan con la raíz y se refina añadiendo más elementos a la ruta. Por ejemplo: cuando selecciona una ruta de páginas, como raíz > A > B, está seleccionando los datos de las vistas de página asociadas con la raíz, donde la página siguiente es A y la página siguiente es B.

      Para obtener información sobre cómo seleccionar una ruta en un explorador de rutas, consulte [Selección de rutas](../../../../home/c-get-started/c-analysis-vis/c-path-browsers/t-sel-paths.md#task-bf44d08c71954ef2adec4b82f840adeb). Para obtener información sobre las selecciones, consulte [Realizar selecciones en Visualizaciones](../../../../home/c-get-started/c-vis/c-sel-vis/c-sel-vis.md#concept-012870ec22c7476e9afbf3b8b2515746).
   >[!NOTE]
   >
   >El navegador de rutas ignora los elementos de la dimensión de nivel sin elementos de dimensión base asociados. Esta situación puede ocurrir cuando se crea un explorador de rutas a partir de una asignación de procesos. Consulte [Creación de exploradores](../../../../home/c-get-started/c-analysis-vis/c-path-browsers/c-create-path-browsers.md#concept-e120de6a740d4b6f98dda9e2b638f6ff)de rutas.

* **Dimensión de grupo:** La dimensión de grupo determina cómo se agrupan los elementos de la dimensión de nivel para formar las rutas de un explorador de rutas. Específicamente, los elementos de dimensión de nivel asociados a una única ruta en un navegador de rutas no pueden abarcar más de un elemento de una dimensión de grupo.

   Para entenderlo, considere un ejemplo de uso de datos web. Supongamos que las dimensiones base, de nivel y de grupo para el explorador de rutas son Página, Vista de página y Sesión, respectivamente. Una ruta en el explorador de rutas muestra la secuencia de páginas A > B > C. La dimensión de grupo (Sesión) le indica que las vistas de página (elementos de la dimensión Vista de página) asociadas con la secuencia de página A > B > C se produjeron durante una sola sesión. Es importante tener en cuenta que puede haber varias sesiones durante las cuales hubo vistas de página para la secuencia de páginas A > B > C. Por lo tanto, la ruta que muestra la secuencia de páginas A > B > C representa todas las sesiones individuales en las que se produjeron las vistas de página para esa secuencia.

* **Métrica**: El grosor de la ruta que conduce a un elemento determinado es proporcional al valor de la métrica para ese elemento. Las rutas más gruesas indican valores de métricas buenos que las rutas más delgadas.

La etiqueta en la esquina superior izquierda del navegador de rutas nombra las dimensiones base y de grupo representadas en la visualización. El nombre de la dimensión de nivel no está visible en la visualización del navegador de rutas. La etiqueta toma la forma &quot;Secuencia de nombres *de dimensión* base+s para cada nombre *de dimensión de* grupo&quot;. Por ejemplo, la etiqueta Secuencia de películas para cada usuario indica que la dimensión base es Película y que la dimensión de grupo es Usuario.

![](assets/vis_PathBrowser_Movies.png)

Al hacer clic con el botón secundario en cualquier elemento del explorador de rutas, puede ver el nombre de la métrica asociada con el explorador de rutas y su valor para ese elemento.

![](assets/vis_PathBrowser_RightClick.png)

>[!NOTE]
>
>Puede cambiar las dimensiones y métricas predeterminadas para un explorador de rutas. Para obtener instrucciones sobre cómo configurar una visualización del navegador de rutas, consulte [Configuración de exploradores](../../../../home/c-get-started/c-intf-anlys-ftrs/t-config-path-brwsr.md#task-bbb3ddaa140a414f984b697c2b8202a3)de rutas.

