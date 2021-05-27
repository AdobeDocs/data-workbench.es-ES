---
description: Debe instalar y ejecutar Sensor en cada servidor web que proporcione el contenido del sitio para recopilar todas las solicitudes que vean esos servidores.
title: ¿Cómo puedo adquirir estos datos?
uuid: c0d8b01e-a135-4ef7-8159-811766929f62
exl-id: 1c886f60-eae9-48c2-b641-396c622035d4
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '333'
ht-degree: 3%

---

# ¿Cómo puedo adquirir estos datos?{#how-do-i-acquire-this-data}

Debe instalar y ejecutar Sensor en cada servidor web que proporcione el contenido del sitio para recopilar todas las solicitudes que vean esos servidores.

Estas solicitudes constituyen el 90% o más de las solicitudes realizadas a su sitio y el 90% o más de los datos necesarios para el análisis completo del tráfico del sitio. [!DNL Page Tags] debe utilizarse para recopilar el 10 % o menos restante de los datos de tráfico que no conoce el servidor web. Sin embargo, las siguientes son configuraciones válidas para la recopilación de datos de solicitudes web de su sitio, en orden de preferencia, según nuestra experiencia operativa:

1. [!DNL Sensor] se instala en cada servidor web que controle y que admita su sitio. El contenido de sitios de terceros, el contenido servido desde la caché y ciertos tipos de contenido dinámico deben etiquetarse, y dichas etiquetas de página deben enviar los datos que recopilan a un servidor web en su ubicación que ejecuta [!DNL Sensor]. Puede agregar un servidor web adicional si el nivel de tráfico de solicitud de etiqueta de página lo justifica, o en casos especiales, puede dedicar un servidor web para recopilar estas solicitudes de etiqueta de página.
1. [!DNL Sensor] se instala en dos servidores web, también denominados servidores de recopilación de datos en esta guía, en su ubicación, que están dedicados a recopilar datos de solicitudes de etiquetas de página de páginas etiquetadas. Todo el contenido del sitio está etiquetado y todas las etiquetas de página se dirigen a los dos servidores de recopilación de datos.
1. [!DNL Sensor’s] los servicios de recopilación de datos los proporciona un externalizador que ejecuta servidores de recopilación de datos para recopilar todos los datos de solicitudes web. En este caso, todo el contenido del sitio se etiqueta y las etiquetas de página envían sus datos a los servidores de recopilación de datos externalizados.

   Para obtener más información sobre [!DNL Sensor], consulte la *Guía de la Data Workbench [!DNL Sensor]*.
