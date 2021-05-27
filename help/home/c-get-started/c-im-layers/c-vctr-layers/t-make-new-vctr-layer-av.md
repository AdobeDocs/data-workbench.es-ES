---
description: Pasos para que cualquier capa vectorial esté disponible para mostrar en la visualización del globo.
title: Hacer que una nueva capa vectorial esté disponible
uuid: 7bfbae0d-e5db-4aa2-8a8b-15b4980aadb5
exl-id: 6c084bac-1a6d-452a-bf07-e502d0f2145a
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '171'
ht-degree: 7%

---

# Hacer que una nueva capa vectorial esté disponible{#make-a-new-vector-layer-available}

Pasos para que cualquier capa vectorial esté disponible para mostrar en la visualización del globo.

1. En la carpeta Profiles\*profile name*\Maps del directorio de instalación del servidor de Data Workbench, coloque el archivo de capa y los archivos [!DNL .vec] o [!DNL .tsv].
1. Edite el archivo [!DNL order.txt] en la carpeta Profiles\*profile name*\Maps para reflejar el orden en que desea que se muestren las capas. De forma predeterminada, las capas aparecen en orden lexicográfico por sus nombres.

   >[!NOTE]
   >
   >Al editar el archivo [!DNL order.txt], asegúrese de no ocultar las capas de mapa que desee mostrar.

   Para obtener más información sobre el uso de archivos [!DNL order.txt], consulte [Personalización de menús mediante archivos Order.txt](../../../../home/c-get-started/c-intf-anlys-ftrs/c-ctm-menus/t-cstm-menus-ordr-files.md#task-a391800a8dd444deb3e1516d5189f999).

1. En Insight, seleccione el perfil deseado haciendo clic con el botón derecho en la barra de título del espacio de trabajo y haciendo clic en **[!UICONTROL Switch Profile]** > *&lt;**[!UICONTROL profile name]**>*.
1. Haga clic con el botón derecho en la barra de título del espacio de trabajo y haga clic en **[!UICONTROL Work Online]**. Aparece una X junto a Trabajo en línea.
1. Abra un espacio de trabajo y, en una visualización de globo, haga clic con el botón derecho y seleccione la nueva capa. Aparece una X junto al nombre de la capa.
