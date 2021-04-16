---
description: Información sobre la instalación de un servicio de datos en un servidor de Data Workbench.
title: Instalación de un servicio de datos en un servidor de Data Workbench
uuid: afe8e259-7fef-4327-9afc-18f36a1934db
exl-id: 414e93b7-4e9c-4c84-8fba-8052939240c5
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '240'
ht-degree: 7%

---

# Instalación de un servicio de datos en un servidor de Data Workbench{#installing-a-data-service-on-a-data-workbench-server}

Información sobre la instalación de un servicio de datos en un servidor de Data Workbench.

Si utiliza el servicio de inteligencia geográfica IP o el servicio de datos de ubicación geográfica IP, debe instalar el perfil [!DNL IP Geo-intelligence] o [!DNL IP Geo-location] y los archivos de búsqueda relacionados en el servidor de Data Workbench. Debe completar los siguientes procedimientos después de instalar el perfil [!DNL Geography] de Data Workbench. Consulte [Instalación de la geografía de Data Workbench](../../../../home/c-geo-oview/c-inst-geo/c-inst-geo.md). Si no ha instalado Data Workbench, siga las instrucciones de la *Guía del usuario de Data Workbench* antes de continuar.

>[!NOTE]
>
>Para instalar los archivos del servicio de datos, debe tener acceso a los archivos del servidor de Data Workbench.

Adobe distribuye los servicios de información geográfica IP y de ubicación geográfica IP como [!DNL .zip] archivos. Cada archivo [!DNL .zip] contiene dos carpetas: Búsquedas y perfiles. Para instalar un servicio de datos en el servidor de Data Workbench, debe realizar los siguientes pasos:

* Instale el perfil del servicio de datos. Consulte [Instalación del perfil de servicio de datos](../../../../home/c-geo-oview/c-wk-data-svcs/c-install-data-svc/c-inst-data-svc-prof.md).
* Instale las búsquedas del servicio de datos. Consulte [Instalación de los archivos de búsqueda del servicio de datos](../../../../home/c-geo-oview/c-wk-data-svcs/c-install-data-svc/t-inst-data-svc-lkp-files.md).

Debe instalar el perfil del servicio de datos y los archivos de búsqueda en el equipo del servidor de Data Workbench en el que esté procesando y ejecutando el perfil del conjunto de datos. Si está ejecutando un clúster de servidores de Data Workbench, debe instalar los archivos en el servidor maestro. Para obtener información sobre los perfiles de conjuntos de datos, consulte la *Guía de configuración de conjuntos de datos*.
