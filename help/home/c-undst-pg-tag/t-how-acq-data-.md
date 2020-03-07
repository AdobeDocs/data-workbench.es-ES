---
description: Debe instalar y ejecutar Sensor en cada servidor web que proporcione el contenido del sitio para recopilar todas las solicitudes que ven esos servidores.
solution: Analytics
title: ¿Cómo puedo adquirir estos datos?
topic: Data workbench
uuid: c0d8b01e-a135-4ef7-8159-811766929f62
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# ¿Cómo puedo adquirir estos datos?{#how-do-i-acquire-this-data}

Debe instalar y ejecutar Sensor en cada servidor web que proporcione el contenido del sitio para recopilar todas las solicitudes que ven esos servidores.

Estas solicitudes constituyen el 90% o más de las solicitudes realizadas en el sitio y el 90% o más de los datos necesarios para el análisis completo del tráfico del sitio. [!DNL Page Tags] luego debe utilizarse para recopilar el 10 % restante o menos de los datos de tráfico que sus servidores Web no conocen. Sin embargo, las siguientes son configuraciones válidas para la recopilación de datos de solicitudes Web de su sitio, en orden de preferencia, según nuestra experiencia operativa:

1. [!DNL Sensor] se instala en cada servidor web que controla y que admite el sitio. Se debe etiquetar el contenido de sitios de terceros, el contenido servido desde la caché y ciertos tipos de contenido dinámico, y dichas etiquetas de página deben enviar los datos que recopilan a un servidor web en la ubicación que se está ejecutando [!DNL Sensor]. Puede agregar un servidor web adicional si el nivel de tráfico de solicitud de etiqueta de página lo justifica o, en casos especiales, puede dedicar un servidor web para recopilar estas solicitudes de etiqueta de página.
1. [!DNL Sensor] se instala en dos servidores Web, también denominados servidores de recopilación de datos en esta guía, en su ubicación que están dedicados a recopilar datos de solicitud de etiqueta de página de páginas etiquetadas. Todo el contenido del sitio está etiquetado y todas las etiquetas de página se dirigen a los dos servidores de recopilación de datos.
1. [!DNL Sensor’s] los servicios de recopilación de datos son proporcionados por un proveedor externo que ejecuta servidores de recopilación de datos para recopilar todos los datos de solicitud web. En este caso, todo el contenido del sitio está etiquetado y las etiquetas de página envían sus datos a los servidores de recopilación de datos externalizados.

   Para obtener más información sobre [!DNL Sensor], consulte la *Guía[!DNL Sensor]del área de trabajo de datos*.

