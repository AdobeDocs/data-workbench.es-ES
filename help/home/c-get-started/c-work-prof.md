---
description: Data Workbench descarga perfiles en el equipo.
title: Perfiles
uuid: 8ea36138-9839-40e5-89e2-4b120f1dd7aa
exl-id: a140f549-448c-4e34-8eae-ad154fa01f1f
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '448'
ht-degree: 0%

---

# Perfiles{#profiles}

{{eol}}

Data Workbench descarga perfiles en el equipo.

Si carga un perfil por primera vez, debe tener una conexión de red con la variable [!DNL Data Workbench server] y trabajar en línea para que la Data Workbench pueda descargar los archivos necesarios desde la [!DNL Data Workbench server].

La descarga del perfil puede tardar varios minutos. No debe comenzar a trabajar con el perfil hasta que la caché de datos empiece a rellenarse, pero no tiene que esperar hasta que esté llena. Para realizar un seguimiento del progreso de la caché de datos, el progreso de la sincronización de perfiles y la fecha y hora de los datos procesados más recientemente, observe las barras de estado a medida que se carga el perfil.

>[!NOTE]
>
>No ve datos en visualizaciones que agregue hasta que la caché de datos empiece a llenarse.

La próxima vez que cargue el perfil, las actualizaciones del perfil y sus datos se descargarán únicamente si tiene una conexión de red con la variable [!DNL Data Workbench server] y están trabajando en línea. Si trabaja sin conexión, el perfil y sus datos se cargan desde la caché del equipo. En este caso, está viendo la versión del perfil y los datos que se descargaron la última vez que trabajó en línea con el perfil. Para obtener más información sobre cómo trabajar en línea o sin conexión, consulte [Trabajar sin conexión y en línea](../../home/c-get-started/c-off-on.md#concept-cef8758ede044b18b3558376c5eb9f54).

Cuando necesite cambiar su perfil (mediante el [!DNL Profile Manager] o [!DNL Server Files Manager]), debe trabajar en línea para asegurarse de tener la versión más actualizada del perfil. Para obtener más información sobre la variable [!DNL Profile Manager] y [!DNL Server Files Manager], consulte [Interfaces administrativas](../../home/c-get-started/c-admin-intrf/c-admin-intrf.md#concept-855c1a91e1a948969fab592adca15f74).

Si no puede acceder o cargar un perfil, es posible que deba confirmar lo siguiente:

* Tiene una conexión de red con el [!DNL Data Workbench server] máquina en la que reside el perfil.
* Tiene los permisos adecuados para acceder al perfil.

Para obtener ayuda, póngase en contacto con el administrador del sistema.

## Carga o conmutación de perfiles {#section-c50499d7d8084d7cadfada52df33f5f4}

1. Iniciar Data Workbench.
1. En la barra lateral, haga clic en el nombre del perfil y, a continuación, haga clic en **[!UICONTROL Switch Profile]** > *&lt;**[!UICONTROL profile name]**>*, donde *nombre de perfil* es el perfil con el que desea trabajar.

   ![](assets/sidebar_profile.png)

Si es la primera vez que carga el perfil seleccionado, puede tardar varios minutos en descargar suficientes datos para rellenar una visualización.

## Acceso a un perfil en un clúster {#section-189a0ac04a8f46099c11c0f4f77b6dbb}

Data Workbench de usuarios que acceden a un perfil que se ejecuta en un

El clúster de servidores de Data Workbench solo identifica el servidor de Data Workbench maestro en el archivo de configuración de Data Workbench ( [!DNL Insight.cfg]). Desde la perspectiva del usuario de la Data Workbench, solo se puede acceder al perfil en un servidor de Data Workbench (el servidor maestro de Datas Workbench). Sin embargo, las solicitudes de consulta de los analistas se pueden dirigir a cualquiera de los servidores de Data Workbench del clúster.

Para obtener más información sobre los perfiles que se ejecutan en un clúster de Data Workbench Server, consulte la *Guía de instalación y administración de productos para servidor*.
