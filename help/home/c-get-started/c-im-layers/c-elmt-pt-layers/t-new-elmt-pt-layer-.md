---
description: Pasos para hacer que cualquier capa de punto de elemento esté disponible para mostrar en la visualización del globo.
title: Hacer que una nueva capa de punto de elemento esté disponible
uuid: 5f4bad2f-e98d-4224-bba8-285ad5e23da9
exl-id: 12797335-0788-4103-a581-41bc3bb3dcc9
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '207'
ht-degree: 6%

---

# Hacer que una nueva capa de punto de elemento esté disponible{#make-a-new-element-point-layer-available}

{{eol}}

Pasos para hacer que cualquier capa de punto de elemento esté disponible para mostrar en la visualización del globo.

1. En la carpeta Profiles\*profile name*\Maps del directorio de instalación del servidor de Data Workbench, coloque el archivo de capa y su archivo de búsqueda relacionado.
1. Si ha definido una nueva dimensión para la capa de punto del elemento y aún no ha retransformado el conjunto de datos, vuelva a transformar el conjunto de datos ahora.
1. Edite el [!DNL order.txt] en la carpeta Profiles\*profile name*\Maps para reflejar el orden en que desea que se muestren las capas. De forma predeterminada, las capas aparecen en orden lexicográfico por sus nombres.

   >[!NOTE]
   >
   >Al editar el [!DNL order.txt] , asegúrese de no cubrir las capas de mapa que desee mostrar.

   Para obtener más información sobre el uso de [!DNL order.txt] , consulte el capítulo Configuración de interfaz y características de análisis de la sección *Guía del usuario de Data Workbench*.

1. En Data Workbench, seleccione el perfil deseado haciendo clic con el botón derecho en la barra de título del espacio de trabajo y haciendo clic en **[!UICONTROL Switch Profile]** > *&lt;**[!UICONTROL profile name]**>*.
1. Haga clic con el botón derecho en la barra de título del espacio de trabajo y haga clic en **[!UICONTROL Work Online]**. Aparece una X junto a Trabajo en línea.
1. Abra un espacio de trabajo y, en una visualización de globo, haga clic con el botón derecho y seleccione la nueva capa. Aparece una X junto al nombre de la capa.
