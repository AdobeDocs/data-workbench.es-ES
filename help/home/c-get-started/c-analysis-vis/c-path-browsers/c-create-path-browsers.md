---
description: Puede crear un navegador de rutas a partir de un gráfico, una tabla o una asignación de procesos.
solution: Analytics
title: Creación de exploradores de rutas
topic: Data workbench
uuid: 84a5e587-fb02-461b-aec8-1b6ad473ebc3
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Creación de exploradores de rutas{#creating-path-browsers}

Puede crear un navegador de rutas a partir de un gráfico, una tabla o una asignación de procesos.

**Creación de un explorador de rutas a partir de un gráfico o una tabla**

1. Agregue un explorador de rutas a su área de trabajo. La visualización está en blanco excepto para la etiqueta (Secuencia de...) en la esquina superior izquierda.
1. Abra un gráfico o una tabla que muestre la dimensión cuyos elementos desee mostrar en el navegador de rutas. Por ejemplo, si está trabajando con datos de sitios web, abra un gráfico de página o una tabla e identifique la página que desea establecer como raíz.
1. Pulse Ctrl+Alt y arrastre el elemento deseado al navegador de rutas. La etiqueta en la esquina superior izquierda del explorador de rutas cambia para reflejar la dimensión base cuyo elemento arrastre al explorador de rutas.

>[!NOTE]
>
>Al arrastrar un elemento a un navegador de rutas, puede cambiar la dimensión base asociada con el navegador de rutas, pero no cambia la dimensión de nivel, la dimensión de grupo o la métrica. Por lo tanto, debe tener cuidado al elegir una dimensión base que tenga sentido cuando se utiliza con la dimensión de nivel, la dimensión de grupo y la métrica del explorador de rutas. Para cambiar la dimensión de nivel, la dimensión de grupo o la métrica, debe editar el archivo del navegador de rutas en un editor de texto como el Bloc de notas [!DNL *.vw] . Consulte [Configuración de exploradores](../../../../home/c-get-started/c-intf-anlys-ftrs/t-config-path-brwsr.md#task-bbb3ddaa140a414f984b697c2b8202a3)de rutas.

**Para crear un explorador de rutas a partir de una asignación de procesos**

>[!NOTE]
>
>Un navegador de rutas creado a partir de una asignación de procesos muestra únicamente los elementos que se muestran en la asignación de procesos. No se muestran otros elementos de la dimensión base.

1. Cree un mapa de proceso. Consulte [Creación de mapas](../../../../home/c-get-started/c-analysis-vis/c-proc-maps/c-create-proc-maps.md#concept-daf5b14dae7a442191611b1b9c1122bf)de proceso.
1. Arrastre el elemento deseado desde la asignación de procesos hasta el explorador de rutas. El elemento se convierte en la raíz del explorador de rutas.

>[!NOTE]
>
>Cuando se crea un navegador de rutas a partir de una asignación de procesos, el navegador de rutas omite los elementos de la dimensión de nivel sin elementos de dimensión base asociados. Cuando arrastra un nodo desde una asignación de proceso a un explorador de rutas, la dimensión base del explorador de rutas (denominada Mapa) se define mediante la asignación de procesos y sus elementos se limitan a los elementos de la asignación de procesos. Como resultado, algunos elementos de la dimensión de nivel del navegador de rutas no tienen elementos de dimensión base asociados y no están representados en el navegador de rutas.

