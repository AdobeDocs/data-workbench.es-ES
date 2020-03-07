---
description: El archivo de configuración Sensor, txlogd.conf, contiene parámetros que Sensor utiliza para establecer una conexión con el servidor del área de trabajo de datos.
solution: Insight
title: Edición del archivo txlogd.conf del sensor
uuid: e7f41c14-9047-4e1a-be0f-8acc8ecb1160
translation-type: tm+mt
source-git-commit: 25366087936dfa5e31c5921aac400535ec259f2e

---


# Edición del archivo txlogd.conf del sensor{#editing-the-sensor-txlogd-conf-file}

El archivo de configuración Sensor, txlogd.conf, contiene parámetros que Sensor utiliza para establecer una conexión con el servidor del área de trabajo de datos.

Estos parámetros incluyen la dirección del servidor, el número de puerto y el protocolo de comunicación (HTTP o HTTPS). El archivo de configuración también contiene opciones de filtrado de contenido de registro e información del experimento controlado. Los experimentos controlados permiten a los diseñadores del sitio realizar experimentos para probar los cambios de contenido o diseño en un subconjunto de todos los visitantes del sitio.

Al cambiar otros [!DNL txlogd.conf] parámetros, como la dirección IP del [!DNL data workbench server] o el nombre del [!DNL Sensor], puede simplemente reemplazar [!DNL txlogd.conf] por la versión actualizada y [!DNL Sensor] recoger los cambios automáticamente. En algunos sistemas, es posible que no pueda editar o reemplazar el archivo sin detener el servidor Web o el proceso del transmisor.

**Para abrir y editar txlogd.conf**

1. Vaya al directorio de instalación [!DNL Sensor] y abra el [!DNL txlogd.conf] archivo en un editor de texto.
1. Edite el archivo según sea necesario.
1. Guarde y cierre el archivo.

   * La ubicación del archivo de configuración del experimento controlado (definido por el parámetro ExpFile en el [!DNL txlogd.conf] archivo) debe estar en un directorio del servidor web al que puedan acceder los desarrolladores de contenido web o que esté controlado por el sistema de administración de contenido.
   * El valor del parámetro ExpCookieURL es una página virtual que se utiliza para probar sitios web. A los usuarios que visiten esa página se les proporcionará un nuevo ID de seguimiento.

Para obtener más información sobre cómo trabajar con [!DNL txlogd.conf], póngase en contacto con los servicios de consultoría de Adobe.
