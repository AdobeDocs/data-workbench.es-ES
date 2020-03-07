---
description: Pasos para que cualquier capa de punto de elemento esté disponible para la visualización en el globo.
solution: Analytics
title: Hacer que una nueva capa de punto de elemento esté disponible
topic: Data workbench
uuid: 5f4bad2f-e98d-4224-bba8-285ad5e23da9
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Hacer que una nueva capa de punto de elemento esté disponible{#make-a-new-element-point-layer-available}

Pasos para que cualquier capa de punto de elemento esté disponible para la visualización en el globo.

1. En la carpeta Profiles\*profile name*\Maps del directorio de instalación del servidor de Área de trabajo de datos, coloque el archivo de capa y el archivo de búsqueda relacionado.
1. Si ha definido una nueva dimensión para la capa de punto del elemento y aún no ha retransformado el conjunto de datos, vuelva a transformar el conjunto de datos ahora.
1. Edite el [!DNL order.txt] archivo en la carpeta Perfiles\*nombre de perfil*\Mapas para reflejar el orden en que desea que se muestren las capas. De forma predeterminada, las capas aparecen en orden lexicográfico por sus nombres.

   >[!NOTE]
   >
   >Al editar el [!DNL order.txt] archivo, procure no cubrir las capas de mapa que desee mostrar.

   Para obtener más información sobre el uso de [!DNL order.txt] archivos, consulte el capítulo Configuración de interfaz y características de análisis de la Guía *del usuario de*&#x200B;Área de trabajo de datos.

1. En Área de trabajo de datos, seleccione el perfil deseado haciendo clic con el botón derecho en la barra de título del espacio de trabajo y haciendo clic en **[!UICONTROL Switch Profile]** > *&lt;**[!UICONTROL profile name]**>*.
1. Haga clic con el botón secundario en la barra de título del espacio de trabajo y haga clic en **[!UICONTROL Work Online]**. Aparece una X junto a Trabajar en línea.
1. Abra un espacio de trabajo y, en una visualización de globo, haga clic con el botón derecho y seleccione la nueva capa. Aparece una X junto al nombre de la capa.
