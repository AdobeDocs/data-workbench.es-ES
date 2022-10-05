---
description: El perfil Geografía almacena una colección de capas y archivos de imágenes.
title: Mostrar capas
uuid: ebc7025d-e619-43dd-88da-7452ada3226b
exl-id: 12ec913f-c7e5-49b5-8792-db0881cb5cfe
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '267'
ht-degree: 1%

---

# Mostrar capas{#display-layers}

{{eol}}

El perfil Geografía almacena una colección de capas y archivos de imágenes.

Al mostrar un globo, puede seleccionar cuál de las capas disponibles se mostrará para una tarea de análisis determinada:

* **Mármol azul a 2 km:** Esta capa muestra el globo. Cuando no se selecciona esta capa, el globo no es visible.
* **Coordenadas IP:** Esta capa de puntos de elemento muestra la latitud y la longitud de las ubicaciones en el conjunto de datos en función de las direcciones IP de los visitantes.
* **Puntos postales:** Esta capa muestra la latitud y la longitud de las ubicaciones en el conjunto de datos en función de una lista de códigos postales de Estados Unidos proporcionada por el Adobe. La variable [!DNL Zip Points.txt] el archivo de búsqueda contiene los datos de código postal, latitud y longitud que se van a mostrar, mientras que la variable [!DNL Zip Points.layer] contiene los parámetros de configuración necesarios para mostrar estos datos en el globo. Ambos archivos se almacenan en la carpeta Profiles\Geography\Maps dentro del directorio de instalación del servidor de Data Workbench.

* ***Otros nombres de capa disponibles:*** Cada nombre de capa representa un [!DNL .layer] archivo almacenado en la carpeta Profiles\Geography\Maps, Profiles\IP Geo-location\Maps o en la carpeta Profiles\IP Geo-Intelligence\Maps del directorio de instalación de Insight Server.

>[!NOTE]
>
>Para tener el perfil de geolocalización de IP o de inteligencia geográfica de IP, debe suscribirse al servicio de geolocalización de IP o al servicio de inteligencia geográfica de IP, respectivamente.

Para controlar el orden en que se muestran las capas, puede utilizar una [!DNL order.txt] archivo. Consulte [Personalización de menús mediante archivos Order.txt](../../../../home/c-get-started/c-intf-anlys-ftrs/c-ctm-menus/t-cstm-menus-ordr-files.md#task-a391800a8dd444deb3e1516d5189f999).

**Alternar capas en un globo**

* Haga clic con el botón derecho en la visualización y haga clic en el nombre de capa que desee. Una X a la izquierda de la capa indica que la capa es visible.
