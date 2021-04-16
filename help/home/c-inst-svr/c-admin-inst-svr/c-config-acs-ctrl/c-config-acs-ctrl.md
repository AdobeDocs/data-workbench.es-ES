---
description: El archivo de configuración Control de acceso, Control de acceso.cfg, define los grupos de control de acceso mediante los cuales Insight Server concede permisos a archivos en función de los atributos (OU, CN, etc.) del certificado de la conexión entrante.
title: Configuración del control de acceso
uuid: e0206b43-3c8c-48ec-b663-814f5b663b96
exl-id: 2836c907-fc74-4d35-badc-b8f06cd6989f
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '132'
ht-degree: 4%

---

# Configuración del control de acceso{#configuring-access-control}

El archivo de configuración Control de acceso, Control de acceso.cfg, define los grupos de control de acceso mediante los cuales Insight Server concede permisos a archivos en función de los atributos (OU, CN, etc.) del certificado de la conexión entrante.

**Frecuencia recomendada:** según sea necesario

[!DNL Insight Server] proporciona grupos de control de acceso configurables para administrar la seguridad de las conexiones a  [!DNL Insight Server]. Los grupos de control de acceso identifican a los usuarios a los que se permite realizar funciones administrativas mediante [!DNL Insight].

Si necesita proporcionar acceso a nuevos usuarios o equipos, como cuando agrega un equipo a un clúster [!DNL Insight Server], simplemente edite el archivo de configuración de Control de acceso.
