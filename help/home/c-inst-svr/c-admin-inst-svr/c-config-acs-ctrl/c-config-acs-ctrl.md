---
description: El archivo de configuración Control de acceso, Access Control.cfg, define los grupos de control de acceso mediante los cuales Insight Server concede permisos a los archivos en función de los atributos (OU, CN, etc.) del certificado de conexión entrante.
solution: Insight
title: Configuración del control de acceso
uuid: e0206b43-3c8c-48ec-b663-814f5b663b96
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Configuración del control de acceso{#configuring-access-control}

El archivo de configuración Control de acceso, Access Control.cfg, define los grupos de control de acceso mediante los cuales Insight Server concede permisos a los archivos en función de los atributos (OU, CN, etc.) del certificado de conexión entrante.

**Frecuencia recomendada:** Según sea necesario

[!DNL Insight Server] proporciona grupos de control de acceso configurables para administrar la seguridad de las conexiones a [!DNL Insight Server]. Los grupos de control de acceso identifican a los usuarios a los que se permite realizar funciones administrativas mediante [!DNL Insight].

Si necesita proporcionar acceso a nuevos usuarios o equipos, como al agregar un equipo a un [!DNL Insight Server] clúster, simplemente edite el archivo de configuración de Control de acceso.
