---
description: Se requiere un clúster de Insight Server cuando la cantidad de datos que desea procesar y hacer accesible a los usuarios de Insight e Report supera la capacidad de un solo servidor de Insight.
solution: Analytics
title: Acerca de los clústeres de Insight Server
uuid: d65e0fe5-f87d-4d8e-a208-9192e9d62fb5
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '320'
ht-degree: 2%

---


# Acerca de los clústeres de Insight Server{#about-insight-server-clusters}

Se requiere un clúster de Insight Server cuando la cantidad de datos que desea procesar y hacer accesible a los usuarios de Insight e Report supera la capacidad de un solo servidor de Insight.

Al configurar un [!DNL Insight Server] clúster, puede distribuir un conjunto de datos de una sola análisis en varios equipos de un clúster para aprovechar la potencia de procesamiento de varios [!DNL Insight Servers].

El primer paso en la implementación de un [!DNL Insight Server] clúster es asignar los [!DNL Insight Server] equipos del clúster. La primera [!DNL Insight Server] máquina que configure es la maestra [!DNL Insight Server] (a veces denominada principal [!DNL Insight Server]).

>[!NOTE]
>
>Si utiliza una unidad de servidor de [!DNL Insight Server] archivos (FSU), Adobe recomienda que configure la FSU como la unidad maestra [!DNL Insight Server]. Para obtener información sobre la configuración de una FSU, consulte la Guía *de configuración de* Dataset.

El maestro [!DNL Insight Server] administra la comunicación entre el otro [!DNL Insight Servers] en el clúster (llamados servidores de procesamiento o, a veces, servidores de consulta) y las instancias de [!DNL Insight] y [!DNL Report]. Para un conjunto de datos determinado, el procesamiento del archivo de registro se produce en el (uno o más) designado [!DNL Insight Servers] (maestro o procesamiento) como se especifica en los archivos de [!DNL Insight Server] configuración. Cuando se trabaja en un entorno agrupado, [!DNL Insight] las instalaciones se configuran para acceder al maestro [!DNL Insight Server], pero cualquiera de las consultas puede gestionarlas [!DNL Insight Servers] dentro del clúster.

>[!NOTE]
>
>Archivo **PAServer.cfg** . Si desea enviar trabajos de clúster de Predictive Analytics a los servidores de Insight, deberá configurar el [!DNL PAServer.cfg] archivo para gestionar los envíos de clúster del lado del servidor. El perfil personalizado debe heredar el [!DNL PAServer.cfg] del perfil de análisis predictivo ([!DNL Server\Profiles\Predictive Analytics\Dataset]). Establezca un *servidor* maestro en este archivo y guarde el [!DNL PAServer.cfg] en el sitio de implementación.
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
>Las instrucciones que figuran en este capítulo no se aplican a la creación de un [!DNL Insight Server] grupo compuesto por más de cinco (5) [!DNL Insight Servers]. Póngase en contacto con Adobe para obtener los requisitos del sistema y las recomendaciones de configuración de perfil para clústeres de más de cinco [!DNL Insight Servers].
