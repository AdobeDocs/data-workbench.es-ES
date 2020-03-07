---
description: Pasos para que una capa de punto de elemento esté disponible para la visualización en el globo.
solution: Analytics
title: Disponibilidad de una nueva capa de punto de elemento
topic: Data workbench
uuid: 7880de63-d206-4c56-b8cf-75882d867ace
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Disponibilidad de una nueva capa de punto de elemento{#making-a-new-element-point-layer-available}

Pasos para que una capa de punto de elemento esté disponible para la visualización en el globo.

1. En la carpeta Profiles\*profile name*\Maps del directorio de instalación del servidor del área de trabajo de datos, coloque el archivo de capa y el archivo de búsqueda relacionado.
1. Si ha definido una nueva dimensión para la capa de punto del elemento y aún no ha retransformado el conjunto de datos, vuelva a transformar el conjunto de datos ahora.
1. Edite el [!DNL order.txt] archivo en la carpeta Perfiles\*nombre de perfil*\Mapas para reflejar el orden en que desea que se muestren las capas. De forma predeterminada, las capas aparecen en orden lexicográfico por sus nombres.

   >[!NOTE]
   >
   >Al editar el [!DNL order.txt] archivo, procure no cubrir las capas de mapa que desee mostrar.

   Para obtener más información sobre el uso de [!DNL order.txt] archivos, consulte el capítulo Configuración de interfaz y características de análisis de la Guía *del usuario de*&#x200B;Área de trabajo de datos.

1. En el área de trabajo de datos, seleccione el perfil deseado haciendo clic con el botón derecho en la barra de título del espacio de trabajo y haciendo clic en **[!UICONTROL Switch Profile]** > *&lt;**[!UICONTROL profile name]**>*.
1. Haga clic con el botón secundario en la barra de título del espacio de trabajo y haga clic en **[!UICONTROL Work Online]**. Aparece una X junto a [!DNL Work Online].
1. Abra un espacio de trabajo y, en una visualización de globo, haga clic con el botón derecho y seleccione la nueva capa. Aparece una X junto al nombre de la capa.
