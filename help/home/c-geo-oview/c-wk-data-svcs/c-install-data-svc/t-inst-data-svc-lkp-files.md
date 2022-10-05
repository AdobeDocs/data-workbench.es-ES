---
description: Pasos para instalar los archivos de búsqueda de Geo-Intelligence o Geo-location de IP.
title: Instalación de los archivos de búsqueda del servicio de datos
uuid: a3fe8a14-2c74-4105-bc5b-2298f0f4b61e
exl-id: b19904f4-ead0-4bed-a79f-864c78bc0e1d
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '222'
ht-degree: 6%

---

# Instalación de los archivos de búsqueda del servicio de datos{#installing-the-data-service-lookup-files}

{{eol}}

Pasos para instalar los archivos de búsqueda de Geo-Intelligence o Geo-location de IP.

El archivo de búsqueda (Lookups\*nombre de perfil*\*nombre de archivo de datos*) proporcionado con el perfil del servicio de datos es un archivo binario ( [!DNL .bin]) que contiene datos relacionados geográficamente basados en direcciones IP. Debe reemplazar este archivo periódicamente para asegurarse de que dispone de los datos geográficos más recientes. Consulte [Actualización de archivos del servicio de datos](../../../../home/c-geo-oview/c-wk-data-svcs/c-updt-data-svc-files.md#concept-2b3d11e4cb814fc09add5de58a87045c).

**Para instalar los archivos de búsqueda de Geo-Intelligence o Geo-location de IP**

>[!NOTE]
>
>Todas sus [!DNL IP Geo-location] o [!DNL IP Geo-intelligence] los archivos de datos deben ajustarse a la memoria física disponible del servidor de Data Workbench.

1. Abra la carpeta Búsquedas en el [!DNL .zip] archivo que recibió de Adobe.
1. Copie la carpeta IP Geo-Intelligence o Geo-location de IP a la carpeta Lookups del directorio de instalación del servidor de Data Workbench (desea terminar con un ...\Lookups\IP Geo-Intelligence o un ...\Lookups\carpeta de geolocalización de IP en el servidor de Data Workbench, como se muestra en el siguiente ejemplo. Los nombres de las otras carpetas de la carpeta Búsquedas pueden diferir de los que se muestran.

   ![Información sobre los pasos](assets/Geo_installLookups_dirIP.png)

   >[!NOTE]
   >
   >Periódicamente, Adobe le envía archivos que contienen [!DNL IP Geo-intelligence] o [!DNL IP Geo-location] archivos de búsqueda. Cuando reciba estos archivos, debe cargarlos en el servidor de Data Workbench tal como indica el Adobe. Para obtener instrucciones, consulte la siguiente sección.
