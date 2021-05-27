---
description: El perfil Geografía almacena una colección de capas y archivos de imágenes.
title: Mostrar capas
uuid: ebc7025d-e619-43dd-88da-7452ada3226b
exl-id: 12ec913f-c7e5-49b5-8792-db0881cb5cfe
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '267'
ht-degree: 1%

---

# Mostrar capas{#display-layers}

El perfil Geografía almacena una colección de capas y archivos de imágenes.

Al mostrar un globo, puede seleccionar cuál de las capas disponibles se mostrará para una tarea de análisis determinada:

* **Mármol azul a 2 km:**  esta capa muestra el globo. Cuando no se selecciona esta capa, el globo no es visible.
* **Coordenadas IP:** esta capa de puntos de elemento muestra la latitud y la longitud de las ubicaciones de su conjunto de datos en función de las direcciones IP de los visitantes.
* **Puntos postales:** esta capa muestra la latitud y la longitud de las ubicaciones en el conjunto de datos en función de una lista de códigos postales de Estados Unidos proporcionados por el Adobe. El archivo de búsqueda [!DNL Zip Points.txt] contiene los datos de código postal, latitud y longitud que se van a mostrar, mientras que el archivo [!DNL Zip Points.layer] contiene los parámetros de configuración necesarios para mostrar estos datos en el globo. Ambos archivos se almacenan en la carpeta Profiles\Geography\Maps folder within the Data Workbench server installation directory.

* ***Otros nombres de capa disponibles:*** Cada nombre de capa representa un  [!DNL .layer] archivo almacenado en la carpeta Profiles\Geography\Maps folder, Profiles\IP Geo-location\Maps o en la carpeta Profiles\IP Geo-Intelligence\Maps del directorio de instalación de Insight Server.

>[!NOTE]
>
>Para tener el perfil de geolocalización de IP o de inteligencia geográfica de IP, debe suscribirse al servicio de geolocalización de IP o al servicio de inteligencia geográfica de IP, respectivamente.

Para controlar el orden en que se muestran las capas, puede utilizar un archivo [!DNL order.txt]. Consulte [Personalización de menús mediante archivos Order.txt](../../../../home/c-get-started/c-intf-anlys-ftrs/c-ctm-menus/t-cstm-menus-ordr-files.md#task-a391800a8dd444deb3e1516d5189f999).

**Alternar capas en un globo**

* Haga clic con el botón derecho en la visualización y haga clic en el nombre de capa que desee. Una X a la izquierda de la capa indica que la capa es visible.
