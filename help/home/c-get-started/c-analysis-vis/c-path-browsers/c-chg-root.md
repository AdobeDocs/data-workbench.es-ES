---
description: Puede cambiar la raíz de un navegador de rutas mediante la designación de un elemento mostrado como raíz o la adición de un nuevo elemento a la visualización.
solution: Analytics
title: Cambiar la raíz del explorador de rutas
topic: Data workbench
uuid: 0bb9b004-9736-411b-bd22-cac04f4733a6
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Cambiar la raíz del explorador de rutas{#change-the-path-browser-s-root}

Puede cambiar la raíz de un navegador de rutas mediante la designación de un elemento mostrado como raíz o la adición de un nuevo elemento a la visualización.

>[!NOTE]
>
>No se puede establecer un nodo de inicio o de fin como la raíz de un explorador de rutas.

**Configuración de la raíz de un explorador de rutas**

* Haga clic con el botón secundario en el elemento deseado y haga clic en **[!UICONTROL Set as root]**.

**Agregar un nuevo elemento al explorador de rutas**

1. Abra un gráfico o una tabla que muestre la dimensión cuyos elementos desee mostrar en el navegador de rutas.

   Por ejemplo, si está trabajando con datos de sitios web, abra un gráfico de página o una tabla e identifique la página que desea establecer como raíz.

1. Pulse Ctrl+Alt y arrastre el elemento deseado a la posición raíz del navegador de rutas.

   >[!NOTE]
   >
   >Puede cambiar la dimensión base asociada con un navegador de rutas arrastrando un elemento de la dimensión deseada al navegador de rutas. Este elemento se convierte en la nueva raíz del navegador de rutas y la etiqueta en la esquina superior izquierda del navegador de rutas cambia para reflejar la dimensión de este elemento.

   Por ejemplo, supongamos que crea un navegador de ruta de página que muestra la secuencia de páginas para cada sesión. Si arrastrara un elemento de la dimensión Término de búsqueda al explorador de rutas, el elemento de término de búsqueda se convertiría en la nueva raíz y la etiqueta ahora mostraría la secuencia de términos de búsqueda para cada sesión.

   >[!NOTE]
   >
   >Al arrastrar un elemento a un navegador de rutas, puede cambiar la dimensión base asociada con el navegador de rutas, pero no cambia la dimensión de nivel, la dimensión de grupo o la métrica. Por lo tanto, debe tener cuidado al elegir una dimensión base que tenga sentido cuando se utiliza con la dimensión de nivel, la dimensión de grupo y la métrica del explorador de rutas. Para cambiar la dimensión de nivel, la dimensión de grupo o la métrica, debe editar el archivo del navegador de rutas en un editor de texto como el Bloc de notas [!DNL *.vw] . Consulte [Configuración de exploradores](../../../../home/c-get-started/c-intf-anlys-ftrs/t-config-path-brwsr.md#task-bbb3ddaa140a414f984b697c2b8202a3)de rutas.

