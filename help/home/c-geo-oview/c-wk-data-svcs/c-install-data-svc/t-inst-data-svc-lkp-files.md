---
description: Pasos para instalar los archivos de búsqueda de Geo-Intelligence o Geo-location de IP.
title: Instalación de los archivos de búsqueda del servicio de datos
uuid: a3fe8a14-2c74-4105-bc5b-2298f0f4b61e
exl-id: b19904f4-ead0-4bed-a79f-864c78bc0e1d
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '222'
ht-degree: 6%

---

# Instalación de los archivos de búsqueda del servicio de datos{#installing-the-data-service-lookup-files}

Pasos para instalar los archivos de búsqueda de Geo-Intelligence o Geo-location de IP.

El archivo de búsqueda (Lookups\*nombre de perfil*\*nombre de archivo de datos*) proporcionado con el perfil del servicio de datos es un archivo binario ( [!DNL .bin]) que contiene datos relacionados geográficamente basados en la dirección IP. Debe reemplazar este archivo periódicamente para asegurarse de que dispone de los datos geográficos más recientes. Consulte [Actualización de archivos del servicio de datos](../../../../home/c-geo-oview/c-wk-data-svcs/c-updt-data-svc-files.md#concept-2b3d11e4cb814fc09add5de58a87045c).

**Para instalar los archivos de búsqueda de Geo-Intelligence o Geo-location de IP**

>[!NOTE]
>
>Todos los archivos de datos [!DNL IP Geo-location] o [!DNL IP Geo-intelligence] deben caber en la memoria física disponible del servidor de Data Workbench.

1. Abra la carpeta Lookups del archivo [!DNL .zip] que recibió de Adobe.
1. Copie la carpeta IP Geo-Intelligence o Geo-location de IP a la carpeta Lookups del directorio de instalación del servidor de Data Workbench (desea terminar con un ...\Lookups\IP Geo-intelligence or a ...\Lookups\IP Geo-location folder on your data workbench server as shown in the following example. Los nombres de las otras carpetas de la carpeta Búsquedas pueden diferir de los que se muestran.

   ![Información sobre los pasos](assets/Geo_installLookups_dirIP.png)

   >[!NOTE]
   >
   >Periódicamente, Adobe le envía archivos que contienen archivos de búsqueda [!DNL IP Geo-intelligence] o [!DNL IP Geo-location] actualizados. Cuando reciba estos archivos, debe cargarlos en el servidor de Data Workbench tal como indica el Adobe. Para obtener instrucciones, consulte la siguiente sección.
