---
description: Debe asegurarse de que los equipos en los que se instalan los productos de servidor de Adobe cumplen los requisitos mínimos del sistema definidos en el documento de requisitos mínimos del sistema.
solution: Analytics
title: Confirmación del buen estado de sus sistemas
uuid: 6d132865-36ab-40fc-be24-e031f356fce2
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '169'
ht-degree: 5%

---


# Confirmación del buen estado de sus sistemas{#confirming-your-systems-are-healthy}

Debe asegurarse de que los equipos en los que se instalan los productos de servidor de Adobe cumplen los requisitos mínimos del sistema definidos en el documento de requisitos mínimos del sistema.

**Frecuencia recomendada:** Cada 5-10 minutos

También debe monitorear sus sistemas según las optimizaciones para el funcionamiento de ese hardware en particular, incluyendo, entre otras, la supervisión de lo siguiente:

* Uso de CPU
* Espacio en disco
* Mensajes del sistema de hardware
* Temperatura interna del sistema
* Uso de memoria
* Condiciones de la fuente de alimentación
* Rendimiento y errores del controlador de disco o RAID

Adobe recomienda configurar la herramienta de administración para avisar a los administradores cuando cualquier parámetro del sistema de un equipo servidor supere el umbral establecido.

Para [!DNL Insight Server] equipos, Adobe también recomienda configurar cada uno [!DNL Insight Server] para que indique cuándo alcanza el límite mínimo de espacio en disco que ha configurado. Para obtener más información sobre estas alertas, consulte [Configuración de alertas](../../../home/c-inst-svr/c-admin-inst-svr/t-config-adm-alrts.md#task-0858f588da4941aa9d4952f6592681aa)administrativas.
