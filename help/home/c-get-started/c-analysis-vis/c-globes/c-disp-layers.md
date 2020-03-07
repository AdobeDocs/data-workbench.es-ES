---
description: El perfil Geografía almacena una colección de capas y archivos de imágenes.
solution: Analytics
title: Mostrar capas
topic: Data workbench
uuid: ebc7025d-e619-43dd-88da-7452ada3226b
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Mostrar capas{#display-layers}

El perfil Geografía almacena una colección de capas y archivos de imágenes.

Al mostrar un globo, puede seleccionar qué capas disponibles mostrar para una tarea de análisis concreta:

* **Mármol azul 2 km:** Esta capa muestra el globo. Cuando esta capa no está seleccionada, el globo no está visible.
* **Coordenadas IP:** Esta capa de punto de elemento muestra la latitud y la longitud de las ubicaciones en el conjunto de datos en función de las direcciones IP del visitante.
* **Puntos postales:** Esta capa muestra la latitud y la longitud de las ubicaciones del conjunto de datos en función de una lista de códigos postales de Estados Unidos proporcionada por Adobe. El archivo de [!DNL Zip Points.txt] búsqueda contiene los datos de código postal, latitud y longitud que se van a mostrar, mientras que el [!DNL Zip Points.layer] archivo contiene los parámetros de configuración necesarios para mostrar estos datos en el globo. Ambos archivos se almacenan en la carpeta Profiles\Geography\Maps folder within the Data Workbench server installation directory.

* ***Otros nombres de capas disponibles:*** Cada nombre de capa representa un [!DNL .layer] archivo almacenado en la carpeta Profiles\Geography\Maps folder, Profiles\IP Geo-location\Maps o en la carpeta Profiles\IP Geo-Intelligence\Maps del directorio de instalación de Insight Server.

>[!NOTE]
>
>Para tener el perfil Geo-location IP o Geo-Intelligence IP, debe suscribirse al servicio de datos Geo-location IP o Geo-Intelligence, respectivamente.

Para controlar el orden en que se muestran las capas, puede utilizar un [!DNL order.txt] archivo. Consulte [Personalización de menús con archivos](../../../../home/c-get-started/c-intf-anlys-ftrs/c-ctm-menus/t-cstm-menus-ordr-files.md#task-a391800a8dd444deb3e1516d5189f999)Order.txt.

**Alternar capas en un globo**

* Haga clic con el botón derecho en la visualización y haga clic en el nombre de la capa que desee. Una X a la izquierda de la capa indica que la capa está visible.

