---
description: Se requiere un clúster de Insight Server cuando la cantidad de datos que desea procesar y poner a disposición de los usuarios de Insight e Report excede la capacidad de un solo Insight Server.
title: Acerca de los clústeres de Insight Server
uuid: d65e0fe5-f87d-4d8e-a208-9192e9d62fb5
exl-id: b26e0f63-76db-461d-91e7-0968624aa0f7
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '320'
ht-degree: 2%

---

# Acerca de los clústeres de Insight Server{#about-insight-server-clusters}

Se requiere un clúster de Insight Server cuando la cantidad de datos que desea procesar y poner a disposición de los usuarios de Insight e Report excede la capacidad de un solo Insight Server.

Al configurar un clúster [!DNL Insight Server], puede distribuir un único conjunto de datos de análisis entre varios equipos de un clúster para aprovechar la potencia de procesamiento de varios [!DNL Insight Servers].

El primer paso en la implementación de un clúster [!DNL Insight Server] es asignar las máquinas [!DNL Insight Server] del clúster. El primer [!DNL Insight Server] equipo que configure es su [!DNL Insight Server] maestro (a veces denominado [!DNL Insight Server] principal).

>[!NOTE]
>
>Si utiliza una [!DNL Insight Server] unidad de servidor de archivos (FSU), Adobe recomienda configurar la FSU como su [!DNL Insight Server] maestro. Para obtener información sobre la configuración de una FSU, consulte la *Guía de configuración de conjuntos de datos*.

El [!DNL Insight Server] maestro administra la comunicación entre los otros [!DNL Insight Servers] del clúster (llamados servidores de procesamiento o, a veces, servidores de consulta) y las instancias de [!DNL Insight] y [!DNL Report]. Para un conjunto de datos determinado, el procesamiento del archivo de registro se produce en el (uno o más) designado [!DNL Insight Servers] (maestro o procesamiento) como se especifica en los archivos de configuración [!DNL Insight Server]. Cuando se trabaja en un entorno agrupado, las instalaciones [!DNL Insight] están configuradas para acceder al [!DNL Insight Server] maestro, pero las consultas pueden ser gestionadas por cualquiera de las [!DNL Insight Servers] dentro del clúster.

>[!NOTE]
>
>El archivo **PAServer.cfg**. Si desea enviar trabajos de agrupación en clúster de Predictive Analytics a servidores de Insight, deberá configurar el archivo [!DNL PAServer.cfg] para gestionar los envíos de clúster del lado del servidor. El perfil personalizado debe heredar el [!DNL PAServer.cfg] del perfil de Predictive Analytics ([!DNL Server\Profiles\Predictive Analytics\Dataset]). Establezca un *Master Server* en este archivo y guarde el [!DNL PAServer.cfg] en el sitio de implementación.
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
>Las instrucciones de este capítulo no se aplican a la creación de un [!DNL Insight Server] clúster que consta de más de cinco (5) [!DNL Insight Servers]. Póngase en contacto con Adobe para obtener los requisitos del sistema y las recomendaciones de configuración de perfil para clústeres de más de cinco [!DNL Insight Servers].
