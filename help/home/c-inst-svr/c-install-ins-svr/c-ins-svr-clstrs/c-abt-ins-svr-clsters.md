---
description: Se requiere un clúster de Insight Server cuando la cantidad de datos que desea procesar y poner a disposición de los usuarios de Insight e Report excede la capacidad de un solo Insight Server.
title: Acerca de los clústeres de Insight Server
uuid: d65e0fe5-f87d-4d8e-a208-9192e9d62fb5
exl-id: b26e0f63-76db-461d-91e7-0968624aa0f7
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '320'
ht-degree: 2%

---

# Acerca de los clústeres de Insight Server{#about-insight-server-clusters}

{{eol}}

Se requiere un clúster de Insight Server cuando la cantidad de datos que desea procesar y poner a disposición de los usuarios de Insight e Report excede la capacidad de un solo Insight Server.

Al configurar un [!DNL Insight Server] clúster, puede distribuir un único conjunto de datos de análisis entre varios equipos de un clúster para aprovechar la potencia de procesamiento de varios [!DNL Insight Servers].

El primer paso en la implementación de un [!DNL Insight Server] es para asignar la variable [!DNL Insight Server] equipos del clúster. La primera [!DNL Insight Server] la máquina que ha configurado es la máquina maestra [!DNL Insight Server] (a veces denominado [!DNL Insight Server]).

>[!NOTE]
>
>Si está utilizando un [!DNL Insight Server] Unidad de servidor de archivos (FSU), Adobe recomienda que configure la FSU como la FSU maestra [!DNL Insight Server]. Para obtener información sobre cómo configurar una FSU, consulte la *Guía de configuración de conjuntos de datos*.

El maestro [!DNL Insight Server] gestiona la comunicación entre los demás [!DNL Insight Servers] en el clúster (llamados servidores de procesamiento o, a veces, servidores de consulta) y las instancias de [!DNL Insight] y [!DNL Report]. Para un conjunto de datos determinado, el procesamiento del archivo de registro se produce en el (uno o más) designado [!DNL Insight Servers] (maestro o procesamiento) tal como se especifica en la [!DNL Insight Server] archivos de configuración. Cuando se trabaja en un entorno agrupado, [!DNL Insight] las instalaciones están configuradas para acceder al maestro [!DNL Insight Server], pero las consultas pueden ser gestionadas por cualquiera de los [!DNL Insight Servers] dentro del clúster.

>[!NOTE]
>
>La variable **PAServer.cfg** archivo. Si desea enviar trabajos de agrupación en clúster de Predictive Analytics a servidores de Insight, deberá configurar la variable [!DNL PAServer.cfg] para administrar los envíos de clustering del lado del servidor. El perfil personalizado debe heredar el [!DNL PAServer.cfg] del perfil de Predictive Analytics ([!DNL Server\Profiles\Predictive Analytics\Dataset]). Configure un *Servidor maestro* en este archivo y guarde la variable [!DNL PAServer.cfg] al sitio de implementación.
>
>
```
>PAServer = PAServerConfig: 
>   Master Server = serverInfo: 
>       Address = string: 
>       Port = int: 80
>       Use SSL = bool: false
>```

>[!IMPORTANT]
>
>Las instrucciones de este capítulo no se aplican a la creación de un [!DNL Insight Server] grupo compuesto por más de cinco (5) [!DNL Insight Servers]. Póngase en contacto con Adobe para obtener los requisitos del sistema y las recomendaciones de configuración de perfil para clústeres de más de cinco [!DNL Insight Servers].
