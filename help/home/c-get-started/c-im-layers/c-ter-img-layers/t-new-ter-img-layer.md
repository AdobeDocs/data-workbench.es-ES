---
description: Pasos para que cualquier capa de terreno esté disponible para mostrar en la visualización del globo.
title: Hacer que una nueva capa de imagen de terreno esté disponible
uuid: 8fb98a3e-6335-4922-a1e6-35c92b19e2ec
exl-id: bf0e6b37-4c8a-4d50-8bc9-eb70ca1cbb23
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '183'
ht-degree: 7%

---

# Hacer que una nueva capa de imagen de terreno esté disponible{#make-a-new-terrain-image-layer-available}

Pasos para que cualquier capa de terreno esté disponible para mostrar en la visualización del globo.

1. En la carpeta Profiles\*profile name*\Maps del directorio de instalación del servidor de Data Workbench, coloque el archivo de capa y los archivos de imagen compatibles.
1. Edite el archivo [!DNL order.txt] en la carpeta Profiles\*profile name*\Maps para reflejar el orden en que desea que se muestren las capas. De forma predeterminada, las capas aparecen en orden lexicográfico por sus nombres.

   >[!NOTE]
   >
   >Al editar el archivo [!DNL order.txt], asegúrese de no ocultar las capas de mapa que desee mostrar.

   Para obtener más información sobre el uso de archivos [!DNL order.txt], consulte el capítulo Configuración de interfaz y características de análisis de la *Guía del usuario de Data Workbench*.

1. En la Data Workbench, seleccione el perfil deseado haciendo clic con el botón derecho en la barra de título del espacio de trabajo y haciendo clic en **[!UICONTROL Switch Profile]** > *&lt;**[!UICONTROL profile name]**>*.
1. Haga clic con el botón derecho en la barra de título del espacio de trabajo y haga clic en **[!UICONTROL Work Online]**. Aparece una X junto a Trabajo en línea.
1. Abra un espacio de trabajo y, en una visualización de globo, haga clic con el botón derecho y seleccione la nueva capa. Aparece una X junto al nombre de la capa.
