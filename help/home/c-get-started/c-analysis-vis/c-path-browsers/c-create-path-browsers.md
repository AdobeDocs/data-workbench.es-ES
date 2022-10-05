---
description: Puede crear un explorador de rutas a partir de un gráfico, una tabla o un mapa de procesos.
title: Creación de exploradores de rutas
uuid: 84a5e587-fb02-461b-aec8-1b6ad473ebc3
exl-id: 9fa11b84-da73-447a-8b10-7eab381e3f66
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '380'
ht-degree: 2%

---

# Creación de exploradores de rutas{#creating-path-browsers}

{{eol}}

Puede crear un explorador de rutas a partir de un gráfico, una tabla o un mapa de procesos.

**Creación de un explorador de rutas a partir de un gráfico o una tabla**

1. Agregue un navegador de rutas al espacio de trabajo. La visualización está en blanco excepto para la etiqueta (Secuencia de...) en la esquina superior izquierda.
1. Abra un gráfico o una tabla que muestre la dimensión cuyos elementos desea mostrar en el explorador de rutas. Por ejemplo, si está trabajando con datos de sitios web, abra un gráfico de páginas o una tabla e identifique la página que desea establecer como raíz.
1. Pulse Ctrl+Alt y arrastre el elemento deseado al navegador de rutas. La etiqueta en la esquina superior izquierda del explorador de rutas cambia para reflejar la dimensión base cuyo elemento arrastre al explorador de rutas.

>[!NOTE]
>
>Arrastrar un elemento a un explorador de rutas puede cambiar la dimensión base asociada al explorador de rutas, pero no cambia la dimensión de nivel, la dimensión de grupo o la métrica. Por lo tanto, debe tener cuidado al elegir una dimensión base que tenga sentido cuando se utiliza con la dimensión de nivel del explorador de rutas, la dimensión de grupo y la métrica. Para cambiar la dimensión de nivel, la dimensión de grupo o la métrica, debe editar la [!DNL *.vw] en un editor de texto como Bloc de notas. Consulte [Configuración de exploradores de rutas](../../../../home/c-get-started/c-intf-anlys-ftrs/t-config-path-brwsr.md#task-bbb3ddaa140a414f984b697c2b8202a3).

**Creación de un explorador de rutas a partir de un mapa de procesos**

>[!NOTE]
>
>Un explorador de rutas creado a partir de un mapa de procesos muestra solamente los elementos que se muestran en el mapa de procesos. Otros elementos de la dimensión base no se muestran.

1. Creación de un mapa del proceso. Consulte [Creación de mapas de procesos](../../../../home/c-get-started/c-analysis-vis/c-proc-maps/c-create-proc-maps.md#concept-daf5b14dae7a442191611b1b9c1122bf).
1. Arrastre el elemento deseado desde el mapa de proceso hasta el explorador de rutas. El elemento se convierte en la raíz del explorador de rutas.

>[!NOTE]
>
>Cuando se crea un explorador de rutas a partir de un mapa de procesos, el explorador de rutas ignora los elementos de la dimensión de nivel sin elementos de dimensión base asociados. Cuando arrastra un nodo desde un mapa de proceso a un explorador de rutas, la dimensión base del explorador de rutas (denominada Mapa) se define en el mapa de procesos y sus elementos se limitan a los elementos del mapa de procesos. Como resultado, algunos elementos de la dimensión de nivel del explorador de rutas no tienen elementos de dimensión base asociados y no se representan en el explorador de rutas.
