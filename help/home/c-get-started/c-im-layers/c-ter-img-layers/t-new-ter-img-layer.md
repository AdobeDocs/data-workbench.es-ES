---
description: Pasos para que cualquier capa de terreno esté disponible para la visualización en el globo.
solution: Analytics
title: Hacer que una nueva capa de imagen de terreno esté disponible
topic: Data workbench
uuid: 8fb98a3e-6335-4922-a1e6-35c92b19e2ec
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Hacer que una nueva capa de imagen de terreno esté disponible{#make-a-new-terrain-image-layer-available}

Pasos para que cualquier capa de terreno esté disponible para la visualización en el globo.

1. En la carpeta Profiles\*profile name*\Maps del directorio de instalación del servidor de Área de trabajo de datos, coloque el archivo de capa y los archivos de imagen compatibles.
1. Edite el [!DNL order.txt] archivo en la carpeta Perfiles\*nombre de perfil*\Mapas para reflejar el orden en que desea que se muestren las capas. De forma predeterminada, las capas aparecen en orden lexicográfico por sus nombres.

   >[!NOTE]
   >
   >Al editar el [!DNL order.txt] archivo, procure no cubrir las capas de mapa que desee mostrar.

   Para obtener más información sobre el uso de [!DNL order.txt] archivos, consulte el capítulo Configuración de interfaz y características de análisis de la Guía *del usuario de*&#x200B;Área de trabajo de datos.

1. En Área de trabajo de datos, seleccione el perfil deseado haciendo clic con el botón derecho en la barra de título del espacio de trabajo y haciendo clic en **[!UICONTROL Switch Profile]** > *&lt;**[!UICONTROL profile name]**>*.
1. Haga clic con el botón secundario en la barra de título del espacio de trabajo y haga clic en **[!UICONTROL Work Online]**. Aparece una X junto a Trabajar en línea.
1. Abra un espacio de trabajo y, en una visualización de globo, haga clic con el botón derecho y seleccione la nueva capa. Aparece una X junto al nombre de la capa.
