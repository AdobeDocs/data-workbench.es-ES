---
description: Pasos para que una nueva capa de terreno esté disponible para la visualización del globo.
title: Disponibilidad de una nueva capa de imagen de terreno
uuid: aeeb4ab0-f55c-47b8-96e4-eafd4df4d68a
exl-id: 76374298-ed65-4fcf-b40b-be7c15784f40
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '180'
ht-degree: 7%

---

# Disponibilidad de una nueva capa de imagen de terreno{#making-a-new-terrain-image-layer-available}

Pasos para que una nueva capa de terreno esté disponible para la visualización del globo.

1. En la carpeta Profiles\*profile name*\Maps dentro del directorio de instalación **[!UICONTROL Insight Server]**, coloque el archivo de capa y los archivos de imagen compatibles.
1. Edite el archivo [!DNL order.txt] en la carpeta Profiles\*profile name*\Maps para reflejar el orden en que desea que se muestren las capas. De forma predeterminada, las capas aparecen en orden lexicográfico por sus nombres.

   >[!NOTE]
   >
   >Al editar el archivo [!DNL order.txt], asegúrese de no ocultar las capas de mapa que desee mostrar.

   Para obtener más información sobre el uso de archivos [!DNL order.txt], consulte el capítulo Configuración de interfaz y características de análisis de la *Guía del usuario de Data Workbench*.

1. En Data Workbench, seleccione el perfil deseado haciendo clic con el botón derecho en la barra de título del espacio de trabajo y haciendo clic en **[!UICONTROL Switch Profile]** > *&lt;**[!UICONTROL profile name]**>*.
1. Haga clic con el botón derecho en la barra de título del espacio de trabajo y haga clic en **[!UICONTROL Work Online]**. Aparece una X junto a [!DNL Work Online].
1. Abra un espacio de trabajo y, en una visualización de globo, haga clic con el botón derecho y seleccione la nueva capa. Aparece una X junto al nombre de la capa.
