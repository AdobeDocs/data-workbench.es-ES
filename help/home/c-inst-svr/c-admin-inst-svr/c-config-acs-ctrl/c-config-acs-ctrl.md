---
description: El archivo de configuración Control de acceso, Control de acceso.cfg, define los grupos de control de acceso mediante los cuales Insight Server concede permisos a archivos en función de los atributos (OU, CN, etc.) del certificado de la conexión entrante.
title: Configuración del control de acceso
uuid: e0206b43-3c8c-48ec-b663-814f5b663b96
exl-id: 2836c907-fc74-4d35-badc-b8f06cd6989f
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '132'
ht-degree: 4%

---

# Configuración del control de acceso{#configuring-access-control}

{{eol}}

El archivo de configuración Control de acceso, Control de acceso.cfg, define los grupos de control de acceso mediante los cuales Insight Server concede permisos a archivos en función de los atributos (OU, CN, etc.) del certificado de la conexión entrante.

**Frecuencia recomendada:** Según sea necesario

[!DNL Insight Server] proporciona grupos de control de acceso configurables para administrar la seguridad de las conexiones a [!DNL Insight Server]. Los grupos de control de acceso identifican a los usuarios a los que se permite realizar funciones administrativas mediante [!DNL Insight].

Si necesita proporcionar acceso a nuevos usuarios o equipos, por ejemplo, al agregar un equipo a un [!DNL Insight Server] , simplemente edite el archivo de configuración de Control de acceso.
