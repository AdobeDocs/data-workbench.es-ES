---
description: Puede cambiar la raíz de un explorador de rutas mediante la designación de un elemento mostrado como raíz o la adición de un nuevo elemento a la visualización.
title: Cambio de la raíz del explorador de rutas
uuid: 0bb9b004-9736-411b-bd22-cac04f4733a6
exl-id: 09842b93-af26-42b9-9395-a02b86978b21
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '347'
ht-degree: 2%

---

# Cambio de la raíz del explorador de rutas{#change-the-path-browser-s-root}

Puede cambiar la raíz de un explorador de rutas mediante la designación de un elemento mostrado como raíz o la adición de un nuevo elemento a la visualización.

>[!NOTE]
>
>No se puede establecer un nodo de inicio o de fin como la raíz de un explorador de rutas.

**Para establecer la raíz de un explorador de rutas**

* Haga clic con el botón derecho en el elemento deseado y haga clic en **[!UICONTROL Set as root]**.

**Para agregar un nuevo elemento al explorador de rutas**

1. Abra un gráfico o una tabla que muestre la dimensión cuyos elementos desea mostrar en el explorador de rutas.

   Por ejemplo, si está trabajando con datos de sitios web, abra un gráfico de páginas o una tabla e identifique la página que desea establecer como raíz.

1. Pulse Ctrl+Alt y arrastre el elemento deseado a la posición raíz del navegador de rutas.

   >[!NOTE]
   >
   >Puede cambiar la dimensión base asociada a un explorador de rutas arrastrando un elemento de la dimensión deseada al explorador de rutas. Este elemento se convierte en la nueva raíz del explorador de rutas y la etiqueta de la esquina superior izquierda del explorador de rutas cambia para reflejar la dimensión de este elemento.

   Por ejemplo, supongamos que crea un navegador de rutas de página que muestra la Secuencia de páginas para cada sesión. Si arrastrara un elemento de la dimensión Término de búsqueda al explorador de rutas, el elemento de término de búsqueda se convertiría en la nueva raíz y la etiqueta ahora mostraría la Secuencia de términos de búsqueda para cada sesión.

   >[!NOTE]
   >
   >Arrastrar un elemento a un explorador de rutas puede cambiar la dimensión base asociada al explorador de rutas, pero no cambia la dimensión de nivel, la dimensión de grupo o la métrica. Por lo tanto, debe tener cuidado al elegir una dimensión base que tenga sentido cuando se utiliza con la dimensión de nivel del explorador de rutas, la dimensión de grupo y la métrica. Para cambiar la dimensión de nivel, la dimensión de grupo o la métrica, debe editar el archivo [!DNL *.vw] del explorador de rutas en un editor de texto como el Bloc de notas. Consulte [Configuración de exploradores de rutas](../../../../home/c-get-started/c-intf-anlys-ftrs/t-config-path-brwsr.md#task-bbb3ddaa140a414f984b697c2b8202a3).
