---
description: El Área de trabajo de datos descarga perfiles en el equipo.
title: Perfiles
uuid: 8ea36138-9839-40e5-89e2-4b120f1dd7aa
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Profiles{#profiles}

El Área de trabajo de datos descarga perfiles en el equipo.

Si está cargando un perfil por primera vez, debe tener una conexión de red con el [!DNL Data Workbench server] y trabajar en línea para que el Área de trabajo de datos pueda descargar los archivos necesarios desde el [!DNL Data Workbench server].

La descarga del perfil puede tardar varios minutos. No debe empezar a trabajar con el perfil hasta que la caché de datos empiece a rellenarse, pero no tiene que esperar hasta que esté llena. Puede rastrear el progreso de la caché de datos, el progreso de la sincronización de perfiles y la fecha y hora de los datos procesados más recientemente, mirando las barras de estado a medida que se carga el perfil.

>[!NOTE]
>
>No se ven datos en visualizaciones que se agregan hasta que la caché de datos comienza a llenarse.

La próxima vez que cargue el perfil, las actualizaciones del mismo y sus datos se descargarán únicamente si tiene una conexión de red con el perfil [!DNL Data Workbench server] y está trabajando en línea. Si está trabajando sin conexión, el perfil y sus datos se cargan desde la caché del equipo. En este caso, está viendo la versión del perfil y los datos que se descargaron la última vez que trabajó en línea con el perfil. Para obtener más información sobre cómo trabajar en línea en lugar de sin conexión, consulte [Trabajar sin conexión y en línea](../../home/c-get-started/c-off-on.md#concept-cef8758ede044b18b3558376c5eb9f54).

Cuando necesite cambiar su perfil (mediante el [!DNL Profile Manager] o el [!DNL Server Files Manager]), debe trabajar en línea para asegurarse de que tiene la versión más actualizada del perfil. Para obtener más información sobre [!DNL Profile Manager] y el [!DNL Server Files Manager], consulte Interfaces [administrativas](../../home/c-get-started/c-admin-intrf/c-admin-intrf.md#concept-855c1a91e1a948969fab592adca15f74).

Si no puede acceder a un perfil o cargarlo, es posible que tenga que confirmar lo siguiente:

* Tiene una conexión de red con el equipo en el que reside el [!DNL Data Workbench server] perfil.
* Tiene los permisos adecuados para acceder al perfil.

Para obtener ayuda, póngase en contacto con el administrador del sistema.

## Carga o conmutación de perfiles {#section-c50499d7d8084d7cadfada52df33f5f4}

1. Inicie Área de trabajo de datos.
1. En la barra lateral, haga clic en el nombre del perfil y en **[!UICONTROL Switch Profile]** > *&lt;**[!UICONTROL profile name]**>*, donde el nombre *del* perfil es el perfil con el que desea trabajar.

   ![](assets/sidebar_profile.png)

Si es la primera vez que carga el perfil seleccionado, puede que le lleve varios minutos descargar datos suficientes para completar una visualización.

## Acceso a un perfil en un clúster {#section-189a0ac04a8f46099c11c0f4f77b6dbb}

Usuarios de Área de trabajo de datos que acceden a un perfil que se ejecuta en un

el clúster de servidores del área de trabajo de datos identifica únicamente el servidor maestro del área de trabajo de datos en el archivo de configuración del área de trabajo de datos ( [!DNL Insight.cfg]). Desde la perspectiva del usuario de Área de trabajo de datos, el perfil solo es accesible en un servidor de Área de trabajo de datos (el servidor maestro de Área de trabajo de datos). Sin embargo, las solicitudes de consulta de los analistas se pueden dirigir a cualquiera de los servidores del área de trabajo de datos del clúster.

Para obtener más información sobre los perfiles que se ejecutan en un clúster de Data Workbench Server, consulte la Guía *de instalación y administración de productos* de servidor.
