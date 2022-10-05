---
description: El archivo de configuración Sensor, txlogd.conf, contiene parámetros que Sensor utiliza para establecer una conexión con el servidor de Data Workbench.
title: Edición del archivo txlogd.conf del sensor
uuid: e7f41c14-9047-4e1a-be0f-8acc8ecb1160
exl-id: ed243bb4-cf87-4bcf-89d6-5ff5cec3bc6e
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '260'
ht-degree: 3%

---

# Edición del archivo txlogd.conf del sensor{#editing-the-sensor-txlogd-conf-file}

{{eol}}

El archivo de configuración Sensor, txlogd.conf, contiene parámetros que Sensor utiliza para establecer una conexión con el servidor de Data Workbench.

Estos parámetros incluyen la dirección del servidor, el número de puerto y el protocolo de comunicación (HTTP o HTTPS). El archivo de configuración también contiene opciones de filtrado de contenido de registro e información de experimento controlada. Los experimentos controlados permiten a los diseñadores del sitio realizar experimentos para probar contenido o cambios de diseño en un subconjunto de todos los visitantes del sitio.

Al cambiar otro [!DNL txlogd.conf] como la dirección IP del [!DNL data workbench server] o el nombre del [!DNL Sensor], es posible que pueda reemplazar [!DNL txlogd.conf] con la versión actualizada y [!DNL Sensor] recogerá los cambios automáticamente. En algunos sistemas, es posible que no pueda editar o reemplazar el archivo sin detener el servidor web o el proceso del transmisor.

**Para abrir y editar txlogd.conf**

1. Vaya a la [!DNL Sensor] directorio de instalación y abra [!DNL txlogd.conf] en un editor de texto.
1. Edite el archivo según sea necesario.
1. Guarde y cierre el archivo.

   * La ubicación del archivo de configuración del experimento controlado (definido por el parámetro ExpFile en la variable [!DNL txlogd.conf] ) debe estar en un directorio del servidor web al que puedan acceder los desarrolladores de contenido web o que esté controlado por el sistema de administración de contenido.
   * El valor del parámetro ExpCookieURL es una página virtual que se utiliza para probar sitios web. A los usuarios que visiten esa página se les asignará un nuevo ID de seguimiento.

Para obtener más información sobre cómo trabajar con [!DNL txlogd.conf], póngase en contacto con los servicios de consultoría de Adobe.
