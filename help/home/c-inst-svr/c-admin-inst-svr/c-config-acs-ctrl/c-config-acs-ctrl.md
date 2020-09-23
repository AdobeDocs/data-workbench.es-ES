---
description: El archivo de configuración de Control de acceso, Control de acceso.cfg, define los grupos de controles de acceso mediante los cuales Insight Server concede permisos a los archivos en función de los atributos (OU, CN, etc.) del certificado de conexión entrante.
solution: Analytics
title: Configuración del control de acceso
uuid: e0206b43-3c8c-48ec-b663-814f5b663b96
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '132'
ht-degree: 4%

---


# Configuración del control de acceso{#configuring-access-control}

El archivo de configuración de Control de acceso, Control de acceso.cfg, define los grupos de controles de acceso mediante los cuales Insight Server concede permisos a los archivos en función de los atributos (OU, CN, etc.) del certificado de conexión entrante.

**Frecuencia recomendada:** Según sea necesario

[!DNL Insight Server] proporciona grupos de controles de acceso configurables para administrar la seguridad de las conexiones a [!DNL Insight Server]. Los grupos de controles de acceso identifican a los usuarios a los que se permite realizar funciones administrativas mediante [!DNL Insight].

Si necesita proporcionar acceso a nuevos usuarios o equipos, como al agregar un equipo a un [!DNL Insight Server] clúster, simplemente edite el archivo de configuración de Control de acceso.
